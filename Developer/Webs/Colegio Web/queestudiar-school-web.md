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
| LOGIN_SESSION                | schoolSession                           | NOmbre de la variable de la sesión como cookie |
| sessionUrl                  | .queestudiar.pe                       | Nombre del dominio donde se guardará la sesión iniciada. (Cambiará según el deploy de USIL)|
| url                         | https://school.queestudiar.pe           | URL de la web creada. (Cambiará según el deploy de USIL) |
| baseUrl                     | XXXXX-XXXXX-XXXXX      | Link del servicio a consumir en esta web. (Link de la API Principal) |
| baseUrlLocal                | http://localhost:2000                 | Link de API en ambiente local |
| assetsURL                   | https://d10kixcrv010ns.cloudfront.net | -- |



