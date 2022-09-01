---
layout: page
title: Queestudiar Métricas
permalink: /Queestudiar Métricas/
parent: Microservicios
grand_parent: Developer
nav_order: 4
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

<!--  -->
# Cuadro informativo

| Tecnología      | Valor |
| ----------- | ----------- |
| Tecnología principal      | Node JS      |
| Framewok   | Express        |
| Documentos de trabajo | Typescript |

# Declaración de las variables de entorno
Las variaibles de entorno se encuentran en los documentos "`.env`". Para que funcionen en un entorno back-end en Node JS se debe seguien el siguiente procedimiento:
  1. Declarar las variables en el documento `.env`
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013791695671922810/unknown.png)
  1. Hacer conocer a Node JS la existencia las variables de entorno, esto se hace en el documento en el que se utilizarán las variables.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792240067420261/unknown.png)
  1. Ya podemos utilizar las variables de entorno en cualquier documento `.ts` o `.js`.
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/1013792103102423050/unknown.png)

El contenido de las variables de entorno se muestran a continuación:

{% highlight .env %}
    PORT=2000
MESSAGE=HelloWorldNow

# DATA BASE CONFIGS
DB_DIALECT=mysql
DB_NAME=qeestudiar_db
DB_USER_NAME=juan.bucio
DB_PASSWORD=347hfopLlm<>f3jj*#4h
DB_HOST=prodqueestudiar.c5wqshckxtah.us-west-2.rds.amazonaws.com

MODEL_PATH=/core/domain/models
TOKEN_SECRET=34534345345gdfg234234fd343
WEB=https://queestudiar.la
SERVICE_WEB=https://service.qeestudiar.com
QUEESTUDIAR_ID=2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8


# SUPLIERS SERVICES
# aws
CONFIG_ACCESS_KEY_ID=AKIA5N2BE72VZC5CA4WB
CONFIG_SECRET_ACCESS_KEY=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
CONFIG_REGION=us-west-2

# dynamoDb
DYNAMO_CHAT=trasienteDB-dev
DYNAMO_COMUNITY=Community
BIG_DATA_PROCESS=BigDataProcess


# PAYMENTS
# mercadopago
MERCADOPAGO_CLIENT_ID=''
MERCADOPAGO_CLIENT_SECRET=''

{% endhighlight %}

<!--  -->

# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DB_DIALECT                  | mysql                         | -- |
| DB_NAME                     | qeestudiar_db           | -- |
| DB_USER_NAME                | juan.bucio                              | -- |
| DB_PASSWORD                 | 347hfopLlm<>f3jj*#4h                      | -- |
| DB_HOST                     | prodqueestudiar.c5wqshckxtah.us-west-2.rds.amazonaws.com         | -- |
| MODEL_PATH                  | /core/domain/models               | Ruta de la ubicación de los archivos modelo en este proyecto |
| TOKEN_SECRET                | 34534345345gdfg234234fd343        | -- |
| WEB                     | https://queestudiar.la        | -- |
| SERVICE_WEB                | https://service.qeestudiar.com                 | -- |
| QUEESTUDIAR_ID                   | 2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8 | -- |
| CONFIG_ACCESS_KEY_ID                   | 2f994bc7-39c1-4d8d-9dfa-d58fdfd9af8 | -- |
| CONFIG_SECRET_ACCESS_KEY                   | kGR8d9/x4npARDh4vd/kZX8PgCUj6K52Em9p1HQI | -- |
| CONFIG_REGION                   | us-west-2 | -- |
| DYNAMO_CHAT                   | trasienteDB-dev | -- |
| DYNAMO_COMUNITY                   | Community | -- |
| BIG_DATA_PROCESS                   | BigDataProcess | -- |
| MERCADOPAGO_CLIENT_ID                   | '' | -- |
| MERCADOPAGO_CLIENT_SECRET                   | '' | -- |


# Ruta principal para acceder a la API
La ruta en **producción** es la siguiente:
`https://service.qeestudiar.com/metric`


La ruta en **modo de desarollo** es la siguiente:
`http://localhost:2000/metric`

La notación para el acceso a cualquiera de las rutas será de la siguiente namera: `"{host}/"`

# Generar un insert en la base de datos [POST]
Ruta: `{host}/metric/create`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    vocationalGuidanceId: item.vocationalGuidanceId,
    order: item.timestamps,
    studentId: item.studentId,
    schoolId: item.schoolId,
    studentGraduationYear: item.studentGraduationYear,
    studentSection: item.studentSection,
    studentGender: item.studentGender,
    schoolName: item.schoolName,
    schoolBusinessId: item.schoolBusinessId,
    timestamps: item.timestamps,
    responseResult: item.responseResult,
    processedResult: item.processedResult,
    finalResult: item.finalResult,
    state: item.state,
    sponsorId: item.sponsorId,
    isActive: 1
}
{% endhighlight %}


# Extraer las métricas de los estudiantes de un colegio [POST]
Ruta: `{host}/metric/school/progress-students`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    vocationalGuidanceId: item.vocationalGuidanceId,
    order: item.timestamps,
    studentId: item.studentId,
    schoolId: item.schoolId,
    studentGraduationYear: item.studentGraduationYear,
    studentSection: item.studentSection,
    studentGender: item.studentGender,
    schoolName: item.schoolName,
    schoolBusinessId: item.schoolBusinessId,
    timestamps: item.timestamps,
    responseResult: item.responseResult,
    processedResult: item.processedResult,
    finalResult: item.finalResult,
    state: item.state,
    sponsorId: item.sponsorId,
    isActive: 1
}
{% endhighlight %}


# Extraer las carreras top para los estudiantes [POST]
Ruta: `{host}/metric/school/top-carrers`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    vocationalGuidanceId: req.body.vocationalGuidanceId, 
    schoolId: req.body.schoolId,
    schoolBusinessId: req.body.schoolBusinessId,
    studentGraduationYear: req.body.studentGraduationYear,
    filter: req.body.filter
}
{% endhighlight %}

# Extraer la lista de los estudiantes [POST]
Ruta: `{host}/metric/student/list`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    page: 1
}
{% endhighlight %}

# Extraer la cantidad de los estudiantes [POST]
Ruta: `{host}/metric/student/count`

# Extraer la cantidad de los estudiantes [POST]
Ruta: `{host}/metric/student/subscribe`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    code: 1,
    schoolId. 'dasfsfsd',
}
{% endhighlight %}

# Extraer el prograso de los estudiantes [POST]
Ruta: `{host}/metric/student/progress-students`


# Lista de estudiantes de un colegio [POST]
Ruta: `{host}/metric/student/school`


La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    page: 1,
    schoolId. 'dasfsfsd',
}
{% endhighlight %}

# Lista de colegios [POST]
Ruta: `{host}/metric/school/list`


La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    page: 1,
}
{% endhighlight %}

# Cantidad de colegios [POST]
Ruta: `{host}/metric/school/count`

# Guardar el proceso de un estudiante [POST]
Ruta: `{host}/metric/process/insert`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    id: 1,
    studentId: 'fdsfsdfs',
}
{% endhighlight %}

# Extraer el proceso de un estudiante [POST]
Ruta: `{host}/metric/process/list`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    id: 1,
}
{% endhighlight %}

# Extraer el proceso de un estudiante [POST]
Ruta: `{host}/metric/process/new`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    id: 1,
    studentId: 'fdsfsdfs'
}
{% endhighlight %}

# Años de proceso [POST]
Ruta: `{host}/metric/process/year`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    id: 1
}
{% endhighlight %}

# Años de proceso [POST]
Ruta: `{host}/metric/process/list-year`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    id: 1,
    year: '2022-06-15'
}
{% endhighlight %}

# Años de proceso [POST]
Ruta: `{host}/metric/process/all`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    schoolId: 'das45f1-fds21',
    studentId: '45as120-dsa623-56as23'
}
{% endhighlight %}

# Extraer el proceso de cada estudiante [POST]
Ruta: `{host}/metric/process/process`

La API recibe de forma oblidatoria el objeto `body` conteniendo los siguientes parámetros:
{% highlight json %}
{
    vocationalGuidanceId: 'das45f1-fds21',
    studentId: '45as120-dsa623-56as23'
}
{% endhighlight %}

<!-- # Eliminar una sala [DELETE]
Ruta: `{host}/api/nutrionist/users/room/:id`

La API recibe de forma oblidatoria el `id` de la sala que se desea eliminar, esta eliminación será de forma definitiva sin posibilidad de recuperación; retorna la información acerca del proceso efectuado:
{% highlight json %}
{
    "code": 200,
    "message": "Se obtubo el perfil correctamente",
    "data": {
        "message": "Chat borrado satisfactoriamente, refresca la página para evitar errores",
        "roomId": ":id",
        "deletedRoom": 0,
        "deletedRoomUser": 0
    }
}
{% endhighlight %}

# Eliminar una sala2 [DELETE]
Ruta: `{host}/api/nutrionist/users/room/:id`

La API recibe de forma oblidatoria el `id` de la sala que se desea eliminar, esta eliminación será de forma definitiva sin posibilidad de recuperación; retorna la información acerca del proceso efectuado:
{% highlight json %}
{
    "code": 200,
    "message": "Se obtubo el perfil correctamente",
    "data": {
        "message": "Chat borrado satisfactoriamente, refresca la página para evitar errores",
        "roomId": ":id",
        "deletedRoom": 0,
        "deletedRoomUser": 0
    }
}
{% endhighlight %}
 -->

# Tes de integración

## Marco general

El módulo de pruebas unitarias del microservicio de métricas se ubica en el directorio

{% highlight javascript %}
  'app\src\integration\integration.test.ts'
{% endhighlight %}

Allí se encuentran todos los archivos de testeo de la fábrica del proyecto:
![](https://cdn.discordapp.com/attachments/955522800918085686/982402801068040302/unknown.png)

El archivo principal de ejecución es el archivo `integration.test.ts` y los demás contienen los códigos de prueba de forma organizada.


## Ejecución de la prueba
### Abrir el archivo `integration.test.ts`

Dentro encontraremos las funciones a testear:

{% highlight javascript %}
// StudentRoute.test
import {
    testStudentList,
    testStudentCount,
    testStudentSubscribe,
    testStudentProgressStudents,
    testStudentSchool
} from './StudentRoute.test'

// SchoolRoute.test
import {
    testSchoolList,
    testSchoolCount,
    testSchoolExec,
    testSchoolProgressStudents,
    testSchoolTopCarrers
} from './SchoolRoute.test'

// ProcessRoute.test
import {
    testProcessInsert,
    testProcessList,
    testProcessNew,
    testProcessYear,
    testProcessListYear,
    testProcessAll,
    testProcessProcess
} from './ProcessRoute.test'

// MetricsRoute.test
import {
    testCloudTags
} from './MetricsRoute.test'

// WhatsAppRoute.test
import {
    testWhatsAppRedirect
} from './WhatsAppRoute.test'


//STUDENT TEST
testStudentList();
testStudentCount();
testStudentSubscribe();
testStudentProgressStudents();
testStudentSchool();


//SCHOOL TEST
testSchoolList();
testSchoolCount();
testSchoolExec();
testSchoolProgressStudents();
testSchoolTopCarrers();

// PROCESS TEST
testProcessInsert();
testProcessList();
testProcessNew();
testProcessYear();
testProcessListYear();
testProcessAll();
testProcessProcess();


//METRICS TEST
testCloudTags();

// TEST WHATSAPP
testWhatsAppRedirect();

{% endhighlight %}

### Ejecutar el comando `npm run integration`

Debes verificar que la consola ejecute el comando dentro del directorio /app

![](https://cdn.discordapp.com/attachments/955522800918085686/983491175078064178/unknown.png)


### Si la funcionalidad es correcta
De ser el caso que la funcionalidad está correcta, se obtendrá la siguiente respuesta:

![](https://cdn.discordapp.com/attachments/955522800918085686/983490864187854899/unknown.png)

### Si la funcionalidad tiene error
De ser el caso que la funcionalidad no está correcta, se obtendrá la siguiente respuesta:
![](https://cdn.discordapp.com/attachments/955522800918085686/983491014562054215/unknown.png)











# Tes unitario


## Marco general

El módulo de pruebas unitarias del microservicio de métricas se ubica en el directorio

{% highlight javascript %}
  'app/src/core/application/test'
{% endhighlight %}

Allí se encuentran todos los archivos de testeo de la fábrica del proyecto:
![](https://cdn.discordapp.com/attachments/955522800918085686/982402801068040302/unknown.png)

El archivo principal de ejecución es el archivo `test.ts` y los demás contienen los códigos de prueba de forma organizada.


## Ejecución de la prueba
### Abrir el archivo `test.ts`

Dentro encontraremos las funciones a testear:

{% highlight javascript %}
import {
    testMetricsFactoryGetMetrics, 
    testMetricsFactoryGetTopCarrers
} from './MetricsFactory.test';
import {
    CloudFactoryTest,
    testCloudFactoryGetTags
} from './CloudFactory.test';
import {
    testStudentFactoryGetProgressStudent, 
    testStudentFactoryGetAllStudents, 
    testStudentFactoryGetCountStudents,
    testStudentFactoryGetStudentsBySchool,
    testStudentFactorySubscribeStudent
} from './StudentFactory.test';
import {
    testSchoolFactoryExec, 
    testSchoolFactoryGetAllStudents,
    testSchoolFactoryGetCountSchool
} from './SchoolFactory.test';
import {
    testProcessFactoryInsertProcess,
    testProcessFactoryGetStudentProcess,
    testProcessFactoryNewProcess,
    testProcessFactoryProcessYear,
    testProcessFactoryGetStudentProcessYear,
    testProcessFactoryGetAllProcess,
    testProcessFactoryGetProcessById
} from './ProcessFactory.test';
import {
    testWhatsAppFactoryTracket
} from './WhatsAppFactory.test';

//CLOUD TEST
// CloudFactoryTest();
// testCloudFactoryGetTags();

//METRICS TEST
testMetricsFactoryGetMetrics();
testMetricsFactoryGetTopCarrers();

//STUDENT TEST
testStudentFactoryGetProgressStudent();
testStudentFactoryGetAllStudents();
testStudentFactoryGetCountStudents();
testStudentFactoryGetStudentsBySchool();
testStudentFactorySubscribeStudent();

//SCHOOL TEST
testSchoolFactoryExec();
testSchoolFactoryGetAllStudents();
testSchoolFactoryGetCountSchool();

//PROCESS TEST
testProcessFactoryInsertProcess();
testProcessFactoryGetStudentProcess();
testProcessFactoryNewProcess();
testProcessFactoryProcessYear();
testProcessFactoryGetStudentProcessYear();
testProcessFactoryGetAllProcess();
testProcessFactoryGetProcessById();

//WHATSAPP TEST
testWhatsAppFactoryTracket();

{% endhighlight %}

### Ejecutar el comando `npm run unitario`

Debes verificar que la consola ejecute el comando dentro del directorio /app

![](https://cdn.discordapp.com/attachments/955522800918085686/983491864273506444/unknown.png)


### Si la funcionalidad es correcta
De ser el caso que la funcionalidad está correcta, se obtendrá la siguiente respuesta:

![](https://cdn.discordapp.com/attachments/955522800918085686/983492233120604280/unknown.png)

### Si la funcionalidad tiene error
De ser el caso que la funcionalidad no está correcta, se obtendrá la siguiente respuesta:
![](https://cdn.discordapp.com/attachments/955522800918085686/982408420080644206/unknown.png)
