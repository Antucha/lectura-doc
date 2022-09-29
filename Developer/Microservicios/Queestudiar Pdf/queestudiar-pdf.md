---
layout: page
title: Queestudiar Pdf
permalink: /Queestudiar Pdf/
parent: Microservicios
grand_parent: Developer
nav_order: 2
---

<details open markdown="block">
  <summary>
    Índice:
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

<!--  -->
# Cuadro informativo

| Tecnología      | Valor |
| ----------- | ----------- |
| Tecnología principal      | Node JS      |
| Framewok   | Express        |
| Documentos de trabajo | Typescript |

# Declaración de las variables de entorno
Las variaibles de entorno se encuentran en los documentos "`.env`". Para que funcionen en un entorno back-end en Node JS se debe seguien el siguiente procedimiento:
  1. Declarar las variables en el documento `.env`
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1022156594936565811/unknown.png)
  1. Hacer conocer a Node JS la existencia las variables de entorno, esto se hace en el documento en el que se utilizarán las variables.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792240067420261/unknown.png)
  1. Ya podemos utilizar las variables de entorno en cualquier documento `.ts` o `.js`.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792103102423050/unknown.png)

<!-- El contenido de las variables de entorno se muestran a continuación:

{% highlight .env %}

PORT=2000
MESSAGE=HelloWorldNow

# DATA BASE CONFIGS
DB_DIALECT=mysql
DB_NAME=XXXX-XXXX-XXXX
DB_USER_NAME=XXXX-XXXX-XXXX
DB_PASSWORD=XXXX-XXXX-XXXX
DB_HOST=localhost

MODEL_PATH=/core/domain/models
TOKEN_SECRET=XXXX-XXXX-XXXX
WEB=http://localhost:3000
SERVICE_WEB=https://service.qeestudiar.com
QUEESTUDIAR_ID=XXXX-XXXX-XXXX



# SUPLIERS SERVICES
# aws
CONFIG_ACCESS_KEY_ID=XXXX-XXXX-XXXX
CONFIG_SECRET_ACCESS_KEY=XXXX-XXXX-XXXX
CONFIG_REGION=us-west-2

# dynamoDb
DYNAMO_CHAT=XXXX-XXXX-XXXX
DYNAMO_COMUNITY=XXXX-XXXX-XXXX  

{% endhighlight %}

 -->


# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | Motor de la base de datos utilizado |
| DB_NAME                     | XXXX-XXXX-XXXX           | Nombre de la base de datos |
| DB_USER_NAME                | XXXX-XXXX-XXXX                              | Nombre de usuario de BD |
| DB_PASSWORD                 | XXXX-XXXX-XXXX                      | Contraseña de la BD |
| DB_HOST                     | XXXX-XXXX-XXXX         | Host de la BD |
| CONFIG_ACCESS_KEY_ID                   | XXXX-XXXX-XXXX | AccessKeyId de AWS |
| CONFIG_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | SecretAccessKeyId de AWS |
| CONFIG_REGION                   | XXXX-XXXX-XXXX | Ubicación de servicio de AWS |
| DYNAMO_CHAT                   | trasienteDB-dev | Nombre de la tabla trasienteDB-dev de DynamoDB  |
| DYNAMO_COMUNITY                   | Community | Nombre de la tabla Community de DynamoDB |

# Crear pdf [POST]
Ruta: `{host}/api/pdf/create`

# Crear QUEUE [POST]
Ruta: `{host}/api/pdf/create-queue`

# Enlistar QUEUE [POST]
Ruta: `{host}/api/pdf/list-queue`

# Enviar mensaje QUEUE [POST]
Ruta: `{host}/api/pdf/send-queue`

# Extraer documento existente [POST]
Ruta: `{host}/api/pdf/exist`

# Crear tabla [POST]
Ruta: `{host}/api/pdf/create-table`

# Extraer estado de descarga [POST]
Ruta: `{host}/api/pdf/download-status`
