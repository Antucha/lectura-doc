---
layout: page
title: Loguin [POST]
permalink: /Loguin/
parent: Documentación técnica
nav_order: 1
---


# Loguin a la plataforma [POST]
Ruta: `{host}/api/auth/login`

La API recibe de forma oblidatoria el objeto **body** contenindo los soguientes parámetros:
{% highlight json %}
{
    "user": "antony.devcoder2199@gmail.com",
    "role": "patient",
    "password": "mptrasiente"
}
{% endhighlight %}

`User`, será el correo electrónico registrado del usuario; `role`, el rol del paciente, y existen de tres tipos: tatient, psychologist y assesment; `password` es la contraseña del usuario.

De ser exitosa la operación, se retorna un objeto conteniendo los datos del usuario registrado: 
{% highlight json %}
{
    "code": 200,
    "message": "Logged in successfully",
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9....",
        "user": {
            "id": "f4372360-63fe-11ec-beb0-65f0771517a2",
            "patientId": "f4372361-63fe-11ec-beb0-65f0771517a2",
            "name": "Antony",
            "surname": "Rojas Medina",
            "phone": "929151762",
            "phoneCode": "51",
            "idealWeight": 63.12,
            "targetWeight": 70,
            "currentWeight": 87,
            "heightSize": 166,
            "email": "Antony.devcoder2199@gmail.com",
            "gender": "m",
            "role": "patient",
            "haveMembership": true,
            "subscriptionEnd": "2022-05-16T06:54:00.000Z"
        }
    }
}
{% endhighlight %}

Y, si la operación falla, se retorna el siguente objeto:
{% highlight json %}
{
    "code": 401,
    "message": "Unauthorized user",
    "error": "Unauthorized"
}
{% endhighlight %}
