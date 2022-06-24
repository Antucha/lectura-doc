---
layout: page
title: Queestudiar Métricas
permalink: /Queestudiar Métricas/
parent: Microservicios
grand_parent: Documentación técnica
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
