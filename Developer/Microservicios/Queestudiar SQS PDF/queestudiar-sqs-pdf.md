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
1. El proyecto sqs será desplegado mediante serverless. Las instrucciones serverless que funcionaban en queestudiar están en el archivo `serverless.yml` dentro del proyecto. Dentro de ese archivo se debe cambiar las configuraciones por las de USIL, es decir, en general, deben reemplazarse por las credenciales de cada empresa.
1. Se puede [automatizar](https://aws.amazon.com/blogs/devops/building-a-serverless-jenkins-environment-on-aws-fargate/){:target="_blank"} el despliegue del proyecto con la documentación indicada.

Lo primero a realizar es crear una función en lambda de AWS.

# Lambda

### Paso 1

Se utilizará el servicio de Funciones de Lambda de AWS. La función será nombrada: `queestudiar-sqs-pdf-prod-handlerSQS`.

### Paso 2

Dentro de Lambda crearemos las variables de entorno variables de entorno, damos click en "Editar", y dentro, creamos las variables de entorno:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039662792011153468/image.png)

Las variables de entorno son las siguientes:

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

### Paso 3

Seguidamente crearemos una cola en SQS.

# Amazon SQS

También se utilizará el servicio de colas de Amazon SQS y será nombrado `PDF_QUEUE`
La configuración general de la cola debe ser la siguiente:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039665552102277140/image.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032715515635961927/unknown.png)

### Paso 4

Volvemos a Lambda y en la función creada anteriormente se agregará un desencadenador a la cola de SQS `PDF_QUEUE` dando click en "Añadir desencadenador".
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039667177025966180/image.png)

Y seleccionar "SQS"
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039667490814435479/image.png)

La configuración del desencadenador debe tener la siguiente configuración:
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039668395571937430/image.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032731135563792424/unknown.png)

Finalmente, la cola de sqs tendrá una URL, eso se colocará como variable de entorno en el proyecto de API-GENERADOR.
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039669151469416459/image.png)
  ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039939645267525702/unknown.png)

### Paso 5

Una vez realizado todo lo necesario, ahora sí se debe deplegar el proyecto con severless, para ello:

1. [Creamos](https://qe-docs.herokuapp.com/Queestudiar%20AWS/#downloadpdf){:target="_blank"}  una tabla `DownloadPdf` en DynamoDB.
2. Al haber creado la tabla, vamos a la información de la tabla y tendremos un Nombre de recurso de Amazon (ARN):
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039929509341835264/image.png)
3. copiaremos eso en el documento `serverless.yml`:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039930285292265523/image.png)
4. También será necesario configurar correctamente la región utilizada por la empresa.
5. Copiar el ARN de la cola de SQS:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039937366258876496/image.png)
6. Pegar el ARN en `serverless.yml`:
   ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1039937767280480276/image.png)
7. Las dependencias y las instrucciones finales (instalar serverless y los comandos de despliegue) de despliegue de serverless las encuentra en la [documentación](https://itnext.io/serverless-application-development-with-node-js-on-aws-platform-using-serverless-framework-63e79fcf9409){:target="_blank"}.

# AWS S3

Este proyecto y otros más necesitan recursos de AWS S3, para ello necesitamos subir esos recursos (imágenes) a un bucket de S3 realizando los siguientes pasos.

1. Crear un bucket para el proyecto queestudiar con el nombre `queestudiar`, si ya lo tiene, contunúe al siguiente paso.
2. Descomprimir e importar los siguientes [archivos](https://drive.google.com/file/d/1R3ykcBoYh6R2PanPsuDZyfQwSKzndnFQ/view?usp=sharing){:target="_blank"} dentro del directorio principal del Bucket `queestudiar`.

NOTA: De preferencia configurar estos recursos con acceso público ya que otros proyectos también lo requerirán.
