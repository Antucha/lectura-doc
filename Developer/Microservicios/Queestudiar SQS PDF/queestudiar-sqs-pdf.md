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
1. El proyecto sqs será desplegado mediante serverless.

# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | Motor de la base de datos utilizado |
| DB_NAME                     | XXXX-XXXX-XXXX           | Nombre de la base de datos |
| DB_USER_NAME                | XXXX-XXXX-XXXX                              | Nombre de usuario de BD |
| DB_PASSWORD                 | XXXX-XXXX-XXXX                      | Contraseña de la BD |
| DB_HOST                     | XXXX-XXXX-XXXX         | Host de la BD |
| AWS_ACCESS_KEY_ID                   | XXXX-XXXX-XXXX | AccessKeyId de AWS |
| AWS_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | SecretAccessKeyId de AWS |
| AWS_REGION                   | XXXX-XXXX-XXXX | Región del servidor de AWS |
| S3_BASE_URL                   | XXXXX-XXXX-XXXX | Url del bucket base de S3. Ejm: https://queestudiar.s3-us-east-1.amazonaws.com |
| S3_BUCKET_NAME                   | queestudiar | Nombre del bucket en S3 |
| S3_SUFFIX_NAME                   | pdfs | Nombre del sufijo en S3 |
| PDF_MANAGER_TABLE                   | pdfs | Nombre del almacén de pdfs |
| URL_CHARACTERS                   | XXXX-XXXX-XXXX | Directorio de S3 de la carpeta professionalvalue |
| URL_INTELLIGENT                   | pdfs | Nombre del almacén de pdfs |
| BASE_SERVICE                   | Url de la api principal | Url de la api principal |
| CHROMIUM_LOCATION                   | ./node_modules/puppeteer/.local-chromium/mac-674921/chrome-mac/Chromium.app/Contents/MacOS/Chromium | Ubicación de chromium en node_modules |
| INSTITUTION_ID                   | ba346110-5c59-474a-8504-093d3a7c91e4 | Id de USIL en la bd de queestudiar |
| SCHOOL_WEB_URL                   | https://school.queestudiar.pe | Url de la plataforma de colegios |

# Lambda 

Se utilizará el servicio de Funciones de Lambda de AWS. La función será nombrada: `queestudiar-sqs-pdf-prod-handlerSQS`.

Se debe generar un desencadenador a Lambda y enlasar a `PDF_QUEUE` mediante la siguiente configuración:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032731135563792424/unknown.png)


# Amazon SQS

También se utilizará el servicio de colas de Amazon SQS y será nombrado `PDF_QUEUE`.
La configuración general del proyecto debe ser la siguiente:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032715097967177748/unknown.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032715515635961927/unknown.png)


# AWS S3

1. Crear un bucket para el proyecto queestudiar con el nombre `queestudiar`, si ya lo tiene, contunúe al siguiente paso.
2. Descomprimir e importar los siguientes [archivos](https://drive.google.com/file/d/1R3ykcBoYh6R2PanPsuDZyfQwSKzndnFQ/view?usp=sharing){:target="_blank"} dentro del directorio principal del Bucket `queestudiar`.

