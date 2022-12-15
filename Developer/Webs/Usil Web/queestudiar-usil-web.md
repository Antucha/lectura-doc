---
layout: page
title: Usil Web
permalink: /Usil Web/
parent: Webs
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
| SESSION_URL                  | .queestudiar.la                       | Nombre del dominio donde se guardará la sesión iniciada. |
| SCHOOL_PLATFORM_URL                  | <http://queestudiar-colegio-web-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com>                      | URL de la plataforma de colegio |
| BASE_URL_METRIC                  | <http://queestudiar-metricas-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com>                      | URL de la api de métricas |
| BASE_URL                     | https://service.qeestudiar.com        | Link del servicio a consumir en esta web |
| BASE_URL_LOCAL                | http://localhost:2000                 | Link en ambiente local |
| S3_BUCKET_URL                   | https://usil-queestudiar.s3.amazonaws.com | url del bucket de s3 |
| PORT                   | 5000 | Puerto de exposición |

