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

El contenido de las variables de entorno se muestran a continuación:

{% highlight .env %}
AWS_ACCESS_KEY_ID=AKIA5N2BE72V4SRBVVS6
AWS_SECRET_ACCESS_KEY=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

NODE_ENV=local

# HTTP_BASE PARAMETERS
# loginSession
LOGIN_SESSION=schoolSession
# institutionsSelectedSession
INSTITUTIONS_SELECTED_SESSION=institutionsSelectedSession
# urlModalSession
URL_MODAL_SESSION=urlModal
# sessionUrl
SESSION_URL=.queestudiar.pe
# url
URL=https://school.queestudiar.pe
# baseUrlDev
BASE_URL_DEV=https://service.qeestudiar.com
# baseUrl
BASE_URL=https://service.qeestudiar.com
# baseUrlLocal
BASE_URL_LOCAL=http://localhost:2000
# assetsURL
ASSETS_URL=https://d10kixcrv010ns.cloudfront.net

# GOOGLE MAPS
GOOGLE_MAPS_KEY=AIzaSyBC9dI5E129t41vuxU9n_t4c0PD7xJxtiY
GOOGLE_MAPS_LIBRARIES=places
{% endhighlight %}

# VARIALES

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| loginSession                | schoolSession                           | -- |
| institutionsSelectedSession | institutionsSelectedSession           | -- |
| urlModalSession             | urlModal                              | -- |
| sessionUrl                  | .queestudiar.la                       | Nombre del dominio donde se guardará la sesión iniciada. |
| url                         | https://school.queestudiar.pe           | URL de la web creada- |
| baseUrlDev                  | https://service.qeestudiar.com        | Link del servicio a consumir |
| baseUrl                     | https://service.qeestudiar.com        | Link del servicio a consumir en esta web |
| baseUrlLocal                | http://localhost:2000                 | Link en ambiente local |
| assetsURL                   | https://d10kixcrv010ns.cloudfront.net | -- |
| GOOGLE_MAPS_KEY                   | AIzaSyBC9dI5E129t41vuxU9n_t4c0PD7xJxtiY | -- |
| GOOGLE_MAPS_LIBRARIES                   | places | -- |
