---
layout: page
title: Acualizar token [PUT]
permalink: /Actualizar token/
parent: Documentación técnica
nav_order: 4
---

# Acualizar el token de los usuarios [PUT]
Ruta: `{host}/api/user/firebase/set-token`

La API recibe de forma oblidatoria el objeto `body` conteniendo los soguientes parámetros:
{% highlight json %}
{
    "token": "dVWPyJ8vSmzaneNZtExRiH:APA91bGoJ...",
    "userId": "f4372360-63fe-11ec-beb0-65f0771517a2"
}
{% endhighlight %}

`token` es el nuevo tokes que se desea guardar, y `userId` es el ID del usuario.

Si la operación es exitosa, se retorá el siguiente objeto:
{% highlight json %}
{
    "code": 200,
    "message": "Se ha creado las opciones correctamente"
}
{% endhighlight %}


Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
