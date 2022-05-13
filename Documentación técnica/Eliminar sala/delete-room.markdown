---
layout: page
title: Eliminar sala  [DELETE]
permalink: /Eliminar sala/
parent: Documentación técnica
nav_order: 3
---

# Eliminar una sala [DELETE]
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

