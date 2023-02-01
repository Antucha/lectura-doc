---
layout: page
title: Artefactos
permalink: /Artefactos/
parent: Arquitectura
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

# Diagrama de artefactos

  ![My helpful screenshot](https://cdn.discordapp.com/attachments/905940010019213402/1013822962748624968/Untitled_Diagram.drawio_5.png)


# Cuadro informativo

| Nombre                   | Tipo                                 | Descripción | Tecnología | URL local | URL producción |
| -----------                 | -----------                           | ----------- | ----------- | ----------- | ----------- |
| Frontend Estudiante                  | web                         | Plataforma orientada a estudiantes. | Vue JS | http://localhost:3000/ | https://orientacion.queestudiar.la/ |
| Frontend Colegios                  | web                         | Plataforma orientada a colegios. | Vue JS | http://localhost:3000 | https://school.queestudiar.pe/ |
| Frontend USIL                  | web                         | Plataforma orientada a USIL. | Vue JS | http://localhost:3000 | https://usil.queestudiar.la/ |
| Api principal                  | api                         | Proyecto de API principal. | Node JS | http://localhost:2000 | https://service.qeestudiar.com/api |
| Notificación                  | api                         | -- | Node JS | http://localhost:2000 | https://service.qeestudiar.com/api/notifications |
| Métricas                  | api                         | Orientado a consultas a BD sobre las métricas. | Node JS | http://localhost:2000 | https://service.qeestudiar.com/api/metrics |
| Generador de PDF                  | api                         | Generar PDF de resultados | Node JS | http://localhost:1000 | https://service.qeestudiar.com/api/pdf |
| QEUE                  | api                         | -- | Node JS | http://localhost:2000 | https://service.qeestudiar.com/api/*** |
| Recomendación                  | api                         | -- | Python | http://localhost:4000 | https://service.qeestudiar.com/api |



# Artefactos AWS

| Nombre                   | Símbolo                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| Amazon Simple Storage Service                   | S3                         |  Backup de datos, archivos y aplicaciones. |
| AAWS Lambda                    | --                         |  Permite ejecutar su código sin preocuparse por el aprovisionamiento y el mantenimiento de la infraestructura de backend. |
| Amazon Relational Database Service                    | --                         |  Usado para alojar la base de datos de queestudiar. |
| Amazon DynamoDB                    | --                         |  Base de datos noSQL que es utilizado para alojar datos a partir de los cuales se gerera el PDF de resultados de los estudiantes. |
| Amazon API Gateway                    | --                         |  Control de acceso general para las llamadas de las API's para proteger datos valiosos. |
| Amazon Route 53                    | --                         |  Conecta de forma efectiva las solicitudes del usuario con la infraestructura en ejecución en AWS. |
| AmazonCloudWatch                   | --                         |  Recopila datos operativos y de monitoreo en forma de registros, métricas y eventos, y permite su visualización mediante paneles automatizados para obtener una vista unificada de los recursos, las aplicaciones y los servicios de AWS que se ejecutan en AWS y en las instalaciones. |
|Amazon Simple Queue Service                    | SQS                         |  Para intercambiar información confidencial entre aplicaciones mediante cifrado del lado del servidor (SSE) para cifrar todos los cuerpos de mensajes. |


# Prioridad para despliegue

| Prioridad | Nombre              | Tipo    | Detalle                                           | Documentación |
|-----------|---------------------|---------|--------------------------------------------------------|---------------|
| 1         | S3 Carpetas, PDFS   | Store   | Utilizas por api principal y PDF                    |  [Link 1](https://beamish-cascaron-ae4c37.netlify.app/queestudiar%20sqs%20pdf/#aws-s3){:target="_blank"} - [Link 2](https://beamish-cascaron-ae4c37.netlify.app/queestudiar%20aws/#bucket-s3){:target="_blank"}            |
| 2         | MYSQL RDS           | DB      | Utilizado por API principal y metricas              |  [Link 1](https://beamish-cascaron-ae4c37.netlify.app/queestudiar%20bd/){:target="_blank"}             |
| 3         | Dynamo DB           | DB      | Lo utiliza métricas y API principal                 |  [Link 1](https://beamish-cascaron-ae4c37.netlify.app/queestudiar%20aws/#carga-de-datos-dynamodb){:target="_blank"}             |
| 4         | Recomendación       | api     | No depende de ningun otro artefacto                |               |
| 5         | Notificación        | api     | No depende de ningun otro artefacto                |               |
| 6         | Métricas            | api     | No depende de ningun otro artefacto                |               |
| 7         | QEUE SQS            | sqs     | Creación del Link SQS, utilizado por Generado de PDF|  [Link 1](https://beamish-cascaron-ae4c37.netlify.app/queestudiar%20sqs%20pdf/#forma-de-despliegue-autom%C3%A1tica){:target="_blank"}             |
| 8         | QEUE Lambda         | Lambda  | Lambda actualizar variables manual                 |               |
| 9         | Generador de PDF    | api     | Solo depende de QEUE para enviar colas, link SQS    |               |
| 10        | Api principal       | api     | Api principal, utilizada por otras Api's y web     |               |
| 11        | Frontend Estudiante | web     | Utiliza las mayorías de las apis                    |               |
| 12        | Frontend Colegios   | web     | Utiliza las mayorías de las apis                    |               |
| 13        | Frontend USIL       | web     | Utiliza algunas apis                                |               |







