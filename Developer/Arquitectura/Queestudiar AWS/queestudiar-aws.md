---
layout: page
title: Queestudiar AWS
permalink: /Queestudiar AWS/
parent: Arquitectura
grand_parent: Developer
nav_order: 4
has_children: true
---


<details open markdown="block">
  <summary>
    Índice:
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

AWS es un servicio que a su vez ofrece muchos otros servicios de administración de aplicaciones de software; y, para acceder a todo ello, primeramente se necesita tener una cuenta en AWS. Cuando se cumpla con ese requisito primordial y obvio, empezaremos a configurar AWS para que pueda ser accesible desde el código, es decir desde las aplicaciones de servicio y de cliente que se estén desarrollando.

Luego de crear tener una cuenta en AWS necesitamos crear un usuario dentro de AWS a quien se le darán las credenciales de accesibilidad, para ello necesitamos utilizar el primer servicio de AWS llamado AWS IAm.

# AWS IAm

1. Para acceder a este servicio utilizaremos el buscador y digitaremos "IAm". Y seleccionamos la primera opción que aparece de la siguiente manera.
  ![](https://cdn.discordapp.com/attachments/955522800918085686/1017552037979897886/unknown.png)

1. Nos dirigirá a una pantalla que lucirá de la siguiente manera.
  ![](https://cdn.discordapp.com/attachments/955522800918085686/1017552643813560370/unknown.png)

1. Seleccionamos la opción "Usuarios" y allí crearemos el(los) usuario(s) y sus credenciales.
  ![](https://cdn.discordapp.com/attachments/955522800918085686/1017553318979055746/unknown.png)

1. Damos click en "Agregar usuarios"
1. Colocamos el nombre del usuario.
1. Elegimos la primera opción de tipo de acceso, es decir, "Clave de acceso: acceso mediante programación". La pantalla lucirá de la siguiente forma.
  ![](https://cdn.discordapp.com/attachments/955522800918085686/1017554707033640980/unknown.png)
1. Luego damos click en "Siguiente: Permisos".

Como ejemplo, crearemos un administrador general para la plataforma, es decir, el usuario podrá tener acceso al 100% de los servicios que tiene AWS, cabe mencionar que también se pueden seleccionar solo alguno permisos, dependiendo de los requerimientos.
1. Crearemos un grupo, un grupo es un conjunto de usuarios que comparten los mismos accesos a AWS. Para ello dar click en "Crear grupo"
2. Escribir un nombre para el grupo, y seleccionar "AdministratorAccess". Lucirá de la siguiente manera.
  ![](https://cdn.discordapp.com/attachments/955522800918085686/1017556571263356948/unknown.png)
3. Finalmente, click en "Crear grupo".
4. En "Etiquetas" y en "Revisar", no colocamos nada.
5. EN la sección "Completar" veremos el "Access key ID" y el "Secret access key".
  ![](https://cdn.discordapp.com/attachments/955522800918085686/1017558453683765318/unknown.png)
  Copiamos cada credencial en una lugar de confianza a modo de respaldo, ya que al cerrar la ventana, no volveremos a ver esos accesos.

# Carga de datos DynamoDB 

## Crear tablas
1. Será necesario crear cada una de las siguientes tablas en la base de datos, en el servicio de DynamoDB.

    | Nombre                | Description | Descargable |
    | -----------           | ----------- | ----------- |
    | BigDataProcess        | -       | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/_SUCCESS) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/239ab4f2-510d-41bc-b20f-f8fa752c0745) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/66796a93-c086-49ef-b27d-b9fb06bac4b4) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/7596e887-fa89-477a-baf4-228c34bce8e9) - [Link5](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/9555fcf9-1623-4e5f-bf47-3090f5e4cca5) - [Link6](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/99bb1943-ef19-4e78-94b7-b6346f9a6526) - [Link7](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/b95987be-e705-4499-b062-977054e56d80) - [Link8](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/ea9efb30-055f-4b7e-aa31-4f6e0cb49ab4) - [Link9](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/f29fd4ab-3c6c-4dc6-bb4d-19c084d0d33c) - [Link10](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/BigDataProcess/2023-01-13-17-45-46/manifest)|
    | CalendlyNotifcation   | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/CalendlyNotifcation/2023-01-13-17-46-59/_SUCCESS) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/CalendlyNotifcation/2023-01-13-17-46-59/21d240d1-1ffc-4f0f-993a-ec19a7b9954e) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/CalendlyNotifcation/2023-01-13-17-46-59/71292149-a2df-4225-8ce1-2bd3721bb393) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/CalendlyNotifcation/2023-01-13-17-46-59/8cb2f416-903d-4452-a18a-f5df20bb72e3) - [Link5](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/CalendlyNotifcation/2023-01-13-17-46-59/manifest)        |
    | MessageNotifcation    | -        |  [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/MessageNotifcation/2023-01-13-17-46-23/_SUCCESS) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/MessageNotifcation/2023-01-13-17-46-23/1496ea6f-0241-4a8e-a88e-6999329ea26f) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/MessageNotifcation/2023-01-13-17-46-23/196c2d7b-ade2-4077-8568-c0e7ed7753be) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/MessageNotifcation/2023-01-13-17-46-23/1f488763-fd9e-4727-85cb-5e6b42b3dc87) - [Link5](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/MessageNotifcation/2023-01-13-17-46-23/f73f0a30-8eed-49f3-9965-a6b4b4376fcf) - [Link6](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/MessageNotifcation/2023-01-13-17-46-23/manifest)       |
    | pdfmanager            | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/pdfmanager/2023-01-13-17-30-51/_SUCCESS) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/pdfmanager/2023-01-13-17-30-51/d009e4e6-d745-44d5-b550-cbcde3a4503a) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/pdfmanager/2023-01-13-17-30-51/manifest)        |    
    | DownloadPdf            | -        |  - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/pdfmanager/2023-01-13-17-30-51/_SUCCESS) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/pdfmanager/2023-01-13-17-30-51/d009e4e6-d745-44d5-b550-cbcde3a4503a) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/ultimo_traspaso/pdfmanager/2023-01-13-17-30-51/manifest)      |

<!-- [Link1]() - [Link2]() - [Link3]() - [Link4]() - [Link5]() - [Link6]() - [Link7]() - [Link8]() - [Link9]() - [Link10]() -->

<!--     | Nombre                | Description |
    | -----------           | ----------- |
    | BigDataProcess        | -       |
    | CalendlyNotifcation   | -        |
    | MessageNotifcation    | -        |
    | pdfmanager            | -        |
    | DownloadPdf            | -        | -->
    NOTA: En una carpeta en S3, para cada tabla, subir los archivos descargables inicados como Link en la tabla.

1. La forma de importar los datos a la tabla será mediante Pipeline de AWS. La configuración general debe ser la siguiente, para cada tabla a importar:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1040720402604892251/unknown.png)
  En el "Input S3 folder" puse el directorio de la carpeta donde están todos los archivos con la data, claro que para eso, los archivos deberían haberse subido a una carpeta en S3:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1040720462205948054/unknown.png)

   
<!--     | Nombre                | Description | Descargable |
    | -----------           | ----------- | ----------- |
    | BigDataProcess        | -       | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/BigDataProcess/2022-09-09-20-23-41/3c5888cb-1873-441c-8545-529863560d3f) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/BigDataProcess/2022-09-09-20-23-41/49afcbdc-0d99-45c3-b699-a2121096c0b0) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/BigDataProcess/2022-09-09-20-23-41/c5678587-1164-4dee-9e5e-4beb6efdafc8) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/BigDataProcess/2022-09-09-20-23-41/e70351e5-a75e-48d4-aec5-8d497afb700c)|
    | CalendlyNotifcation   | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/CalendlyNotifcation/2022-09-09-20-37-50/5f17d09d-45e2-4773-9991-f5902d336637) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/CalendlyNotifcation/2022-09-09-20-37-50/6ac554b2-87b9-4926-a17c-28c541bb7f10) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/CalendlyNotifcation/2022-09-09-20-37-50/805d695e-415b-4ac7-875b-2db54a662c0e)        |
    | MessageNotifcation    | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/XXXX-XXXX-XXXXTest/2022-09-09-20-30-27/1c0bbe05-3449-4f3c-a5ed-0df985379c80) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/XXXX-XXXX-XXXXTest/2022-09-09-20-30-27/2559b389-2ac3-4f1d-bab5-cfce5132f265) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/XXXX-XXXX-XXXXTest/2022-09-09-20-30-27/43f35a73-b9ca-4a54-94f9-93d0dfa948c0) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/XXXX-XXXX-XXXXTest/2022-09-09-20-30-27/c2915a46-8b45-41cf-9626-183c7569c32e)        |
    | pdfmanager            | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/pdfmanager/2022-09-09-20-43-45/44c4d65d-826a-4ac5-aa1c-076c1409d69a)       |
 -->
### BigDataProcess
  Esta tabla contiene los siguientes campos:

  {% highlight sql %} 
  studentId (String)
  order (Number)
  createdAt (Timestamp)
  finalResult (Json)
  id (Timestamp)
  isActive (String)
  processedResult (Array)
  responseResult (Array)
  schoolAddress (String)
  schoolBusinessId (String)
  schoolCity (String)
  schoolCountry (String)
  schoolDistrict (String)
  schoolId (String)
  schoolLat (Number)
  schoolLog (Number)
  schoolMonthlyCost (Number)
  schoolName  (String)
  schoolProvince (String)
  sponsorId (String)
  state (Number)
  studentDocument (String)
  studentGender (String)
  studentGraduationYear (String)
  studentName (String)
  studentPhone (String)
  studentPhoneCode  (Number)
  studentSection (String)
  studentSurname (String)
  timestamps  (Number)
  vocationalGuidanceId  (String)
  {% endhighlight %}

  1. Información general:
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1018934546705690624/unknown.png)

  2. Índices
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1018935171656986776/unknown.png)

### CalendlyNotifcation
  Esta tabla contiene los siguientes campos:

  {% highlight sql %} 
  psycologyId (String)
  timestamp (Number)
  ?assigned_to (String)
  answer_1 (String)
  answer_2 (String)
  answer_3 (String)
  answer_4 (String)
  assigned_to (String)
  event_end_time (Date)
  event_start_time (Date)
  event_type_name  (String)
  event_type_uuid (String)
  invitee_email (String)
  invitee_first_name (String)
  invitee_last_name (String)
  invitee_uuid (String)
  psicologyName (String)
  text_reminder_number (String)
  {% endhighlight %}

  1. Información general:
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1018936912351875093/unknown.png)

### MessageNotifcation
  Esta tabla contiene los siguientes campos:

  {% highlight sql %} 
  studentId (String)
  timestamp (Number)
  institutionId (String)
  origin (String)
  phone (String)
  statusMessage (String)
  typeTest (String)
  url (String)
  {% endhighlight %}

  1. Información general:
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1018937164341456986/unknown.png)
  
  1. Descargables con data: [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/431d29a1-87d1-4957-81e0-6ffe796a137b) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/bb0d3814-3e71-4fee-9ff3-0c0a067cc64e) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/d6a118a6-1dd2-4201-99a5-1330c28c52cc) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/fb33fe43-0e55-4134-9b9d-72b96ad3368c) - [Link5](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/_SUCCESS) - [Link6](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/manifest)
### pdfmanager
  Esta tabla contiene los siguientes campos:

  {% highlight sql %} 
  studentId (String)
  order (String)
  groupId  (String)
  name  (String)
  psychologyId (String)
  status (Number)
  year  (Number)
  {% endhighlight %}

  1. Información general:
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1018937382248140861/unknown.png)

### DownloadPdf
  Esta tabla contiene los siguientes campos:

  {% highlight sql %} 
  studentId (String)
  order (String)
  groupId  (String)
  name  (String)
  psychologyId (String)
  status (Number)
  year  (Number)
  {% endhighlight %}

  1. Información general:
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/1066686580703633469/1073357414566469732/image.png)

<!-- Los pasos finales para importar los datos de a la cuenta amazon son;
1. Descargar los documentos de datos indicados en la tabla como "Link". La tabla que tenga más de dos o más descargables es por que se particionaron los datos almacenados para el tratamiento más ligero de los mismos.
1. Luego, se tendrán que cargar esos archivos al servicio S3 de AWS.
1. A partir de allí, se podrá importar los datos a DynamoDB mediante el servicio de PipeLine de AWS. También puede hacerlo siguiendo las instrucciones de [este video](https://youtu.be/orNOAw3cqts?t=570){:target="_blank"}.
 -->

  <!-- | XXXX-XXXX-XXXX           | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/431d29a1-87d1-4957-81e0-6ffe796a137b) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/bb0d3814-3e71-4fee-9ff3-0c0a067cc64e) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/d6a118a6-1dd2-4201-99a5-1330c28c52cc) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/MessageNotifcation/2022-09-09-20-40-51/fb33fe43-0e55-4134-9b9d-72b96ad3368c)       |
  | PruebaProcesos        | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/PruebaProcesos/2022-09-09-20-47-44/cb50a291-76f2-4afb-ac7b-107911250ecc)        |
  | TestManual            | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/TestManual/2022-09-09-20-46-06/3c684ab1-0cc3-41ae-8226-6d7d96962ab4) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/TestManual/2022-09-09-20-46-06/3fd7d3ef-921d-42f8-8a93-22a1734611b4) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/TestManual/2022-09-09-20-46-06/dc744388-b56d-41c6-88f4-ebf826a7abf3) - [Link4](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/TestManual/2022-09-09-20-46-06/dd4455f2-a3ba-4cef-bb01-e6b35855212e)       |
    | DownloadPdf           | -        | - [Link1](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/DownloadPdf/2022-09-09-20-39-24/43001615-e945-4fbf-9082-a7a87487f1fd) - [Link2](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/DownloadPdf/2022-09-09-20-39-24/8e7e18cc-324f-47e4-9501-169bb7e79c29) - [Link3](https://queestudiar.s3.us-west-2.amazonaws.com/copia_dynamo_export/DownloadPdf/2022-09-09-20-39-24/ac9fb953-3851-4442-8035-bb59ce6af095)        | 
 -->

# Bucket S3 
## Propiedades
1. La configuración de queestudiar será de acceso público.
1. Registro de acceso del servidor: Deshabilitada
1. Amazon EventBridge: Desactivado
1. Aceleración de transferencia: Deshabilitada
1. Bloqueo de objetos: Deshabilitada
1. Pago por solicitante: Deshabilitada
1. Alojamiento de sitios web estáticos: Deshabilitada

### Información general sobre el bucket
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1020407181536919642/unknown.png)


### Control de versiones de buckets
1. Control de versiones de buckets: Deshabilitada
1. Eliminación de Multi-Factor Authentication (MFA): Deshabilitada

### Cifrado predeterminado
1. Cifrado predeterminado: Deshabilitada


## Permisos
1. Información general sobre los permisos:  Acceso Público
1. Bloquear acceso público (configuración del bucket): Desactivado
1. Política de bucket: 

  {% highlight json %} 
  {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "1",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:ListBucket",
                "s3:PutObject",
                "s3:PutObjectAcl",
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::queestudiar",
                "arn:aws:s3:::queestudiar/*"
            ]
        },
        {
            "Sid": "AmazonML_s3:ListBucket",
            "Effect": "Allow",
            "Principal": {
                "Service": "machinelearning.amazonaws.com"
            },
            "Action": "s3:ListBucket",
            "Resource": "arn:aws:s3:::queestudiar",
            "Condition": {
                "StringLike": {
                    "s3:prefix": "personalidad.csv*"
                }
            }
        },
        {
            "Sid": "AmazonML_s3:GetObject",
            "Effect": "Allow",
            "Principal": {
                "Service": "machinelearning.amazonaws.com"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::queestudiar/personalidad.csv*"
        },
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::queestudiar/*"
        }
    ]
  }
  {% endhighlight %}

1. Lista de control de acceso (ACL)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1020411074283061299/unknown.png)

1. Uso compartido de recursos entre orígenes (CORS)

  {% highlight json %} 
    [
      {
          "AllowedHeaders": [
              "*"
          ],
          "AllowedMethods": [
              "GET",
              "HEAD"
          ],
          "AllowedOrigins": [
              "*"
          ],
          "ExposeHeaders": []
      }
    ]
  {% endhighlight %}

# POLÍTICAS DE ACCESO AWS

Las políticas acceso con las que cuenta la empresa son las siguientes:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/905940010019213402/1033049695293022319/unknown.png)

Cabe mensionar que las políticas de acceso mínimas son las que permiten realizar operaciones de lectura y escritura en los servicios de DynamoDB y S3.

<div markdown="span" class="alert alert-info" role="alert">
<i class="fa fa-info-circle"></i> <b>Nota:</b> Los permisos y políticas de acceso son determinadas por cada compañía limitando los mismos a lo relevante y necesario.
{{ include.content }}
</div>



# CONTROL DE MENSAJERÍA (TWILIO)

El control o límite mensajería está detallado en la tabla `BalanceNotification`
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085686/1030492521861759076/unknown.png)

  - En columna InstitutionId va el ID de la intitución (Instituto o Universidad emisor de mensajes).
  - En la columna messages va el número límite de mensajes que puede enviar una institución, se irá reduciendo conforme se vaya consumiendo.
  - En la columna messagesInit va el número de mensajes que ya se han enviado hasta la fecha.

En el proyecto de notificaciones, en el documento `SendMessageDynamoDb.ts`. en la función `async sendMessage(studentId, statusMessage, institutionId, typeTest, reference, message, phone)` valida que aún queden cupos en la base de datos.
La línea sombreada en la images es la que realiza la validavión. Si se desea quitar esa validación, solo se debe comentar esa condicional y dejar el contenido que tiene dentro.
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085686/1030496415035686952/unknown.png)
  
El mensaje predeterminado es el siguiente:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/905940010019213402/1030506759812550696/unknown.png)


Los mensajes de notificación están implementados en las aplicaciones de:
* Estudiantes WEB Premium
Puede modificar el mensaje en el documento: `src/orientacion/components/results/ResultCareers.vue` en la línea 962

* Estudiantes WEB Express
Puede modificar el mensaje en el documento: `/src/orientacion/components/my_vocation/InterestResultReference.vue` en la línea 693


