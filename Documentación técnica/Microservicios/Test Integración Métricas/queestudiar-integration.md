---
layout: page
title: Test Integración Métricas
permalink: /Test Integración Métricas/
parent: Microservicios
grand_parent: Documentación técnica
nav_order: 7
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
  'app\src\integration\integration.test.ts'
{% endhighlight %}

Allí se encuentran todos los archivos de testeo de la fábrica del proyecto:
![](https://cdn.discordapp.com/attachments/955522800918085686/982402801068040302/unknown.png)

El archivo principal de ejecución es el archivo `integration.test.ts` y los demás contienen los códigos de prueba de forma organizada.


# Ejecución de la prueba
## Abrir el archivo `integration.test.ts`

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

## Ejecutar el comando `npm run integration`

Debes verificar que la consola ejecute el comando dentro del directorio /app

![](https://cdn.discordapp.com/attachments/955522800918085686/983491175078064178/unknown.png)


## Si la funcionalidad es correcta
De ser el caso que la funcionalidad está correcta, se obtendrá la siguiente respuesta:

![](https://cdn.discordapp.com/attachments/955522800918085686/983490864187854899/unknown.png)

## Si la funcionalidad tiene error
De ser el caso que la funcionalidad no está correcta, se obtendrá la siguiente respuesta:
![](https://cdn.discordapp.com/attachments/955522800918085686/983491014562054215/unknown.png)