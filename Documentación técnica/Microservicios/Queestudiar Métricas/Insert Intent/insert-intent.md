---
layout: page
title: Insert Intent
permalink: /Insert Intent/
parent: Queestudiar Métricas
grand_parent: Microservicios
nav_order: 0
# has_children: true
---

# Generar un insert en la base de datos [POST]
Ruta: `{host}/metric/create`

La API recibe de forma oblidatoria el objeto `body` conteniendo los soguientes parámetros:
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





