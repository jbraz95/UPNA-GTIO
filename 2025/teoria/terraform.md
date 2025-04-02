# Infraestructura como código: Terraform

Como hemos visto podemos crear recursos en AWS de forma manual, pero esto no es escalable, por lo que vamos a ver como podemos automatizar la creación de recursos en AWS usando Terraform.

- [Infraestructura como código: Terraform](#infraestructura-como-código-terraform)
  - [¿Qué es la infraestructura como código?](#qué-es-la-infraestructura-como-código)
  - [¿Qué es Terraform?](#qué-es-terraform)
    - [Código de Terraform](#código-de-terraform)
    - [Variables en terraform](#variables-en-terraform)
    - [TfState de Terraform](#tfstate-de-terraform)
    - [Comandos de Terraform](#comandos-de-terraform)
    - [Módulos de Terraform](#módulos-de-terraform)
  - [Buenas prácticas](#buenas-prácticas)
  - [Instalación de Terraform y tutoriales para AWS](#instalación-de-terraform-y-tutoriales-para-aws)

## ¿Qué es la infraestructura como código?

La infraestructura como código es una práctica que consiste en gestionar y aprovisionar infraestructura y aplicaciones a través de archivos de texto legibles por máquina y almacenados en un repositorio de control de versiones. Básicamente: escribir código para crear infraestructura. Esto lo hacemos porque nos permite:

- Automatizar la creación de infraestructura (Más rápido, más seguro, más fiable)
- Generar siempre la misma infraestructura (No nos olvidamos de nada ni hacemos nada diferente)
- Parametrizar la infraestructura para poder crearla de forma dinámica (No tenemos que crear una infraestructura para cada entorno)
- Mayor control sobre la infraestructura (Podemos ver el histórico de los cambios que se han hecho y revertirlos si es necesario)

Las herramientas más populares para gestionar la infraestructura como código son:

- Terraform: Es la herramienta que vamos a ver en este curso. Es una herramienta de HashiCorp que permite crear, modificar y eliminar recursos en la nube de forma segura y eficiente. Es multiplataforma y multi-cloud, por lo que podemos usarla para crear recursos en AWS, Azure, Google Cloud, etc.
- Ansible: Es una herramienta de automatización de infraestructura. Está centrada en el aprovisionamiento de máquinas virtuales y la gestión de configuraciones.
- Chef: Muy similar a Ansible.
- CloudFormation: Es una herramienta de AWS para crear y gestionar recursos en AWS. Es muy similar a Terraform, pero solo se puede usar para crear recursos en AWS.

## ¿Qué es Terraform?

Nosotros nos vamos a centrar en este curso en Terraform. Es la herramienta más famosa y usada para crear infraestructura en la nube. Es una herramienta de HashiCorp que permite crear, modificar y eliminar recursos en la nube de forma segura y eficiente. Funciona con providers, que son plugins que permiten crear recursos en diferentes proveedores de nube. Por ejemplo, el provider de AWS permite crear recursos en AWS, el provider de Azure permite crear recursos en Azure, etc.

### Código de Terraform

El código de Terraform es declarativo, es decir, especificamos el estado que queremos que tenga la infraestructura y Terraform se encarga de crearla. Por ejemplo, si queremos crear una instancia de EC2 en AWS, en lugar de especificar los pasos que hay que seguir para crearla (crear un grupo de seguridad, crear una instancia de EC2, etc.), simplemente especificamos que queremos crear una instancia de EC2 y Terraform se encarga de crearla.

Un ejemplo de como crear una instancia de EC2 en Terraform sería:

```terraform

# Declaración del proveedor
provider "aws" {
  region = "us-west-2"
}

# Creación del bucket S3 con ID generado aleatoriamente
resource "aws_s3_bucket" "example" {
  bucket = "my-terraform-bucket-${random_id.random.hex}"
}

# Creación del grupo de seguridad donde abrimos todos los puertos
resource "aws_security_group" "instance" {
  name_prefix = "instance_sg_"

  ingress {
    from_port   = 0
    to_port     = 65535
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# Creación de la instancia EC2
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  vpc_security_group_ids = [aws_security_group.instance.id]

  # Asociar la instancia con el bucket S3 creado
  user_data = <<-EOF
    #!/bin/bash
    aws s3 mb s3://${aws_s3_bucket.example.bucket}
    EOF
}
```

En este ejemplo, primero declaramos el proveedor de AWS y especificamos la región en la que se crearán los recursos.

Luego, creamos el bucket S3 utilizando la resource aws_s3_bucket. El ID del bucket se genera aleatoriamente utilizando la función random_id. En la misma configuración, también podrías establecer las políticas de acceso, como versioning, logging, cifrado, entre otros.

A continuación, creamos un grupo de seguridad utilizando la resource aws_security_group. En este caso, se permite el acceso a cualquier puerto TCP desde cualquier dirección IP. Asegúrate de modificar esto para ajustarlo a las necesidades de tu caso de uso.

Finalmente, creamos la instancia EC2 utilizando la resource aws_instance. Asociamos la instancia al grupo de seguridad creado previamente, y le asignamos el tipo de instancia y AMI que deseamos utilizar. Además, en el campo user_data incluimos un script de usuario que crea el bucket S3 previamente creado en la instancia.

### Variables en terraform

Terraform tiene variables para no hardcodear todos los valores en el código. Por ejemplo, si queremos crear una instancia de EC2 en AWS, en lugar de especificar el ID de la AMI que queremos utilizar, podemos crear una variable y especificar el ID de la AMI en el fichero de variables. De esta forma, si queremos crear una instancia de EC2 con otra AMI, solo tenemos que cambiar el valor de la variable. Esto tambien vale para nombres o otras propiedades de los recursos.

### TfState de Terraform

Cuando ejecutamos terraform, este genera un fichero de estado que contiene la información de todos los recursos que hemos creado. Este fichero de estado es muy importante, ya que nos permite saber el estado actual de la infraestructura y si hay algún cambio que se ha hecho manualmente, Terraform lo detectará y lo tendrá en cuenta para realizar los cambios necesarios. Digamos que Terraform conoce el estado de la infraestructura usando tres fuentes de información: el código, el estado y la nube (con llamadas api).

### Comandos de Terraform

Terraform tiene varios comandos que nos permiten gestionar la infraestructura:

- `terraform init`: Inicializa el directorio de trabajo, descargando los plugins necesarios y creando el fichero de estado.
- `terraform plan`: Compara el estado actual con el código y muestra los cambios que se van a realizar.
- `terraform apply`: Crea los recursos especificados en el código.
- `terraform destroy`: Elimina los recursos especificados en el código.

Estos 4 comandos son los que vamos a usar más a menudo. También hay otros comandos que nos permiten hacer otras cosas pero su uso será más esporádico.

### Módulos de Terraform

Para no repetir código lo que haremos serán módulos, que son trozos de código que podemos reutilizar en diferentes partes de nuestro código. Por ejemplo, en todos nuestros proyectos queremos levantar las instancias junto con un s3 propio y permitir el acceso usando un grupo de seguridad. En lugar de reescribir ese código todas las veces crearemos un módulo que haga eso. Ese módulo estará parametrizado y lo podremos usar en todos los proyectos.

## Buenas prácticas

Algunas buenas prácticas las siguientes:

- Crear un bucket S3 para almacenar el estado de Terraform. De esta forma, si varios desarrolladores están trabajando en el mismo proyecto, todos tendrán acceso al estado de Terraform.
- Usar modules para no repetir código.
- Usar variables para no hardcodear valores en el código. Usaremos tfvars para esto (cargando diferentes variables según el entorno)
- Crear un fichero de variables por cada entorno (dev, prod, etc.).
- Usar outputs para mostrar información de los recursos creados.
- Usar el comando `terraform fmt` para formatear el código de Terraform.
- Usar el comando `terraform validate` para validar el código de Terraform.
- Usar el comando `terraform plan` para ver los cambios que se van a realizar antes de ejecutar `terraform apply`.

## Instalación de Terraform y tutoriales para AWS

Os recomiendo seguir el tutorial de HashiCorp para aprender a usar Terraform con AWS. [Link](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)
