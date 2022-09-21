---
layout: page
title: Queestudiar Notificaciones
permalink: /Queestudiar Notificaciones/
parent: Microservicios
grand_parent: Developer
nav_order: 5
---

<details open markdown="block">
  <summary>
    Índice:
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

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

El contenido de las variables de entorno se muestran a continuación:

{% highlight .env %}
  PORT=2000
MESSAGE=HelloWorldNow

# DATA BASE CONFIGS
DB_DIALECT=mysql
DB_NAME=XXXX-XXXX-XXXX
DB_USER_NAME=XXXX-XXXX-XXXX
DB_PASSWORD=XXXX-XXXX-XXXX
DB_HOST=XXXX-XXXX-XXXX

MODEL_PATH=/core/domain/models
TOKEN_SECRET=34534345345gdfg234234fd343
WEB=https://queestudiar.la
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
BYNAMO_BIG_DATA=XXXX-XXXX-XXXX

# twilio
TWILIO_SID=XXXX-XXXX-XXXX
TWILIO_TOKEN=XXXX-XXXX-XXXX

# PAYMENTS
# mercadopago
MERCADOPAGO_CLIENT_ID=XXXX-XXXX-XXXX
MERCADOPAGO_CLIENT_SECRET=XXXX-XXXX-XXXX




{% endhighlight %}

<!--  -->

# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | -- |
| DB_NAME                     | XXXX-XXXX-XXXX           | -- |
| DB_USER_NAME                | XXXX-XXXX-XXXX                              | -- |
| DB_PASSWORD                 | XXXX-XXXX-XXXX                      | -- |
| DB_HOST                     | XXXX-XXXX-XXXX         | -- |
| MODEL_PATH                  | /core/domain/models               | Ruta de la ubicación de los archivos modelo en este proyecto |
| TOKEN_SECRET                | 34534345345gdfg234234fd343        | -- |
| WEB                     | https://queestudiar.la        | -- |
| SERVICE_WEB                | https://service.qeestudiar.com                 | -- |
| QUEESTUDIAR_ID                   | XXXX-XXXX-XXXX | -- |
| CONFIG_ACCESS_KEY_ID                   | XXXX-XXXX-XXXX | -- |
| CONFIG_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | -- |
| CONFIG_REGION                   | us-west-2 | -- |
| DYNAMO_CHAT                   | XXXX-XXXX-XXXX | -- |
| DYNAMO_COMUNITY                   | XXXX-XXXX-XXXX | -- |
| BIG_DATA_PROCESS                   | XXXX-XXXX-XXXX | -- |
| TWILIO_SID | XXXX-XXXX-XXXX | -- |
| TWILIO_TOKEN |XXXX-XXXX-XXXX  | -- |
| MERCADOPAGO_CLIENT_ID                   | '' | -- |
| MERCADOPAGO_CLIENT_SECRET                   | '' | -- |

# Extraer calendario [POST]
Ruta: `{host}/notification/calendly`

# Crear tabla [POST]
Ruta: `{host}/notification/whatsapp/create-table`

# Enviar mensaje [POST]
Ruta: `{host}/notification/whatsapp/sendMessage'`

# Guardar balance [POST]
Ruta: `{host}/notification/whatsapp/set-balance`

# Recordatorio [POST]
Ruta: `{host}/notification/whatsapp/remember`

# Extraer data [POST]
Ruta: `{host}api/machine/getData`

# Extraer token [POST]
Ruta: `{host}/notification/calendly/token`

# Guardar calendario [POST]
Ruta: `{host}/notification/calendly/set-calendly`

# Guardar tabla [POST]
Ruta: `{host}/notification/calendly/create-table`
