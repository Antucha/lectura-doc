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
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1022156594936565811/unknown.png)
  1. Hacer conocer a Node JS la existencia las variables de entorno, esto se hace en el documento en el que se utilizarán las variables.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792240067420261/unknown.png)
  1. Ya podemos utilizar las variables de entorno en cualquier documento `.ts` o `.js`.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792103102423050/unknown.png)
<!-- 
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
    TOKEN_SECRET=XXXX-XXXX-XXXX
    WEB=https://queestudiar.la
    SERVICE_WEB=http://localhost:2300
    QUEESTUDIAR_ID=XXXX-XXXX-XXXX


    # SUPLIERS SERVICES
    # usil
    USIL_AUTHORIZATION_VALUE=eShVmYq3t6w9y$B&E)H@McQfTjWnZr4u7x!A%C*F-JaNdRgUkXp2s5v8y/B?E(G+
    USIL_AUTHORIZATION_KEY=X-API-KEY
    USIL_SERVICE_WEB=https://paneldigital.usil.edu.pe

    # twilio
    TWILIO_ACCOUNT_SID=XXXX-XXXX-XXXX
    TWILIO_AUTH_TOKEN=XXXX-XXXX-XXXX
    TWILIO_PHONE=XXXX-XXXX-XXXX

    # activeCampaign
    COMPAIGN_AUTHORIZATION_VALUE=1014f73aedf1c6d4e34e74170127e8791aea3cb093879d6ca40946d3be05d85b873de714
    COMPAIGN_AUTHORIZATION_KEY=Api-Token
    COMPAIGN_SERVICE_WEB=https://lazarosmayra76669.api-us1.com

    # aws
    SNS_ACCESS_ID=XXXX-XXXX-XXXX
    SNS_SECRET_ACCESS_KEY=XXXX-XXXX-XXXX
    SNS_REGION=us-west-2
    SES_ACCESS_ID=XXXX-XXXX-XXXX
    SES_SECRET_ACCESS_KEY=XXXX-XXXX-XXXX
    SES_REGION=us-west-2
    SES_EMAIL=admin@queestudiar.la

    # facebook
    FACEBOOK_SERVICE_WEB=https://graph.facebook.com

    # google
    GOOGLE_SERVICE_WEB=https://www.googleapis.com


    # PAYMENTS
    # mercadopago
    MERCADOPAGO_CLIENT_ID=XXXX-XXXX-XXXX
    MERCADOPAGO_CLIENT_SECRET=XXXX-XXXX-XXXX

{% endhighlight %}
 -->
<!--  -->

# Variables de entorno

## Variables de entorno del sistema queestudiar

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | Motor de la base de datos utilizado |
| DB_NAME                     | XXXX-XXXX-XXXX           | Nombre de la base de datos |
| DB_USER_NAME                | XXXX-XXXX-XXXX                              | Nombre de usuario de BD |
| DB_PASSWORD                 | XXXX-XXXX-XXXX                      | Contraseña de la BD |
| DB_HOST                     | XXXX-XXXX-XXXX         | Host de la BD |
| MODEL_PATH                  | /core/domain/models               | Ruta de la ubicación de los archivos modelo en este proyecto |
| TOKEN_SECRET                | appkj55kjfglk4j5lkjfg$fgkj4{}[f]df        | Código de JWT |
| WEB                     | https://queestudiar.la  (Dependiendo de la url actual de la web)       | Web de queestudiar |
| SERVICE_WEB                | http://localhost:2300 (dependendo de la url local)                 | URL localhost |
| QUEESTUDIAR_ID                   | 2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8 | ID de configuración de queestudiar |
| TWILIO_ACCOUNT_SID                   | XXXX-XXXX-XXXX | SID del servicio de Twilio |
| TWILIO_AUTH_TOKEN                   | XXXX-XXXX-XXXX | Token del servicio de Twilio|
| TWILIO_PHONE                   | XXXX-XXXX-XXXX | Teléfono del servicio de Twilio |
| COMPAIGN_AUTHORIZATION_VALUE                   | 1014f73aedf1c6d4e34e74170127e8791aea3cb093879d6ca40946d3be05d85b873de714 | -- |
| COMPAIGN_AUTHORIZATION_KEY                   | Api-Token | -- |
| COMPAIGN_SERVICE_WEB                   | https://lazarosmayra76669.api-us1.com | -- |
| SNS_ACCESS_ID                   | XXXX-XXXX-XXXX | Configuración SNS de AWS |
| SNS_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | Configuración SNS de AWS |
| SNS_REGION                   | us-west-2 | Configuración SNS de AWS |
| SES_ACCESS_ID                   | XXXX-XXXX-XXXX | Configuración SES de AWS |
| SES_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | Configuración SES de AWS |
| SES_REGION                   | us-west-2 | Configuración SES de AWS |
| SES_EMAIL                   | admin@queestudiar.la | Configuración SES de AWS |
| MERCADOPAGO_CLIENT_ID                   | XXXX-XXXX-XXXX | Configuración de acceso a mercadopago |
| MERCADOPAGO_CLIENT_SECRET                   | XXXX-XXXX-XXXX | Configuración de acceso a mercadopago |


## Variables de entorno para el CRM con USIL

### Variables de entorno para el CRM con TEST EXPRESS

| Variables                   | Valor                                 |
| -----------                 | -----------                           |
| ID_CAMPANA_CRM_EXPRESS_USIL                  | 625                         |
| HUB_CPROGRAMA_CRM_EXPRESS_USIL                  | 1                         |
| INTEGRACION_CRM_EXPRESS_USIL                  | 1                         |
| CAMPO_2_CRM_EXPRESS_USIL                  | 1337                         |
| CAMPO_3_CRM_EXPRESS_USIL                  | TTCP-1                         |
| CAMPO_4_CRM_EXPRESS_USIL                  | 'TCP pauta'                         |
| DOWNLOADED_CRM_EXPRESS_USIL                  | 0                         |
| TEXTO_2_CRM_EXPRESS_USIL                  | confirmado                         |
| VERIFIED_PHONE_CRM_EXPRESS_USIL                  | 1                         |
| REFERENCE_STATE_CRM_EXPRESS_USIL                  | 1                         |

### Variables de entorno para el CRM con TEST EXPRESS con USIL PARAGUAY

| Variables                   | Valor                                 |
| -----------                 | -----------                           |
| ID_CAMPANA_CRM_EXPRESS_USIL_PARAGUAY                  | 849                         |
| HUB_CPROGRAMA_CRM_EXPRESS_USIL_PARAGUAY                  | 243                         |
| INTEGRACION_HUB_CRM_EXPRESS_USIL_PARAGUAY                  | 1                         |
| INTEGRACION_CRM_EXPRESS_USIL_PARAGUAY                  | 1                         |
| CAMPO_2_CRM_EXPRESS_USIL_PARAGUAY                  | ''                         |
| CAMPO_3_CRM_EXPRESS_USIL_PARAGUAY                  | ''                         |
| CAMPO_4_CRM_EXPRESS_USIL_PARAGUAY                  | ''                         |
| DOWNLOADED_CRM_EXPRESS_USIL_PARAGUAY                  | 0                         |
| TEXTO_2_CRM_EXPRESS_USIL_PARAGUAY                  | confirmado                         |
| VERIFIED_PHONE_CRM_EXPRESS_USIL_PARAGUAY                  | 1                         |
| REFERENCE_STATE_CRM_EXPRESS_USIL_PARAGUAY                  | 1                         |

### Variables de entorno para el CRM con TEST PREMIUM 

| Variables                   | Valor                                 |
| -----------                 | -----------                           |
| ID_CAMPANA_CRM_PREMIUM_USIL                  | 683                         |
| INSTITUCION_PROCEDENCIA_CAMPANA_CRM_USIL                  | QUEESTUDIAR                         |
| HUB_CPROGRAMA_CRM_PREMIUM_USIL                  | 1                         |
| INTEGRACION_CRM_PREMIUM_USIL                  | 1                         |
| TEXTO_2_CRM_PREMIUM_USIL                  | ''                         |
| CAMPO_2_CRM_PREMIUM_USIL                  | 1285                         |
| CAMPO_3_CRM_PREMIUM_USIL                  | 'TQE Colegios 2022-01'                         |
| CAMPO_4_CRM_PREMIUM_USIL                  | 'QE Colegios 2022'                         |
| DOWNLOADED_CRM_PREMIUM_USIL                  | 0                         |
| UTM_CONTENT_CRM_COMPLETED                  | TEST-COMPLETADO                         |
| UTM_CONTENT_CRM_INCOMPLETED                  | TEST-INCOMPLETO                         |

### Variables de entorno para el CRM con TEST PREMIUM 

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| USIL_AUTHORIZATION_VALUE                   | eShVmYq3t6w9y$B&E)H@McQfTjWnZr4u7x!A%C*F-JaNdRgUkXp2s5v8y/B?E(G+ | Valor de configuración con USIL para conectarse al CRM Dynamics y envía resultado de OV Premium y Test Express - por confirmar con Juan Sandoval. |
| USIL_AUTHORIZATION_KEY                   | X-API-KEY | Valor de configuración con USIL para conectarse al CRM Dynamics y envía resultado de OV Premium y Test Express - por confirmar con Juan Sandoval. |
| USIL_SERVICE_WEB                   | https://paneldigital.usil.edu.pe | Valor de configuración con USIL para conectarse al CRM Dynamics y envía resultado de OV Premium y Test Express - por confirmar con Juan Sandoval. |
## Documentos relacionados al CRM

El documento que utiliza estas variables es el siguiente.
* `NotificationResultService.ts`;


# CONSULTAS

**Base Url:** http://queestudiar-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com

## Loguin [POST]
Ruta: `{host}/api/auth/login`

Auth required : NO

Permissions required : None
### Request
**type: body**

{% highlight json %}
  {
    "user": "Janeexample.com",
    "password": "123456",
    "role": "user",
    "id": "213"
  }
{% endhighlight %}
## Registro [POST]
Ruta: `{host}/api/auth/register`

Auth required : NO

Permissions required : None
### Request
**type: body**

{% highlight json %}
  {
    "user": "Janeexample.com",
    "password": "123456",
    "role": "user",
    "id": "213",
    "name": "Rosa",
    "surname": "Merino",
    "graduationYear": 2023,
    "gender": "M",
    "payedCareer": "Yo mismo",
    "whereStudy": "",
    "email": "rosa.merino@ezample.com",
    "allianceId": "123564",
    "surnameFather": "Merino",
    "surnameMother": "Salas",
    "day": "01",
    "month": "02",
    "year": "2023",
    "grade": "5",
    "section": "A1",
    "email": "alumno@exaple.com",
    "schoolId": "fds13-fgfsd-321fd",
    "code": "214562",
    "campaign": "",
    "studentType": "",
    "document": "79581635",
  }
{% endhighlight %}

## Verificar número de celular [POST]
Route: `{host}/api/auth/verify-number`

Auth required: NO

Permissions required: None

### Request
**Type: Body**

{% highlight json %}
{
    "user": "Janeexample.com",
}
{% endhighlight %}

## Guardar contraseña [POST]
Route: `{host}/api/auth/recover`

Auth required: NO

Permissions required: None

### Request
**Type: Body**

{% highlight json %}
{
    "email": "jane.example@gmail.com",
}
{% endhighlight %}
## Extraer contraseña [GET]
Route: `{host}/api/auth/recover`

Auth required: NO

Permissions required: None

### Request
**Type: Query**

{% highlight json %}
{
    "token": "somerandomtoken123",
}
{% endhighlight %}
## Verificar contraseña [POST]
Route: `{host}/api/auth/recover/validate`

Auth required: NO

Permissions required: None

### Request
**Type: Body**

{% highlight json %}
{
    "password": "newpassword",
    "token": "somerandomtoken123",
}
{% endhighlight %}

## Register V2 [POST]
Route: `{host}/api/v2/auth/register`

Auth required: NO

Permissions required: None

### Request
**Type: Body**

{% highlight json %}
{
    "user": "Janeexample.com",
    "password": "123456",
    "role": "user",
    "name": "Rosa",
    "surname": "Merino",
    "graduationYear": 2023,
    "gender": "M",
    "payedCareer": "Yo mismo",
    "whereStudy": "",
    "email": "rosa.merino@ezample.com",
    "lat": "-34.603722",
    "lng": "-58.381592",
    "country":"Argentina",
    "city":"Buenos Aires",
    "route":"Avenida de Mayo",
    "streetNumber":"1300",
    "formattedAddress":"Avenida de Mayo 1300, Buenos Aires, Argentina",
    "rangePrice":"$20000 - $30000",
    "careers":"Informatica, Matematica",
    "campaign":"",
    "studentType":"",
    "objective":"",
    "allianceId": "123564",
    "schoolId":"fds13-fgfsd-321fd"
}
{% endhighlight %}
## Extraer atributos de un estudiante [GET]
Route: `{host}/api/student/attribute`

Auth required: YES

Permissions required: None

### Request
**Type: Query**

{% highlight json %}
{
    "vocationalGuidanceId": "123456789"
}
{% endhighlight %}

### Headers

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

## Extraer carreras filtradas [GET]
Route: `{host}/api/student/careers-filter`

Auth required: YES

Permissions required: None

### Request
**Type: None**

### Headers

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

## Enroll [POST]
Route: `{host}/api/student/enroll`

Auth required: YES

Permissions required: None

### Request
**Type: Body**

{% highlight json %}
{
    "careerId":"123456",
    "institutionId":"789012",
    "action":"enroll"
}
{% endhighlight %}

### Headers

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

## Enroll [GET]
Route: `{host}/api/student/enroll`

Auth required: YES

Permissions required: None

### Request
**Type: Query**

{% highlight json %}
{
    "careerId":"123456",
    "institutionId":"789012"
}
{% endhighlight %}

### Headers

| header key                   | header value                                | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

## Ectraer perfil de un estudiante [POST]
Route: `{host}/api/student/:studentId`

Auth required: Optional

Permissions required: None

### Request
**Type: Param**

{% highlight json %}
{
    "studentId": "123456"
}
{% endhighlight %}

### Headers

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses (Optional) |

## Actualizar data de un estudiante [PUT]
Route: `{host}/api/student`

Auth required: YES

Permissions required: None

### Request
**Type: Body**

{% highlight json %}
{
    "name": "John",
    "surname": "Doe",
    "email": "johndoe@example.com",
    "role": "student",
    "password": "123456",
    "phone": "1234567890",
    "gender": "M",
    "type": "",
    "payedInstitution": "",
    "whereStudy": "",
    "rangePrice": "",
    "graduationYear": "",
    "career": ""
}
{% endhighlight %}

### Headers

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

## Agregar atributo a un estudiante [POST]
Route: `{host}/api/student/:studentId/attribute`

Auth required: YES

Permissions required: None

### Request

{% highlight json %}
{
    "name": "attributes",
    "attributes": [
        "attribute1",
        "attribute2"
    ],
    "careers": [
        "career1",
        "career2"
    ],
    "careersNot": [
        "career3",
        "career4"
    ],
    "vocationalGuidanceId":"123456789"
}
{% endhighlight %}

## Extraer perfil de estudiante [GET]
Route: `{host}/api/student`

Auth required: YES

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

Permissions required: None

### Request
**Type: Query**

{% highlight json %}
{
    "studentId": "123456789"
}
{% endhighlight %}

## Guardar carreras de preferencia [POST]
Route: `{host}/api/student/preference-career/:studentId`

Auth required: YES

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

Permissions required: None

### Request
**Type: Query**

{% highlight json %}
{
"careers": [
    {
    "careerId": "123456789",
    "isPreferred": true
    },
    {
    "careerId": "987654321",
    "isPreferred": false
    }
  ]
}
{% endhighlight %}

## Extraer la guía vocacional [GET]
Ruta: `{host}/api/vocational`

## Extraer todos los atributos [GET]
Ruta: `{host}/api/vocational/personality/attribute`

## Buscar institución [GET]
Ruta: `{host}/api/vocational/professional`

## Extraer personalidad [GET]
Ruta: `{host}/api/vocational/personality/:type`

Auth required: No
### Request
**Type: params**

{% highlight json %}
  {
    "type": "infj"
  }
{% endhighlight %}

1. `type`: Código del tipo de personalidad.

### Response

{% highlight json %}
{
    "code": 200,
    "message": "Se obtuvo la personalidad correctamente",
    "data": {
        "id": "10ab3dbd-6e39-4114-875f-acac87319104",
        "type": "infj",
        "description_type": "personality",
        "category": "diplomatic",
        "categoryEs": "Diplomático",
        "title": "El consejero",
        "image": "infj-advocate.svg",
        "description": "Estás motivado a hacer una diferencia positiva en el mundo. Deseas mejorar la vida de los demás, hasta es probable que luches por eso. Confías en tu fuerte intuición, funcionas mejor cuando tomas decisiones basadas en tu corazón en lugar de la lógica. Necesitas tiempo para que tu creatividad fluya libremente y te permita soñar en grande. Los rasgos idealistas que tiene tu personalidad pueden revelar tus altas expectativas tanto para ti mismo como para otros, lo que no siempre es útil.",
        "shortDescription": "Callados y místicos; sin embargo, inspiradores e idealistas incansables.",
        "characters": [
            {
                "name": "Martin Luther King",
                "movie": null,
                "image": "diplomats_INFJ_martin_luther_king.svg"
            }
        ],
        "attributes": [
            {
                "id": "04ecb349-ac6c-4c2c-ba6b-42f66053c5a7",
                "name": "Creativo"
            }
        ]
    }
}
{% endhighlight %}

1. `id`: Id de la personalidad.
2. `type`: Código de la personalidad.
3. `description_type`: El tipo de personalidad.
3. `category`: Categoría de la personalidad.
4. `categoryEs`: Categoría de la personalidad en español.
5. `title`: Título de la personalidad.
6. `image`: Imagen representativa de la personalidad.
7. `description`: Descripción de la personalidad.
8. `characters`: Lista de personalidades famosas con la misma personalidad.
9. `atributes`: Lista de atributos con de la personalidad.

## Extraer inteligencias [GET]
Ruta: `{host}/api/vocational/intelligences`

### Response
**Type: params**

{% highlight json %}
{
    "code": 200,
    "message": "Se obtuvo la lista de Inteligencias ",
    "data": {
        "descriptions": [
            {
                "id": "007dc673-60b1-446e-be0f-48ae1f4eba10",
                "type": "visual",
                "description_type": "intelligence",
                "category": "Inteligencia",
                "title": "Visual Espacial y Artístico",
                "image": "visual-intelligence.png",
                "description": "Presentas ideas en 3D. Observas el mundo y los objetos desde diferentes perspectivas. Posees la habilidad para manipular o crear imágenes mentales para resolver problemas, percibir detalles, dibujar o confeccionar esbozos y ver con precisión. Las personas que tienen tu inteligencia espacial suelen ser artistas, fotógrafos, arquitectos, diseñadores, publicistas o escultores.",
                "shortDescription": ""
            },
            {
                "id": "1de5aba0-c8c7-4e4a-b20e-239bd10b747a",
                "type": "people",
                "description_type": "intelligence",
                "category": "Inteligencia",
                "title": "Interpersonal",
                "image": "people-intelligence.png",
                "description": "Tienes la habilidad de llevarte bien o relacionarte con otras personas. La inteligencia interpersonal conlleva a interactuar con los demás de manera eficiente, porque eres capaz de entender, empatizar y comunicarte muy bien. Disciernes las emociones y las intenciones de los demás. Eso te permite interpretar las palabras y gestos o los objetivos y las metas de otras personas. Los políticos, los profesores o los actores son aventajados en este tipo de inteligencia.",
                "shortDescription": ""
            }
        ]
    }
}
{% endhighlight %}

1. `descriptions`: Lista de tipos de inteligencia.

## Extraer preguntas de personalidad [GET]
Ruta: `{host}/api/vocational/questions/personality`

### Response
**Type: params**

{% highlight json %}
{
    "code": 200,
    "message": "Se obtuvo la lista de Inteligencias ",
    "data": [
        {
            "id": "01081937-678f-11e9-82db-12136491b65a",
            "vocationalGuidanceId": "48e96300-adeb-48fa-b1d3-a221fc451ae3",
            "name": null,
            "itemJson": {
                "text1": "Hacer listas",
                "text2": "Dependo de mi memoria",
                "title": "En tus planes y diferentes actividades, ¿sueles hacer una lista o dependes de tu memoria?"
            },
            "description": null,
            "image": "free.png",
            "identifierValue": "Q1",
            "checked": false
        }
      ]
    }
}
{% endhighlight %}

1. La respuesta es una lista de las preguntas del módulo de personalidad.

## Extraer último resultado [GET]
Ruta: `{host}/api/vocational/last-result`

Auth required: YES

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

### Response
**Type: params**

{% highlight json %}
{
    "code": 200,
    "message": "Se obtuvo la informacion correctamente",
    "data": {
        "careerMatches": [
            {
                "career": "b6d959b7-99f8-4604-9418-3361bcb54387",
                "percentage": 12,
                "name": "sociología",
                "large_description": "Carrera donde se atiende a las experiencias de vida individuales para que, partiendo de lo unitario se llegue a una percepción colectiva de lo que sucede. Se brindan herramientas para que los procedimientos se lleven a cabo con la mayor objetividad posible. Interpretarás estadísticas y resultados de encuestas de opinión eficientemente. Necesitarás ser una persona investigadora, analítica, flexible."
            }
        ],
        "decisionTimeCareers": [
            {
                "title": "Tus Cualidades vs Carreras",
                "criteria_title": "Tus Cualidades",
                "type": "qualities",
                "description": "<ul><li>Creativo</li><li>Reflexivo</li><li>Leal</li><li>Principios firmes</li><li>Idealista</li></ul>",
                "career_name": "Cinematografía",
                "career_description": "<p><span >El estudiante se especializará en cinematografía, pero también te podrá innovar en lo narrativo, el desarrollo audiovisual y la producción de contenidos multi pantalla</span></p>",
                "career_id": "9191f6a7-9250-4cdd-8765-2844cccb1498",
                "score": 3,
                "final_score": 11,
                "color": "#7060f4",
                "is_evaluated": true,
                "criteria": [
                    {
                        "type": "vocation",
                        "score": 5
                    },
                    {
                        "type": "qualities",
                        "score": 3
                    },
                    {
                        "type": "abilities",
                        "score": 3
                    }
                ],
                "percentage": 55
            }
        ]
    }
}
{% endhighlight %}

1. `careerMatches`: Lista de carreras a las que el usuario es apto.
2. `decisionTimeCareers`: Lista de los resultados de la comparación entre las cualidades de el usuario con las carreras a las que es apto.


## Extraer último resultado de talento [GET]
Ruta: `{host}/api/vocational/last-result-talent`

## Extraer preguntas de una actividad vocacional [GET]
Ruta: `{host}/api/vocational/questions/:vocationalId`

### Request
**Type: params**

{% highlight json %}
  {
    "vocationalId": "s12a3-dsad21-dsa246"
  }
{% endhighlight %}
### Response

{% highlight json %}
{
    "code": 200,
    "message": "Se listo las preguntas correctamente",
    "data": [
        {
            "id": "11e66b6b-ad90-4eef-b99a-6838cc88861b",
            "vocationalGuidanceId": "3c38680d-7ce0-43ff-8179-4958b980e049",
            "name": "Ser reconocido por la gente",
            "itemJson": "Unexpected end of JSON input",
            "description": "Tener reconocimiento de la gente",
            "image": "reconocido.png",
            "identifierValue": null,
            "checked": false
        },
        {
            "id": "1711e74d-03c6-4bb9-aa04-5f0d1f0ef3bc",
            "vocationalGuidanceId": "3c38680d-7ce0-43ff-8179-4958b980e049",
            "name": "Anteponer mi vida personal a la profesional",
            "itemJson": "Unexpected end of JSON input",
            "description": null,
            "image": "life.png",
            "identifierValue": null,
            "checked": false
        }
      ]
    }
}
{% endhighlight %}

1. La respuesta es una lista de las preguntas de módulo que se pasa como ID.

## Extraer resultados de progreso [GET]
Ruta: `{host}/api/vocational/progress/result`

Auth required: YES

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

### Response

{% highlight json %}
{
    "code": 200,
    "message": "Se obtuvo la informacion correctamente",
    "data": {
        "6122993f-d1c6-4196-aaf0-00666f4ed686": {
            "result": null
        },
        "3c38680d-7ce0-43ff-8179-4958b980e049": {
            "result": [
                {
                    "id": "2063ab42-70ef-4e22-af47-e016a2e5453f",
                    "vocationalGuidanceId": "3c38680d-7ce0-43ff-8179-4958b980e049",
                    "name": "Trabajar al aire libre",
                    "itemJson": "Unexpected end of JSON input",
                    "description": null,
                    "image": "free.png",
                    "identifierValue": null,
                    "checked": false
                }
            ]
        },
        "48e96300-adeb-48fa-b1d3-a221fc451ae3": {
            "result": {
                "personalityType": "INFJ",
                "calculated": [
                    {
                        "score": 23,
                        "typeIndicator": "I",
                        "percentage": 6.25
                    }
                ]
            }
        }
      }
    }
}
{% endhighlight %}

1. La respuesta un obtejo que contiene como propiedades los ID de cada proceso vocacional, ellos, al mismo tiempo, son objetos conteniendo los resultados que obtuvo el estudiante en ese módulo, si no tiene resultados, el resultado será un `null`.

## Actualizar referencia completa [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId/reference`

## Extraer progreso vocacional completo [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId`

Auth required: YES

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

Permissions required: None

### Request
**Type: params**

{% highlight json %}
{
"vocationalId": "s12a3-dsad21-dsa246"
}
{% endhighlight %}

1. `type`: Id de la actividad a desarrollar.

### Response
**Type: params**

{% highlight json %}
{
{
    "code": 200,
    "message": "Se obtuvo la informacion correctamente",
    "data": {
        "id": "a4ffd190-f2f9-11ec-a20e-afaad72d1d5b",
        "studentId": "0e57a981-f2f8-11ec-ba79-ef794d69bf3c",
        "vocationalGuidanceId": "e8689d51-6802-4386-91eb-2dc98796e328",
        "responseResult": {
            "like": [
                {
                    "id": "c73c75fe-8d06-4197-8525-0d78ac933c6f",
                    "slug": "comunicacion-y-diseno-grafico",
                    "name": "Comunicación y diseño gráfico",
                    "description": "Carrera en la que aplicarás conocimientos de arte, comunicación y marketing para transmitir ideas que conecten con el público a través de texto e imágenes y con la ayuda de softwares y diversas técnicas. Necesitarás ser una persona creativa, detallista y estratega. ",
                    "like": true,
                    "curricula": [],
                    "suggestion": [],
                    "careerWorkfield": [
                        {
                            "id": "96bb0cec-80af-4d8c-a0d0-b256c6659990",
                            "careerId": "c73c75fe-8d06-4197-8525-0d78ac933c6f",
                            "name": "Consultoras de imagen y comunicación",
                            "image": null,
                            "description": "",
                            "createdAt": "2021-07-30T22:39:49.000Z"
                        }
                    ],
                    "careerSpecialties": [
                        {
                            "id": "792bce04-35a4-43c4-b064-9cb65e475754",
                            "careerId": "c73c75fe-8d06-4197-8525-0d78ac933c6f",
                            "name": "Periodismo",
                            "image": null,
                            "description": "",
                            "createdAt": "2021-07-30T22:37:39.000Z"
                        }
                    ],
                    "discardByPerson": false,
                    "notSuggestion": [],
                    "selected": true
                }
            ],
            "dislike": []
        },
        "processedResult": null,
        "finalResult": {
            "like": [
                {
                    "id": "c73c75fe-8d06-4197-8525-0d78ac933c6f",
                    "slug": "comunicacion-y-diseno-grafico",
                    "name": "Comunicación y diseño gráfico",
                    "description": "Carrera en la que aplicarás conocimientos de arte, comunicación y marketing para transmitir ideas que conecten con el público a través de texto e imágenes y con la ayuda de softwares y diversas técnicas. Necesitarás ser una persona creativa, detallista y estratega. ",
                    "like": true,
                    "curricula": [],
                    "suggestion": [],
                    "careerWorkfield": [
                        {
                            "id": "96bb0cec-80af-4d8c-a0d0-b256c6659990",
                            "careerId": "c73c75fe-8d06-4197-8525-0d78ac933c6f",
                            "name": "Consultoras de imagen y comunicación",
                            "image": null,
                            "description": "",
                            "createdAt": "2021-07-30T22:39:49.000Z"
                        }
                    ],
                    "careerSpecialties": [
                        {
                            "id": "792bce04-35a4-43c4-b064-9cb65e475754",
                            "careerId": "c73c75fe-8d06-4197-8525-0d78ac933c6f",
                            "name": "Periodismo",
                            "image": null,
                            "description": "",
                            "createdAt": "2021-07-30T22:37:39.000Z"
                        }
                    ],
                    "discardByPerson": false,
                    "notSuggestion": [],
                    "selected": true
                }
            ],
            "dislike": []
        },
        "state": "1",
        "createdAt": "2022-06-23T13:37:37.000Z"
    }
}
}
{% endhighlight %}

1. `id`: Id de la carrera
2. `studentId`: ID del estudiante
3. `vocationalGuidanceId`: ID de la actividad en desarrollo.
3. `responseResult`: La respuesta a la actividad realizada, en ese caso, una lista(arreglo) de las carreras seleccionadas por el estudiante. Las carreras están agrupadas en carreras que le gustaron(`like`) al estudiante y carreras que no le gustaron(`dislike`) al estudiante. Aquí se guarda la respuesta inicial del estudiante.
4. `finalResult`: Lista actualizada del `responseResult`.
5. `state`: estado del registro en BD.
6. `createdAt`: fecha de creación del registro en BD.


## Extraer datos personales de progreso institucional [GET]
Ruta: `{host}/api/vocational/progress/personality/:id`

## Extraer datos de progreso [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId/public`

## Actualizar respuestas para alguna actividad en específico datos de progreso  personal[PUT]
Ruta: `{host}/api/vocational/progress/:vocationalId`


Auth required: YES

| header key                   | header value	                                 | description |
| -----------                 | -----------                           | ----------- |
| Authorization                  | Bearer AKfycbyF7II                       | Seguridad con token de duración de 4 meses |

Permissions required: None

### Request
**Type: body**

{% highlight json %}
{
    "data":{
      "responseResult":[
         {
            "title":"Tus Cualidades vs Carreras",
            "criteria_title":"Tus Cualidades",
            "type":"qualities",
            "description":"<ul><li>Creativo</li><li>Reflexivo</li><li>Leal</li><li>Principios firmes</li><li>Idealista</li></ul>",
            "career_name":"Comunicación y diseño gráfico",
            "career_description":"Carrera en la que aplicarás conocimientos de arte, comunicación y marketing para transmitir ideas que conecten con el público a través de texto e imágenes y con la ayuda de softwares y diversas técnicas. Necesitarás ser una persona creativa, detallista y estratega. ",
            "career_id":"c73c75fe-8d06-4197-8525-0d78ac933c6f",
            "score":3,
            "final_score":0,
            "color":"#7060f4",
            "is_evaluated":true
         }
      ],
      "finalAnsware":true
   }
}
{% endhighlight %}

1. `responseResult`: Una lista de carreras que se necesita actualizar.

### Response
**Type: params**

{% highlight json %}
  {
    "code": 200,
    "message": "Se coloco tu respuesta correctamente"
  }
{% endhighlight %}

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

