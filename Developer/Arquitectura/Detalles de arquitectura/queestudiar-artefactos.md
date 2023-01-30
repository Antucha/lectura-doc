---
layout: page
title: Detalles de arquitectura
permalink: /Detalles de arquitectura/
parent: Arquitectura
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

# Lenguaje moderno no propietario

Domain Driven Design
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1015284043266392204/unknown.png)

# Estructura

  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1015283734104248381/unknown.png)

# FRONTEND Y BACKEND

Es la estructura que mantiene cada proyecto, tanto para el frontend y las APIs.

  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1015283503803412611/unknown.png)


# Detalles de el uso de Twilio

## Artefactos que utilizan el servicio de twilio

* Api de notificaciones

El endpoint realizado en el artefacto es el siguiente: `/notification/whatsapp/sendMessage`

Los artefactos que lo consumen son los siguientes:
* Plataforma de estudiantes.
* Plataforma de talento.

Ambos artefactos solicitan el envío de un mensaje al estudiante en cuanto haya terminado su proceso vocativo.
El detalle del código se muestra en la siguiente imagen:

![My helpful screenshot](https://cdn.discordapp.com/attachments/1066686580703633469/1069385108630536252/5523a268-8721-476a-ae3d-ebc5cbdc61d7.png)

Y el detalle de la información enviada a la petición se muestra a continuación:

![My helpful screenshot](https://cdn.discordapp.com/attachments/1066686580703633469/1069385217032327218/03b20f5b-5435-4803-a2af-a3adda901a2c.png)


En relación a Twilio, se han configurado cinco plantillas, las cuales se enumeran a continuación:

![My helpful screenshot](https://cdn.discordapp.com/attachments/1066686580703633469/1069385280039161997/23456412-67f8-4b71-9f57-0a928855b647.png)

De estas plantillas, se utiliza la siguiente:

![My helpful screenshot](https://cdn.discordapp.com/attachments/1066686580703633469/1069385153958400041/e9d6d50b-dc5f-41d8-8dae-72f0f0ea9629.png)

En el archivo `ResultCareers.vue`, se tiene un mensaje con la palabra var, esa palabra se reemplazará poor una URL en el servicio de notificaciones.

![My helpful screenshot](https://cdn.discordapp.com/attachments/1066686580703633469/1069469481832812564/image.png)

