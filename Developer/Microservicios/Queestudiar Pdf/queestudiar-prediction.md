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
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013791695671922810/unknown.png)
  1. Hacer conocer a Node JS la existencia las variables de entorno, esto se hace en el documento en el que se utilizarán las variables.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792240067420261/unknown.png)
  1. Ya podemos utilizar las variables de entorno en cualquier documento `.ts` o `.js`.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792103102423050/unknown.png)

El contenido de las variables de entorno se muestran a continuación:

{% highlight .env %}

PORT=2000
MESSAGE=HelloWorldNow

# DATA BASE CONFIGS
DB_DIALECT=mysql
DB_NAME=queestudiar_local
DB_USER_NAME=root
DB_PASSWORD=1234
DB_HOST=localhost

MODEL_PATH=/core/domain/models
TOKEN_SECRET=appkj55kjfglk4j5lkjfg$fgkj4{}[f]df
WEB=http://localhost:3000
SERVICE_WEB=https://service.qeestudiar.com
QUEESTUDIAR_ID=2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8



# SUPLIERS SERVICES
# aws
CONFIG_ACCESS_KEY_ID=AKIA5N2BE72V7ABXFZGD
CONFIG_SECRET_ACCESS_KEY=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
CONFIG_REGION=us-west-2

# dynamoDb
DYNAMO_CHAT=trasienteDB-dev
DYNAMO_COMUNITY=Community  

{% endhighlight %}

<!--  -->


# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | -- |
| DB_NAME                     | qeestudiar_db           | -- |
| DB_USER_NAME                | root                              | -- |
| DB_PASSWORD                 | 1234                      | -- |
| DB_HOST                     | prodqueestudiar.c5wqshckxtah.us-west-2.rds.amazonaws.com         | -- |
| MODEL_PATH                  | /core/domain/models               | Ruta de la ubicación de los archivos modelo en este proyecto |
| TOKEN_SECRET                | appkj55kjfglk4j5lkjfg$fgkj4{}[f]df        | -- |
| WEB                     | http://localhost:3000        | -- |
| SERVICE_WEB                | https://service.qeestudiar.com                 | -- |
| QUEESTUDIAR_ID                   | 2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8 | -- |
| CONFIG_ACCESS_KEY_ID                   | AKIA5N2BE72V7ABXFZGD | -- |
| CONFIG_SECRET_ACCESS_KEY                   | 6rUjt7FB1zhTs4rG16BhEXvypaTs9i85Zt5rMZ1JK | -- |
| CONFIG_REGION                   | us-west-2 | -- |
| DYNAMO_CHAT                   | trasienteDB-dev | -- |
| DYNAMO_COMUNITY                   | Community | -- |
| BIG_DATA_PROCESS                   | BigDataTest | -- |
| MERCADOPAGO_CLIENT_ID                   | '' | -- |
| MERCADOPAGO_CLIENT_SECRET                   | '' | -- |

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
