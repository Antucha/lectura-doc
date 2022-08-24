---
layout: page
title: Queestudiar SQS PDF
permalink: /Queestudiar SQS PDF/
parent: Microservicios
grand_parent: Developer
nav_order: 3
---

<details open markdown="block">
  <summary>
    Índice:
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Arquitectura

![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1010224651806462052/unknown.png){: width="450" }

# Descripción
1. PDF SERVICE verifica que el PDF haya sido creado o ya existe en el repositorio para no volver a crear. También agrupa la cantidad de estudiantes de peticiones de estudiantes para una descarga masiva de PDF.
1. En caso que PDF SERVICE verifique que no existe el PDF, manda el id de estudiante a SQS y lo coloca en cola de ejecución. Para que luego SQS ejecutar el SQS SERVICE (Lambda)  donde le envía cada ID del estudiante y empiece a generar los PDFs.
1. Todo PDF generado por SQS SERVICE (Lambda) es enviando a un repositorio de S3.

