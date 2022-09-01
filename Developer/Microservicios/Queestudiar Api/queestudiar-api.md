---
layout: page
title: Queestudiar Api
permalink: /Queestudiar Api/
parent: Microservicios
grand_parent: Developer
nav_order: 0
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
    DB_NAME=qeestudiar_db
    DB_USER_NAME=jbmarflo
    DB_PASSWORD=f0und3r5$<>hfh48232jhdfjsh32
    DB_HOST=prodqueestudiar.c5wqshckxtah.us-west-2.rds.amazonaws.com

    MODEL_PATH=/core/domain/models
    TOKEN_SECRET=appkj55kjfglk4j5lkjfg$fgkj4{}[f]df
    WEB=https://queestudiar.la
    SERVICE_WEB=http://localhost:2300
    QUEESTUDIAR_ID=2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8


    # SUPLIERS SERVICES
    # usil
    USIL_AUTHORIZATION_VALUE=eShVmYq3t6w9y$B&E)H@McQfTjWnZr4u7x!A%C*F-JaNdRgUkXp2s5v8y/B?E(G+
    USIL_AUTHORIZATION_KEY=X-API-KEY
    USIL_SERVICE_WEB=https://paneldigital.usil.edu.pe

    # twilio
    TWILIO_ACCOUNT_SID=AC4d52aefe4a8f1a90303a44568867bf39
    TWILIO_AUTH_TOKEN=c269bb629eeb18fdd6d29a2b6a4ea795
    TWILIO_PHONE=+12029522287

    # activeCampaign
    COMPAIGN_AUTHORIZATION_VALUE=1014f73aedf1c6d4e34e74170127e8791aea3cb093879d6ca40946d3be05d85b873de714
    COMPAIGN_AUTHORIZATION_KEY=Api-Token
    COMPAIGN_SERVICE_WEB=https://lazarosmayra76669.api-us1.com

    # aws
    SNS_ACCESS_ID=AKIA5N2BE72V53GEQ44B
    SNS_SECRET_ACCESS_KEY=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
    SNS_REGION=us-west-2
    SES_ACCESS_ID=AKIA5N2BE72V4DRMRCVL
    SES_SECRET_ACCESS_KEY=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
    SES_REGION=us-west-2
    SES_EMAIL=admin@queestudiar.la

    # facebook
    FACEBOOK_SERVICE_WEB=https://graph.facebook.com

    # google
    GOOGLE_SERVICE_WEB=https://www.googleapis.com


    # PAYMENTS
    # mercadopago
    MERCADOPAGO_CLIENT_ID=7201972069293933
    MERCADOPAGO_CLIENT_SECRET=6C6CeiYZqYo7J6GEQLn8jJC16sx3Dn9o

{% endhighlight %}

<!--  -->

# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | -- |
| DB_NAME                     | qeestudiar_db           | -- |
| DB_USER_NAME                | jbmarflo                              | -- |
| DB_PASSWORD                 | f0und3r5$<>hfh48232jhdfjsh32                      | -- |
| DB_HOST                     | prodqueestudiar.c5wqshckxtah.us-west-2.rds.amazonaws.com         | -- |
| MODEL_PATH                  | /core/domain/models               | Ruta de la ubicación de los archivos modelo en este proyecto |
| TOKEN_SECRET                | appkj55kjfglk4j5lkjfg$fgkj4{}[f]df        | -- |
| WEB                     | https://queestudiar.la        | -- |
| SERVICE_WEB                | http://localhost:2300                 | -- |
| QUEESTUDIAR_ID                   | 2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8 | -- |
| USIL_AUTHORIZATION_VALUE                   | eShVmYq3t6w9y$B&E)H@McQfTjWnZr4u7x!A%C*F-JaNdRgUkXp2s5v8y/B?E(G+ | -- |
| USIL_AUTHORIZATION_KEY                   | X-API-KEY | -- |
| USIL_SERVICE_WEB                   | https://paneldigital.usil.edu.pe | -- |
| TWILIO_ACCOUNT_SID                   | AC4d52aefe4a8f1a90303a44568867bf39 | -- |
| TWILIO_AUTH_TOKEN                   | c269bb629eeb18fdd6d29a2b6a4ea795 | -- |
| TWILIO_PHONE                   | +12029522287 | -- |
| COMPAIGN_AUTHORIZATION_VALUE                   | 1014f73aedf1c6d4e34e74170127e8791aea3cb093879d6ca40946d3be05d85b873de714 | -- |
| COMPAIGN_AUTHORIZATION_KEY                   | Api-Token | -- |
| COMPAIGN_SERVICE_WEB                   | https://lazarosmayra76669.api-us1.com | -- |
| SNS_ACCESS_ID                   | AKIA5N2BE72V53GEQ44B | -- |
| SNS_SECRET_ACCESS_KEY                   | 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 | -- |
| SNS_REGION                   | us-west-2 | -- |
| SES_ACCESS_ID                   | AKIA5N2BE72V4DRMRCVL | -- |
| SES_SECRET_ACCESS_KEY                   | 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 | -- |
| SES_REGION                   | us-west-2 | -- |
| SES_EMAIL                   | admin@queestudiar.la | -- |
| FACEBOOK_SERVICE_WEB                   | https://graph.facebook.com | -- |
| GOOGLE_SERVICE_WEB                   | https://www.googleapis.com | -- |
| MERCADOPAGO_CLIENT_ID                   | 7201972069293933 | -- |
| MERCADOPAGO_CLIENT_SECRET                   | 6C6CeiYZqYo7J6GEQLn8jJC16sx3Dn9o | -- |

# CONSULTAS

## Loguin [POST]
La ruta en **producción** es la siguiente:
`https://service.qeestudiar.com/metric`


La ruta en **modo de desarollo** es la siguiente:
`http://localhost:2000/metric`

La notación para el acceso a cualquiera de las rutas será de la siguiente namera: `"{host}/"`

## Loguin [POST]
Ruta: `{host}/api/auth/login`

## Registro [POST]
Ruta: `{host}/api/auth/register`

## Verificar número de celular [POST]
Ruta: `{host}/api/auth/verify-number`

## Guardar contraseña [POST]
Ruta: `{host}/api/auth/recover`

## Extraer contraseña [GET]
Ruta: `{host}/api/auth/recover`

## Verificar contraseña [POST]
Ruta: `{host}/api/auth/recover/validate`

## Loguin social [POST]
Ruta: `{host}/api/auth/social/:social`

## Register V2 [POST]
Ruta: `{host}/api/v2/auth/register`

## Extraer atributos de un estudiante [GET]
Ruta: `{host}/api/student/attribute`

## Extraer carreras filtradas [GET]
Ruta: `{host}/api/student/careers-filter`

## Enroll [POST]
Ruta: `{host}/api/student/enroll`

## Enroll [GET]
Ruta: `{host}/api/student/enroll`

## Ectraer perfil de un estudiante [POST]
Ruta: `{host}/api/student/:studentId`

## Actualizar data de un estudiante [PUT]
Ruta: `{host}/api/student`

## Agregar atributo a un estudiante [POST]
Ruta: `{host}/api/student/:studentId/attribute`

## Extraer la guía vocacional [GET]
Ruta: `{host}/api/vocational`

## Extraer todos los atributos [GET]
Ruta: `{host}/api/vocational/personality/attribute`

## Buscar institución [GET]
Ruta: `{host}/api/vocational/professional`

## Extraer personalidad [GET]
Ruta: `{host}/api/vocational/personality/:type`

## Extraer inteligencia [GET]
Ruta: `{host}/api/vocational/intelligences`

## Extraer preguntas de personalidad [GET]
Ruta: `{host}/api/vocational/questions/personality`

## Extraer último resultado [GET]
Ruta: `{host}/api/vocational/last-result`

## Extraer último resultado de talento [GET]
Ruta: `{host}/api/vocational/last-result-talent`

## Extraer preguntas [GET]
Ruta: `{host}/api/vocational/questions/:vocationalId`

## Extraer resultados de progreso [GET]
Ruta: `{host}/api/vocational/progress/result`

## Actualizar referencia completa [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId/reference`

## Actualizar progreso vocacional complero [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId`

## Extraer datos personales de progreso institucional [GET]
Ruta: `{host}/api/vocational/progress/personality/:id`

## Extraer datos de progreso [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId/public`

## Extraer datos de progreso  personal[GET]
Ruta: `{host}/api/vocational/progress/:vocationalId`

## Extraer atributo vovacional [GET]
Ruta: `{host}/api/vocational/vocations-attributes`

## Extraer progreso [GET]
Ruta: `{host}/api/vocational/progress`

## Enviar información [POST]
Ruta: `{host}/api/membership/information`

## Activar membresías de escuelas [GET]
Ruta: `{host}/api/membership/school`

## Verificar código de colegio [GET]
Ruta: `{host}/api/membership/verification`

## Actualizar estudiante [POST]
Ruta: `{host}/api/data-update/student`

## Extraer lista [GET]
Ruta: `{host}/api/school`

## Validar alianza [GET]
Ruta: `{host}/api/school/alliance/:allianceId`

## Buscar estudiante [GET]
Ruta: `{host}/api/school/student`

## Configuraciónvocacional [PUT]
Ruta: `{host}/api/school/vocational/config`

## Extraer último resultado [GET]
Ruta: `{host}/api/school/vocational/last-result`

## Extraer dashborad de institución [GET]
Ruta: `{host}/api/school/dashboard/institution`

## Extraer dashboard de carreras [GET]
Ruta: `{host}/api/school/dashboard/career`

## Lista de usuarios [GET]
Ruta: `{host}/api/school/:id/user`

## Crear usuario [POST]
Ruta: `{host}/api/school/:id/user`

## Crear código de escuelas [POST]
Ruta: `{host}/api/school/:id/school-code`

## Buscar institución [GET]
Ruta: `{host}/api/institution`

## Buscar estudiante [GET]
Ruta: `{host}/api/institution/student`

## Extraer carreras de instituciones [GET]
Ruta: `{host}/api/sitemap/institution/careers`

## Extraer carreras [GET]
Ruta: `{host}/api/institution/careers`

## Actualizar institución [PUT]
Ruta: `{host}/api/institution`

## Agregar carreras [POST]
Ruta: `{host}/api/institution/career/:careerId`

## Actualizar carreras [PUT]
Ruta: `{host}/api/institution/career/:careerId`

## Borrar carreras [DELETE]
Ruta: `{host}/api/institution/career/:careerId`

## Extraer carreras [GET]
Ruta: `{host}/api/institution/career/:careerId`

## Agregar curriculum de carrera por institución [POST]
Ruta: `{host}/api/institution/career/:careerId/curriculum`

## Extraer curriculum de carrera por institución [GET]
Ruta: `{host}/api/institution/career/:careerId/curriculum`

## Eliminar curriculum de carrera [DELETE]
Ruta: `{host}/api/institution/career/:careerId/curriculum/:curriculumId`

## Agregar modalidad [POST]
Ruta: `{host}/api/institution/modality`

## Borrar modalidad [DELETE]
Ruta: `{host}/api/institution/modality/:modalityId`

## Borrar localización [GET]
Ruta: `{host}/api/institution/location/:locationId`

## Agregar localización [POST]
Ruta: `{host}/api/institution/location`

## Extraer inscripción [GET]
Ruta: `{host}/api/institution/leads`

## Exytaer inscrición a conferencia [GET]
Ruta: `{host}/api/institution/leads-conference`

## Extraer detalles de modalidad [GET]
Ruta: `{host}/api/institution/:username/modality/:id`

## Extraer perfil [GET]
Ruta: `{host}/api/institution/:username`

## Extraer localización [GET]
Ruta: `{host}/api/institution/:username/location`

## Extraer carreras [GET]
Ruta: `{host}/api/institution/:username/career`

## Extraer modalidad [GET]
Ruta: `{host}/api/institution/:username/modality`

## Extraer modalidad por id [GET]
Ruta: `{host}/api/institution/:username/career/:slug`

## Enviar notificaciones express [POST]
Ruta: `{host}/api/institution/notification/express`

## Enviar notificaciones SMS [POST]
Ruta: `{host}/api/institution/notification`

## Estado de las notificaciones [GET]
Ruta: `{host}/api/institution/status-notification/:referenceId`

## Validar código de teléfono [GET]
Ruta: `{host}/api/institution/notification/validate`

## Extraer todas las referencias [GET]
Ruta: `{host}/api/institution/notification/reference`

## Buscar carrera [GET]
Ruta: `{host}/api/career/search`

## Extraer instituciones [GET]
Ruta: `{host}/api/career/:slug`

## Extraer todas las carreras [GET]
Ruta: `{host}/api/career`

## Enviar notificación [GET]
Ruta: `{host}/api//cron/notification/phone`

## Scraping [GET]
Ruta: `{host}/api/cron/scrapping`

## Scrapping e-mail [GET]
Ruta: `{host}/api/cron/scrapping-email`

## Extraer referencia de precios [GET]
Ruta: `{host}/api/cron/update-price-reference`

## Pagar [POST]
Ruta: `{host}/api/payment`

## Procesar pago [PUT]
Ruta: `{host}/api/payment`

## Extraer progreso de un colegio [GET]
Ruta: `{host}/api/school/student/:studentId/vocational/progress/:vocationalId`

## Extraer preguntas de un colegio [GET]
Ruta: `{host}/api/school/student/:studentId/vocational/questions/:vocationalId`

## Extraer todo [GET]
Ruta: `{host}/api/conference`

## Inscribir a un estudiante [POST]
Ruta: `{host}/api/conference/student`

## Extraer usuario activo [POST]
Ruta: `{host}/api/mailing/activecampaign/blog`




# CRM Api

Para utilizar esta api se necesita la siguiente ruta:
  1. `/api/institution/notification/crm`

Y como unico dato de entrada se utilizará la autenticación del usuario.


## Test express
Para hacer un test express se necesita como datos de entrada:
  1. `institutionId`: (string)
  2. `referenceId`: (string)
  1. `notificationVerified`: (boolean)
  
Esos datos serán los argumentos de la función.
En primer lugar se verificará la existencia de la referencia pasada como argumento, si no existe se procederá a enviar un error en la consulta, si existe se procederá con el siguiente paso.
Si el `institutionId` enviado es de USIL o USIL Paraguay, se procederá con la elaboración del resultado y guardado de los datos en la tabla Reference. 

## Test premium

Para hacer un test express se necesita como datos de entrada:
  1. `auth`: (object)

Ese dato será el argumento del `sponsorId` que debe estar dentro del objeto de autenticación. El `sponsorId` es el ID de la institución, en este caso el único a ser tomado en cuenta será el ID de la USIL.

Si el `institutionId` enviado es de USIL, se procederá con la elaboración del resultado y guardado de los datos en la tabla Student. 

