---
layout: page
title: Colegio Web
permalink: /Colegio Web/
parent: Webs
grand_parent: Developer
nav_order: 2
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
| SESSION_URL                  | .queestudiar.pe                       | Nombre del dominio donde se guardará la sesión iniciada. (Cambiará según el deploy de USIL)|
| URL                         | https://school.queestudiar.pe           | URL de la web creada. (Cambiará según el deploy de USIL) |
| BASE_URL                     | http://queestudiar-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com      | Link del servicio a consumir en esta web. (Link de la API Principal) |
| BASE_URL_METRIC                     | http://queestudiar-metricas-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com     | Link de la API de métricas |
| BASE_URL_PDF                     | http://queestudiar-generador-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com      | Link de la API de generador de PDF |
| BASE_URL_LOCAL                | http://localhost:5000                 | Link de API en ambiente local |
| ASSETS_URL                   | https://d10kixcrv010ns.cloudfront.net | -- |
| PORT                   | 3500 | -- |
| S3_BUCKET_URL                   | https://usil-queestudiar.s3.amazonaws.com | url del bucket de s3 |


