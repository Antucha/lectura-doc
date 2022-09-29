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

<!-- El contenido de las variables de entorno se muestran a continuación:

{% highlight .env %}
  PORT=2000

  # DATA BASE CONFIGS
  DB_DIALECT=mysql
  DB_NAME=XXXX-XXXX-XXXX
  DB_USER_NAME=XXXX-XXXX-XXXX
  DB_PASSWORD=XXXX-XXXX-XXXX
  DB_HOST=XXXX-XXXX-XXXX

  TOKEN_SECRET=34534345345gdfg234234fd343

  # SUPLIERS SERVICES
  # aws
  CONFIG_ACCESS_KEY_ID=XXXX-XXXX-XXXX
  CONFIG_SECRET_ACCESS_KEY=XXXX-XXXX-XXXX
  CONFIG_REGION=us-west-2

  # dynamoDb
  BYNAMO_BIG_DATA=BigDataTest

  # twilio
  TWILIO_SID=XXXX-XXXX-XXXX
  TWILIO_TOKEN=XXXX-XXXX-XXXX



{% endhighlight %}
 -->
<!--  -->

# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| PORT                  | 2500 (generalmente)                         | Puerto localhost en modo de dearrollo |
| DB_DIALECT                  | mysql                         | Motor de la base de datos utilizado |
| DB_NAME                     | XXXX-XXXX-XXXX           | Nombre de la base de datos |
| DB_USER_NAME                | XXXX-XXXX-XXXX                              | Nombre de usuario de BD |
| DB_PASSWORD                 | XXXX-XXXX-XXXX                      | Contraseña de la BD |
| DB_HOST                     | XXXX-XXXX-XXXX         | Host de la BD |
| CONFIG_ACCESS_KEY_ID                   | XXXX-XXXX-XXXX | AccessKeyId de AWS |
| CONFIG_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | SecretAccessKeyId de AWS |
| CONFIG_REGION                   | XXXX-XXXX-XXXX | Ubicación de servicio de AWS |
| URL_S3_PDF_SERVICE                   | https://queestudiar.s3-us-west-2.amazonaws.com/pdfs | Ubicación de la carpeta de pdfs en el servicio S3 de AWS, cambioa según la configuración del administrador. |
| URL_LINK_MESSAGE                   | "https://descubre.usil.edu.pe/test/que-estudiar-2021/registro.php?msg=ok&utm_term=Undefined&reference" | Link del servicio de mensajería de USIL |
| WSP_PHONE_DATA                   | 'whatsapp:+16013006718' | whatsapp para el envío de mensajería. |
| BIG_DATA_PROCESS                   | BigDataTest | Nombre de la tabla BigDataTest de DynamoDB |
| TWILIO_SID | AC36591f835de012f136676899aad5fe75 | Id del servicio de twilio |
| TWILIO_TOKEN |313d3fc537517e01e92331966f6a421d  | Token del servicio de twilio |

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
