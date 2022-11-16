---
layout: page
title: Estudiante Web
permalink: /Estudiante Web/
parent: Webs
grand_parent: Developer
nav_order: 1
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

# CUADRO INFORMTIVO

| Tecnología      | Valor |
| ----------- | ----------- |
| Tecnología principal      | Vue Js       |
| Framewok   | Nuxt JS        |
| Documentos de estilo | CSS, scss, sass, stylus |

# Declaración de las variables de entorno
Las variaibles de entorno se encuentran en los documentos "`.env`". Para que funcionen en un entorno front-end en Nuxt JS se debe seguien el siguiente procedimiento:
  1. Declarar las variables en el documento `.env`
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013780078934642708/unknown.png)
  1. Hacer conocer a Nuxt JS la existencia de las variables, esto se hace en el documento `nuxt.config.js`
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013781170686791701/unknown.png)
  1. Ya podemos utilizar las variables de entorno en cualquier documento `.vue` o `.js`.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013781700922327150/unknown.png)

# VARIALES DE ENTORNO

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| LOGIN_SESSION                | us-east-1.elasticbeanstalk.com       | Nombre de la variable de sesión almacenada como cookie |
| LOGIN_SESSION_WITH_AUTH            | auth.userSession                      | Variable de la sesión iniciada (estático) |
| REDIRECT_SESSION           | redirectSession                     | Variable para redirigir sesión (estático)|
| AUTH_REDIRECT_SESSION | auth.redirectSession           | Variable se redirección a autenticación |
| TRACKING_CAMPAIGN                  | trackingCampaign                       | Nombre del dominio donde se guardará la sesión iniciada. |
| SEARCH_SESSION_MAIN                         | searchSessionMain           | Variable para buscar la sesión inicial. |
| INSTITUTIONS_SELECTED_SESSION                      | institutionsSelectedSession               | Iformación de la institución del lestudiante. |
| URL_MODAL_SESSION                  | urlModal        | URL_MODAL_SESSION |
| URL                     | https://blog.queestudiar.la       | Link de la landing del blog |
| URL_WEB                | https://queestudiar.la/                 | Link en ambiente de producción |
| BASE_URL_DEV                   | http://queestudiar-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com | Url de la api principal en modo de desarrollo |
| BASE_URL                   | http://queestudiar-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com | Url de la api principal |
| BASE_URL_METRIC                   | http://queestudiar-metricas-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com | Url de la api de métricas |
| BASE_URL_PDF                   | http://queestudiar-generador-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com | Url de la api generador de PDF|
| BASE_URL_NOTIFICATION                   | http://queestudiar-notificacion-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com | Url de la api de notificaciones|
| BASE_URL_LOCAL                   | http://localhost:5000 | Url de la api principal en local |
| ASSETS_URL                   | https://d10kixcrv010ns.cloudfront.net | Url de los assest|
| S3_BUCKET_URL                   | https://usil-queestudiar.s3.amazonaws.com | Url de los assest|


# ACCIONES NECESARIAS

Como el proyecto requiere de recursos del bucket de S3, se tendrá que cambiar la ruta de todos los lugares en donce se utilicen estor recursos, para ello, en el editor de código que utilice, copiar el texto `https://queestudiar.s3.us-west-2` en el buscador, de la siguiente manera:

  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1041743059211268146/image.png)

Y en el segundo casillero, reemplasar por la url del bucket propio de queestudiar en USIL: 

  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1041743499126648902/image.png)

Y finalmente dar click en el botón de "Replace all":

  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1041743856108060832/image.png)

Eso remplazará todas las url del bucket de la empresa queestudiar por el link del bucket que USIL asignó al proyecto de queestudiar en su cuenta de AWS.
