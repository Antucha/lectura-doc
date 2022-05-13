---
layout: page
title: Estado de ánimo  [GET]
permalink: /Estado de ánimo/
parent: Documentación técnica
nav_order: 2
---


# Estado de ánimo semanal de un usuario [GET]
Ruta: `{host}/api/patient/feeling-posted-weekly/:id`

La API recibe de forma oblidatoria el `id` del paciente, y si la operación es exitosa, retorna la información semanal del estado de ánimo del paciente:
{% highlight json %}
{
    "code": 200,
    "message": "Se obtubo el perfil correctamente",
    "data": {
        "message": {
            "message": "Esta semana te está yendo mejor que la semana pasada. Ánimos, puede ser mucho mejor.",
            "icon": "https://trasiente.s3.us-west-2.amazonaws.com/chat/1647548528422.png"
        },
        "history": [
            {
                "weeekNumber": 10,
                "feeling": {
                    "name": "fantastic",
                    "translate": "fantástico",
                    "number": 5,
                    "icon": "https://trasiente.s3.us-west-2.amazonaws.com/chat/1647537963069.png"
                }
            },
            {
                "weeekNumber": 11,
                "feeling": {
                    "name": "pretty_good",
                    "translate": "bastante bien",
                    "number": 4,
                    "icon": "https://trasiente.s3.us-west-2.amazonaws.com/chat/1647537952443.png"
                }
            },
            {
                "weeekNumber": 12,
                "feeling": {
                    "name": "fantastic",
                    "translate": "fantástico",
                    "number": 5,
                    "icon": "https://trasiente.s3.us-west-2.amazonaws.com/chat/1647537963069.png"
                }
            },
            {
                "weeekNumber": 13,
                "feeling": {
                    "name": "alright",
                    "translate": "bien",
                    "number": 3,
                    "icon": "https://trasiente.s3.us-west-2.amazonaws.com/chat/1647537941171.png"
                }
            },
            {
                "weeekNumber": 14,
                "feeling": {
                    "name": "pretty_good",
                    "translate": "bastante bien",
                    "number": 4,
                    "icon": "https://trasiente.s3.us-west-2.amazonaws.com/chat/1647537952443.png"
                }
            }
        ]
    }
}
{% endhighlight %}

`weeekNumber` es la semana del año actual.
