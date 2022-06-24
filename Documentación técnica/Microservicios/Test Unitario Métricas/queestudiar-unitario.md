---
layout: page
title: Test Uniratio Métricas
permalink: /Test Uniratio Métricas/
parent: Microservicios
grand_parent: Documentación técnica
nav_order: 6
---

<details open markdown="block">
  <summary>
    Índice:
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Marco general

El módulo de pruebas unitarias del microservicio de métricas se ubica en el directorio

{% highlight javascript %}
  'app/src/core/application/test'
{% endhighlight %}

Allí se encuentran todos los archivos de testeo de la fábrica del proyecto:
![](https://cdn.discordapp.com/attachments/955522800918085686/982402801068040302/unknown.png)

El archivo principal de ejecución es el archivo `test.ts` y los demás contienen los códigos de prueba de forma organizada.


# Ejecución de la prueba
## Abrir el archivo `test.ts`

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

## Ejecutar el comando `npm run unitario`

Debes verificar que la consola ejecute el comando dentro del directorio /app

![](https://cdn.discordapp.com/attachments/955522800918085686/983491864273506444/unknown.png)


## Si la funcionalidad es correcta
De ser el caso que la funcionalidad está correcta, se obtendrá la siguiente respuesta:

![](https://cdn.discordapp.com/attachments/955522800918085686/983492233120604280/unknown.png)

## Si la funcionalidad tiene error
De ser el caso que la funcionalidad no está correcta, se obtendrá la siguiente respuesta:
![](https://cdn.discordapp.com/attachments/955522800918085686/982408420080644206/unknown.png)

