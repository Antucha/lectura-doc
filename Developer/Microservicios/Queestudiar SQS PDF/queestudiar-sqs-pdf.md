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

1. PDF GENETATOR SERVICE verifica que el PDF de los estuudiantes haya sido creado y ya existe en el repositorio para no volver a crear. En caso de que no exista el PDF, se tendrá que generar el pdf.Para generar los PDFs agrupa la cantidad de peticiones de estudiantes para una descarga masiva de PDF.
1. En caso que PDF SERVICE verifique que no existe el PDF, manda el id de estudiante a SQS y lo coloca en cola de ejecución para que luego SQS ejecute el SQS SERVICE (Lambda)  donde le envía cada ID del estudiante y empiece a generar los PDFs.
1. Todo PDF generado por SQS SERVICE (Lambda) es enviando a un repositorio de S3.
1. El código del proyecto está subido al repositorio `https://git-codecommit.us-east-1.amazonaws.com/v1/repos/queestudiar-queue`.

{% include alerts/danger.html content="**NOTA**<br/>Recordar conceder permisos de consulta a la base de datos mysql a todos los artefactos de microservicios y también al proyeto sqs en la función lambda de AWS" %}

<!-- 1. El proyecto sqs será desplegado mediante serverless. Las instrucciones serverless que funcionaban en queestudiar están en el archivo `serverless.yml` dentro del proyecto. Dentro de ese archivo se debe cambiar las configuraciones por las de USIL, es decir, en general, deben reemplazarse por las credenciales de cada empresa.
1. Se puede [automatizar](https://aws.amazon.com/blogs/devops/building-a-serverless-jenkins-environment-on-aws-fargate/){:target="_blank"} el despliegue del proyecto con la documentación indicada. -->

<!-- ### Paso 1
#### Amazon SQS

Se utilizará el servicio de colas de Amazon SQS y será nombrado `PDF_QUEUE`
La configuración general de la cola debe ser la siguiente:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039665552102277140/image.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032715515635961927/unknown.png)

### Paso 2

Se debe deplegar el proyecto con severless, para ello:

1. [Creamos](https://qe-docs.herokuapp.com/Queestudiar%20AWS/#downloadpdf){:target="_blank"}  una tabla `DownloadPdf` en DynamoDB.
2. Al haber creado la tabla, vamos a la información de la tabla y tendremos un Nombre de recurso de Amazon (ARN) el cual copiaremos como valor de la variable DYMANO_DOWNLOAD_PDF_TABLE_ARN.
3. También será necesario configurar correctamente la región utilizada por la empresa y ponerla en el documento `serverless.yml`.
4. Copiar el ARN de la cola de SQS:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039937366258876496/image.png)
5. Pegar el ARN en el documento `.env` como valor de la variable SQS_PDF_QUEUE_ARN.
6. Colocar las siguientes variables de entorno en el documento `.env`:

    | Variables                   | Valor                                 | Descripción |
    | -----------                 | -----------                           | ----------- |
    | AWS_ACCESS_KEY_ID                   | XXXX-XXXX-XXXX | AccessKeyId de AWS |
    | AWS_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | SecretAccessKeyId de AWS |
    | AWS_REGION                   | XXXX-XXXX-XXXX | Region de AWS |
    | DYMANO_DOWNLOAD_PDF_TABLE_ARN                   | XXXX-XXXX-XXXX | ARN de la tabla DownloadPdf |
    | SQS_PDF_QUEUE_ARN                   | XXXX-XXXX-XXXX | ARN de la cola PDF_QUEUE |

    El usuario con esas credenciales debería tener configurado las siguientes políticas:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1040727120537714729/unknown.png)


7. Se debe [instalar node js](https://www.youtube.com/watch?v=ipmhBYqIP44&ab_channel=UskoKruM2010){:target="_blank"} y seguidamente, en el directorio de la aplicción, los siguientes comandos de instalación:
   1. Para instalar las dependencias del proyecto, ejecutar `npm install`.
   2. Para instalar serverless ejecutar `npm install -g serverless`.
   3. Para verificar, ejecutar `serverless --version` y eso debe arrojar la versión de serverless instalada.
   4. Una vez inataladas todas las dependencias, ejecutatr el comando de despliegue: `serverless deploy`
8. Si el despliegue se realizó de forma correcta, se debe tener la siguiente salida en la consola:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1040705088034975834/image.png)

### Paso 3

#### Lambda

Se utilizará el servicio de Funciones de Lambda de AWS. La función será nombrada: `queestudiar-sqs-pdf-prod-handlerSQS`, o similar, eso dependerá del nombre del servicio especificado en `serverless.yml`:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1040023428905836594/image.png)

Esta función se creará de forma automática al hacer el despliegue de la aplicación.

En lambda verificar la función creada automáticamente y, además, deberá tener un desencadenador a la cola de SQS `PDF_QUEUE`:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039667177025966180/image.png)

La configuración del desencadenador debe tener la siguiente configuración:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039668395571937430/image.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032731135563792424/unknown.png)

### Paso 4

Dentro de Lambda, en la función creada de forma automática, se deben crear las variables de entorno, damos click en "Editar", y dentro, creamos las variables de entorno:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039662792011153468/image.png)

Las variables de entorno son las siguientes:

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | Motor de la base de datos utilizado |
| DB_NAME                     | XXXX-XXXX-XXXX           | Nombre de la base de datos |
| DB_USER_NAME                | XXXX-XXXX-XXXX                              | Nombre de usuario de BD |
| DB_PASSWORD                 | XXXX-XXXX-XXXX                      | Contraseña de la BD |
| DB_HOST                     | XXXX-XXXX-XXXX         | Host de la BD |
| S3_BASE_URL                   | XXXXX-XXXX-XXXX | Url del bucket base de S3. Ejm: <https://queestudiar.s3-us-east-1.amazonaws.com> |
| S3_BUCKET_NAME                   | queestudiar | Nombre del bucket en S3 |
| S3_SUFFIX_NAME                   | pdfs | Nombre del sufijo en S3 |
| PDF_MANAGER_TABLE                   | pdfs | Nombre del almacén de pdfs |
| URL_CHARACTERS                   | XXXX-XXXX-XXXX | Directorio de S3 de la carpeta professionalvalue |
| URL_INTELLIGENT                   | XXXX-XXXX-XXXX | Directorio de S3 de la carpeta intelligence |
| BASE_SERVICE                   | Url de la api principal | Url de la api principal |
| CHROMIUM_LOCATION                   | ./node_modules/puppeteer/.local-chromium/mac-674921/chrome-mac/Chromium.app/Contents/MacOS/Chromium | Ubicación de chromium en node_modules |
| INSTITUTION_ID                   | ba346110-5c59-474a-8504-093d3a7c91e4 | Id de USIL en la bd de queestudiar |
| SCHOOL_WEB_URL                   | <https://school.queestudiar.pe> | Url de la plataforma de colegios |

### Paso 5

Finalmente, la cola de sqs tendrá una URL, eso se colocará como variable de entorno en el proyecto de API-GENERADOR.
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039669151469416459/image.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039939645267525702/unknown.png)
 -->
# AWS S3

Este proyecto y otros más necesitan recursos de AWS S3, para ello necesitamos subir esos recursos (imágenes) a un bucket de S3 realizando los siguientes pasos.

1. Crear un bucket para el proyecto queestudiar con el nombre `queestudiar`, si ya lo tiene, contunúe al siguiente paso.
2. Descomprimir e importar los siguientes [archivos](https://drive.google.com/file/d/1R3ykcBoYh6R2PanPsuDZyfQwSKzndnFQ/view?usp=sharing){:target="_blank"} dentro del directorio principal del Bucket `queestudiar`.
   1. Descomprimir el archivo `image.tar.gz`, descomprimirlo, dentro hay una carpeta `image`, subir esa carpeta al bucket `usil-queestudiar` de S3.
   2. Descomprimir el archivo `assets.zip`, descomprimirlo, dentro hay una carpeta `assets`, subir esa carpeta al bucket `usil-queestudiar` de S3.
   3. Descomprimir el archivo `assets-hbs.tar.gz`, descomprimirlo, dentro hay una carpeta `assets-hbs`, subir esa carpeta al bucket `usil-queestudiar` de S3.
3. También se debe crear, dentro del bucket de `usil-queestudiar`, una carpeta llamada `pdfs`, esta carpeta es una variable de entorno.

NOTA: De preferencia configurar estos recursos con acceso público ya que otros proyectos también lo requerirán.



# Forma de despliegue automática

## Generalidades

Esta forma de automatización es automática ya que:

1. El archivo `serverless.yml` creará automáticamente la tabla `DownloadPdf` en DynamoDB.
2. La cola `pdfQueue` se creará de forma automática.
3. La función `queestudiar-sqs-pdf-prod-handlerSQS` en lambda se creará de forma automática.

### Pasos

  1. Hacer pull del código a un entorno local.
  2. Allí encontrará un archivo `serverless.yml`, alí encontrará el sigiuente contenido:
      {% highlight sql %}
        service: queestudiar-sqs-pdf-test-8
        useDotenv: true
        provider:
          name: aws
          runtime: nodejs12.x
          stage: prod
          region: ${env:AWS_REGION}
          iam:
            role:
              statements:
                - Effect: Allow
                  Action:
                    - dynamodb:*
                    - s3:*
                  Resource:
                    - arn:aws:dynamodb:${env:AWS_REGION}:${env:AWS_ACCOUNT_ID}:table/DownloadPdf
                    - arn:aws:dynamodb:${env:AWS_REGION}:${env:AWS_ACCOUNT_ID}:table/DownloadPdf/index/*
                    - arn:aws:dynamodb:${env:AWS_REGION}:${env:AWS_ACCOUNT_ID}:table/pdfs
                    - arn:aws:dynamodb:${env:AWS_REGION}:${env:AWS_ACCOUNT_ID}:table/pdfs/index/*
                - Effect: Allow
                  Action:
                    - dynamodb:*
                    - s3:*
                  Resource: "arn:aws:dynamodb:${env:AWS_REGION}:${env:AWS_ACCOUNT_ID}:table/DownloadPdf/index/*"
        functions:
          handlerSQS:
            handler: handler.handler
            events:
              - sqs:
                  arn:
                    Fn::GetAtt:
                      - pdfQueue
                      - Arn
        resources:
          Resources:
            pdfQueue:
              Type: AWS::SQS::Queue
              Properties:
                DelaySeconds: 0
                MaximumMessageSize: 1024
                MessageRetentionPeriod: 60
                QueueName: "pdfQueue"
            DownloadPdf:
              Type: "AWS::DynamoDB::Table"
              Properties:
                TableName: DownloadPdf
                AttributeDefinitions:
                  - AttributeName: studentId
                    AttributeType: S
                  - AttributeName: order
                    AttributeType: N
                KeySchema:
                  - AttributeName: studentId
                    KeyType: HASH
                  - AttributeName: order
                    KeyType: RANGE
                ProvisionedThroughput:
                  ReadCapacityUnits: 1
                  WriteCapacityUnits: 1        
      {% endhighlight %}
  3. Crear un archivo `.env` y dentro crear las siguientes variables de entorno:

  | Variables                   | Valor                                 | Descripción |
  | -----------                 | -----------                           | ----------- |
  | AWS_ACCESS_KEY_ID                   | XXXX-XXXX-XXXX | AccessKeyId de AWS |
  | AWS_SECRET_ACCESS_KEY                   | XXXX-XXXX-XXXX | SecretAccessKeyId de AWS |
  | AWS_REGION                   | XXXX-XXXX-XXXX | Region de AWS |
  | AWS_ACCOUNT_ID                   | XXXX-XXXX-XXXX | ID de la cuenta de AWS:, es un número. Ejm: 923017734157 |

  4. Se debe [instalar node js](https://www.youtube.com/watch?v=ipmhBYqIP44&ab_channel=UskoKruM2010){:target="_blank"} y seguidamente, en el directorio de la aplicción, los siguientes comandos de instalación:
      1. Para instalar las dependencias del proyecto, ejecutar `npm install`.
      2. Para instalar serverless ejecutar `npm install -g serverless`.
      3. Para verificar, ejecutar `serverless --version` y eso debe arrojar la versión de serverless instalada.
      4. Una vez inataladas todas las dependencias, ejecutatr el comando de despliegue: `serverless deploy`
  5. Si el despliegue se realizó de forma correcta, se debe tener la siguiente salida en la consola:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1040705088034975834/image.png)
  
  6. Luego, verificar que se hayan creado la cola `pdfQueue` en SQS, la función `queestudiar-sqs-pdf-prod-handlerSQS` en lambda y la tabla `DownloadPdf` en dynamoDB.
  10. Se debe verificar que las configuraciones de la cola `pdfQueue` sea de la siguiente manera, sino, realizarlo manualmente.
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1044282705308819556/image.png)

  11. Se debe verificar que las configuraciones de la función `queestudiar-sqs-pdf-prod-handlerSQS` sea de la siguiente manera, sino, realizarlo manualmente.
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1044283303886323732/image.png)
   Además, se deben colocar las siguientes variables de entorno en la función de lambda:

   | Variables                   | Valor                                 | Descripción |
    | -----------                 | -----------                           | ----------- |
    | DB_DIALECT                  | mysql                         | Motor de la base de datos utilizado |
    | DB_NAME                     | XXXX-XXXX-XXXX           | Nombre de la base de datos |
    | DB_USER_NAME                | XXXX-XXXX-XXXX                              | Nombre de usuario de BD |
    | DB_PASSWORD                 | XXXX-XXXX-XXXX                      | Contraseña de la BD |
    | DB_HOST                     | XXXX-XXXX-XXXX         | Host de la BD |
    | S3_BASE_URL                   | <https://usil-queestudiar.s3.amazonaws.com> | Url del bucket base de S3. Ejm: <https://queestudiar.s3-us-east-1.amazonaws.com> |
    | S3_BUCKET_NAME                   | usil-queestudiar | Nombre del bucket en S3 |
    | S3_SUFFIX_NAME                   | pdfs | Nombre del sufijo en S3 |
    | PDF_MANAGER_TABLE                   | DownloadPdf | Nombre del almacén de pdfs |
    | URL_CHARACTERS                   | <https://usil-queestudiar.s3.amazonaws.com/assets/images/vocation/professionalvalue/> | Directorio de S3 de la carpeta professionalvalue |
    | URL_INTELLIGENT                   | <https://usil-queestudiar.s3.amazonaws.com/assets/images/vocation/intelligence/> | Directorio de S3 de la carpeta intelligence |
    | BASE_SERVICE                   | <http://queestudiar-api-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com> | Url de la api principal (sin '/' final)|
    | CHROMIUM_LOCATION                   | ./node_modules/puppeteer/.local-chromium/mac-674921/chrome-mac/Chromium.app/Contents/MacOS/Chromium | Ubicación de chromium en node_modules |
    | INSTITUTION_ID                   | ba346110-5c59-474a-8504-093d3a7c91e4 | Id de USIL en la bd de queestudiar |
    | SCHOOL_WEB_URL                   | <http://queestudiar-colegio-web-test-924cbc13d3c4341b.us-east-1.elasticbeanstalk.com> | Url de la plataforma de colegios |


  12.  Se debe verificar que las configuraciones de la tabla `DownloadPdf` sea de la siguiente manera, sino, realizarlo manualmente.
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1044284753811079238/image.png)
  16.  Finalmente, la cola de sqs tendrá una URL, eso se colocará como variable de entorno en el proyecto de API-GENERADOR.
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039669151469416459/image.png)
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039939645267525702/unknown.png)

