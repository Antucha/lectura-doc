---
layout: page
title: Query SQL
permalink: /Query SQL/
parent: Documentación funcional
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

# Carreras más solicitadas
En el proyecto de nombre `sandbox-queestudiar`
Ruta: `{host}/api/career`

En el controlador de la ruta, se podrá cambiar el nombre del documento por un nombre deseado.

![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/978409869164019762/unknown.png)

Ello generará un documento EXCEL con el nombre del archivo especificado en el mismo directorio del controlador.

![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/978411376164896808/unknown.png)

O se podrá ejecutar la siguiente query en el WorkBench de MySQL, y se obtendrán los datos para aplicar el tratamiento necesario:
{% highlight sql %}

select vp.* from vocational_progress as vp 
where vp.created_at between '2020-01-01 00:00:00' and '2021-01-01 00:00:00' and 
vp.vocational_guidance_id = "19680012-6383-4737-ae1c-d5836df16afc" 
order by vp.created_at desc 
limit 10000;

{% endhighlight %}

Se tendrá datos con la siguiente estructura:

| data... | response_result | ..Data |
|-------|--------|------|
| data... | [{"title":"Tu Vocación vs ... | ...data |
| data... | [{"title":"Tu Vocación vs ... | ...data |
| data... | [{"title":"Tu Vocación vs ... | ...data |

La columna response_result contendrá los datos que necesitamos tratar: 

![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/978417545080102932/unknown.png)

La propiedad career_name contendrá el nombre de la carrera. Esos datos desestructurados serán almacenados en el archivo excel anteriormente mencionado.




# Estudiante de Usil (premium)

En el proyecto de nombre `sandbox-queestudiar`
Ruta: `{host}/api/career`

{% highlight sql %}

select s.name, s.surname, s.phone, u.email, s.graduation_year, sc.name, 
case 
when sc.type='private' then 'Privada' 
when sc.type='pgd' then 'Pública'
end as Tipo_Colegio,
sc.province as Provincia_Colegio, sc.city as Departamento_Colegio,
case when count(vp.id) >= 11 then '100%' else
(count(vp.id))/11*100
end as Porcentaje,
s.created_at from student s
  inner join user u on u.id = s.user_id
  inner join school sc on sc.id=s.school_id
  left join vocational_progress vp on vp.student_id = s.id
where
    s.school_id  IN
(
  (select sc1.school_id from school_code sc1 
  where sc1.institution_id = 'ba346110-5c59-474a-8504-093d3a7c91e4' 
  order by  created_at desc)
)and 
s.created_at between '2021-01-01 00:00:00' and '2022-03-30 22:25:54' and 
u.state = '1' and 
sc.country='peru'
group by s.id 
###having count(vp.id) < 11
order by s.created_at desc;

{% endhighlight %}

Notas:
* el having se agrega si queremos ver los estudiantes que completaron (>=11) y los que no completaron (<11).
* si se desea cambiar de pais, se cambia por la palabra PERU
* Las fechas se cambian según la fecha que desees sacar, recordar que hay una diferencia de 5 horas en el registro de datos.
* insitution_id en este campo cambias la institucion que deseas colocando su id

# Cantidad de colegios

<!-- En el proyecto de nombre `sandbox-queestudiar`
Ruta: `{host}/api/career` -->

{% highlight sql %} 
select sc.id, s.name, sc.institution_id, sc.created_at from school_code sc 
inner join school s on s.id = sc.school_id 
where sc.created_at between '2021-03-09 00:00:00' AND '2022-03-30 00:00:00'
and sc.institution_id = 'ba346110-5c59-474a-8504-093d3a7c91e4'
 and s.country='peru'
group by s.id
 order by sc.created_at desc;

{% endhighlight %}


# Colegios de provincia (USIL premium)

<!-- En el proyecto de nombre `sandbox-queestudiar`
Ruta: `{host}/api/career` -->

{% highlight sql %} 
select sc.id, s.name,s.city, s.province, sc.institution_id, sc.created_at from school_code sc 
inner join school s on s.id = sc.school_id 
where sc.created_at between '2021-03-09 00:00:00' AND '2022-03-30 00:00:00'
and sc.institution_id = 'ba346110-5c59-474a-8504-093d3a7c91e4'
and s.country='peru'
and s.province !='lima' and s.province !='PROV. CONST. DEL CALLAO'
group by s.id
order by sc.created_at desc;

{% endhighlight %}

Notas:
* En s.province colocar las provincias que no quieres que salga. 
* Las fechas y institucion son el mismo formato que las querys anteriores.


# Estudiantes USIL express


<!-- En el proyecto de nombre `sandbox-queestudiar`
Ruta: `{host}/api/career` -->

{% highlight sql %} 
select r.name,r.surname,r.grade, r.school, r.career from reference r 
where r.institution_id='ba346110-5c59-474a-8504-093d3a7c91e4' 
and r.created_at> '2021-03-09 00:00:00' 
and r.state in (1) 
group by r.id;
{% endhighlight %}

Notas:
* El state significa si terminaron el proceso, el valor de 1 es termino el proceso y el 2 es que no termino el proceso.

# Cantidad de colegios (express)

{% highlight sql %} 
select school, count(*) as students from reference 
where created_at between '2021-03-01 00:00:00' and '2022-03-30 22:25:54'
and state in (2,0,1)
and institution_id = 'ba346110-5c59-474a-8504-093d3a7c91e4'
group by school;

{% endhighlight %}

Notas:
* El state significa si terminaron el proceso, el valor de 1 es termino el proceso y el 2 es que no termino el proceso.

# Cantidad areas (express)


{% highlight sql %} 
select a.name,count(*) from reference r 
inner join career c on r.career = c.name
inner join area a on c.area_id = a.id
where r.institution_id='ba346110-5c59-474a-8504-093d3a7c91e4' 
and YEAR(r.created_at) = '2021' and r.state in (2,1) 
group by a.id;
{% endhighlight %}

# Cantidad carreras (express)


{% highlight sql %} 
select career, count(*) from reference 
where institution_id='ba346110-5c59-474a-8504-093d3a7c91e4' 
and YEAR(created_at) = '2021' 
and state in (2,1) 
and school is not null 
group by career;
{% endhighlight %}



# Cantidad grado (express)

{% highlight sql %} 
select * from school_code where code= 'vocacionusat';
-- or
update school_code set 
institution_id = 'f5c692ac-400c-4a2d-9f85-b1983825cf28' 
where id='ce61f160-853c-11ec-be2e-954930522e2e';

{% endhighlight %}

Notas: 
* En code va el codigo que quieres ver y luego para poder actualizar tienes que colocar el id de la institucion y el id del registro donde está ubicado el código.
* f5c692ac-400c-4a2d-9f85-b1983825cf28 este es el id de USAT y ba346110-5c59-474a-8504-093d3a7c91e4 es el id de USIL.

# Ver si el estudiante está registrado

{% highlight sql %} 
select * from student where phone='981233633';
-- or
select * from user where email=’canazagonzalo@gmail.com’;
{% endhighlight %}

# Cambiar contraseña de cuenta 

{% highlight sql %} 
update user set password = ‘escribir o colocar la contraseña encryptada’ 
where id = ‘colocar el id de tabla user o el user_id de la tabla estudent’
{% endhighlight %}

# Obtener alumnos del año pasado de un colegio en pa rticular

{% highlight sql %} 
update user u 
inner join student s on u.id = s.user_id 
set u.state = '0'
where u.state = '1'
and s.school_id = '0bec6720-c601-11e9-9971-9f263e112bc7'
and u.created_at < '2022-01-01 16:16:17';

{% endhighlight %}

# Como crear colegios nuevos que no están en la base

{% highlight sql %} 
select * from school order by created_at desc;
{% endhighlight %}

# Consultar etapa de proceso de estudiante de todo un corporativo

{% highlight sql %} 
select 
s.name,	
s.surname, 
s.phone, 
s.document, 
s.grade, 
s.section, 
(count(vp.id)/7)*100 as percent,
vp.created_at as 'creación', 
sh.name as 'school', 
s.graduation_year 
from vocational_progress vp 
inner join student s on s.id = vp.student_id
inner join school sh on sh.id = s.school_id
inner join school_business sb on sb.id = sh.school_business_id
inner join user u on u.id = s.user_id
where 
	 u.created_at > '2022-01-01 00:00:00'  and
	 sb.id = '6d8f1be7-0c24-45d7-9b59-9cbb9f14b13c' and -- Aquí poner el id de school_business
	 u.state = '1'
    and vp.vocational_guidance_id in (
'6122993f-d1c6-4196-aaf0-00666f4ed686', 
'48e96300-adeb-48fa-b1d3-a221fc451ae3',
'3c38680d-7ce0-43ff-8179-4958b980e049',
'56709ac9-c731-43cd-8510-0b9a507e5577',
'5a19a7b2-b37a-48ca-94dd-2c6bbdde44dc',
'1ae74de5-8cf5-4a1f-9ae7-271bd5d616ae',
'b6b85bf9-a435-456e-aaf4-e6ddfc371581'
)
group by s.id;
{% endhighlight %}


# Relacionar colegios con un administrador general
* Se selecciona el `id` del corporativo al que se desea relacionar

{% highlight sql %} 
select *from school_business;
{% endhighlight %}

![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/989375554484580422/unknown.png)

* Copia el `id` del corporativo
* Selecciona el colegio que se desea implementar

{% highlight sql %} 
select *from school where id = "85398c30-c51f-11e9-b6c1-c15e70787fb4";
{% endhighlight %}

* Pegar el `id` del corpoorativo en la columna `school_business_id` de la tabla `school_business`.

![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085684/989376680684572702/unknown.png)

* Guarda los cambios

# Cantidad de test premium

Modificar la fecha para determinar el rango que desee.

{% highlight sql %} 
select count(*) from student s
inner join user u on u.id = s.user_id
where s.created_at > '2022-01-01 00:00:00'
and u.state = '1';
{% endhighlight %}


# Cantidad de test express

Modificar la fecha para determinar el rango que desee.

{% highlight sql %} 
select count(*) from student s
inner  join student_membership sm on  s.id = sm.student_id 
where s.created_at > '2022-01-01 00:00:00'  -- and '2021-01-01 00:00:00' 
;
{% endhighlight %}













































































































































































































































