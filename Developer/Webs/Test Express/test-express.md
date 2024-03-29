---
layout: page
title: Test Express
permalink: /Test Express/
parent: Webs
grand_parent: Developer
nav_order: 3
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

# INSTRUCCIONES:

{% include alerts/danger.html content="**NOTA**<br/>Se está utilizando la url https://orientacion.queestudiar.la perteneciente a la plataforma de estudiantes en el ambiente de testing. Este dominio deberá cambiarse por el dominio del ambiente que desee probarse." %}

1. Guaedar el siguiente [script](https://d10kixcrv010ns.cloudfront.net/cdnjs/v2/script-min.js){:target="_blank"} en un documento `.js` en S3 de AWS en modo público.


    {% highlight js %}
      class Queestudiar {
          constructor() {
              this.institutionCode = this.getUrlParameter("institution") || null, 
              this.referenceCode = this.getUrlParameter("reference") || null, 
              this.fullnameUser = this.getUrlParameter("fullname") || null, 
              this.emailUser = this.getUrlParameter("email") || null, 
              this.phoneUser = this.getUrlParameter("phone") || null, 
              this.surnameUser = this.getUrlParameter("surname") || null, 
              this.schoolUser = this.getUrlParameter("school") || null, 
              this.careerUser = this.getUrlParameter("career") || null, 
              this.gradeUser = this.getUrlParameter("grade") || null, 
              this.type = this.getUrlParameter("type") || null
          }
          static get INTEREST() {
              return "interests"
          }
          static get PERSONALITY() {
              return "personality"
          }
          set institution(e) {
              this.institutionCode || (this.institutionCode = e)
          }
          set reference(e) {
              this.referenceCode || (this.referenceCode = e)
          }
          set fullname(e) {
              this.fullnameUser || (this.fullnameUser = e)
          }
          set email(e) {
              this.emailUser || (this.emailUser = e)
          }
          set phone(e) {
              this.phoneUser || (this.phoneUser = e)
          }
          set surname(e) {
              this.surnameUser || (this.surnameUser = e)
          }
          set school(e) {
              this.schoolUser || (this.schoolUser = e)
          }
          set career(e) {
              this.careerUser || (this.careerUser = e)
          }
          set grade(e) {
              this.gradeUser || (this.gradeUser = e)
          }
          getUrlParameter(e) {
              e = e.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
              let t = new RegExp("[\\?&]" + e + "=([^&#]*)").exec(location.search);
              return null === t ? "" : decodeURIComponent(t[1].replace(/\+/g, " "))
          }
          go() {
              document.getElementsByClassName("queestudiar")[0].appendChild(this.prepareFrame())
          }
          validateReference() {
              this.referenceCode || (this.referenceCode = this.random(7))
          }
          random(e) {
              for (var t = "", 
                    s = "abcdefghijklmnopqrstuvwxyz0123456789", 
                    r = s.length, 
                    i = 0; 
                    i < e; i++) t += s.charAt(Math.floor(Math.random() * r));
              return t
          }
          prepareFrame() {
              if (![Queestudiar.INTEREST, Queestudiar.PERSONALITY].includes(this.type)) 
                return alert("Tipo de test invÃƒÂ¡lido."), "";
              this.validateReference();
              let e = "https://orientacion.queestudiar.la/embed/" + //Cambiar este dominio con el dominio de la plataforma de estudiantes que se desee probar dependiendo del ambiente que se desee probar 
                    this.type + "/" + 
                    this.institutionCode + 
                    "?key=" + 
                    this.referenceCode + 
                    "&fullname=" + 
                  this.fullnameUser;
              switch (this.emailUser && (e += "&email=" + this.emailUser), 
                      this.phoneUser && (e += "&phone=" + this.phoneUser), 
                      this.surnameUser && (e += "&surname=" + this.surnameUser), 
                      this.schoolUser && (e += "&school=" + this.schoolUser), 
                      this.careerUser && (e += "&career=" + this.careerUser), 
                      this.gradeUser && (e += "&grade=" + this.gradeUser), 
                      this.type) {
                  case Queestudiar.PERSONALITY:
                      e += "&processId=48e96300-adeb-48fa-b1d3-a221fc451ae3";
                      break;
                  case Queestudiar.INTEREST:
                      e += "&processId=dec0bcef-aa3c-4f8d-80cf-781e32285ddc"
              }
              let t = document.createElement("iframe");
              return 	t.setAttribute("src", e), 
                    t.style.position = "fixed", 
                    t.style.top = "0", 
                    t.style.left = "0", 
                    t.style.bottom = "0", 
                    t.style.right = "0", 
                    t.style.width = "100%", 
                    t.style.height = "100%", 
                    t.style.border = "none", 
                    t.style.margin = "0", 
                    t.style.padding = "0", 
                    t.style.overflow = "hidden", 
                    t.style["z-index"] = "999999", 
                    t
          }
      }
    {% endhighlight %}

  Esa variable se guardará en un docuento, por ejemplo: `https://d10kixcrv010ns.cloudfront.net/cdnjs/v2/script-min.js`

1. Registrar el ID institucional, por ejemplo: 627fa4f4-e07a-4520-bdab-0647fda47c98
2. Insertar Widget
   
  Insertar el siguiente bloque de código en el componente y/o documento donde lo requiera:

  {% highlight html %}
    <div class="queestudiar"></div>

    <script type="text/javascript" src="https://d10kixcrv010ns.cloudfront.net/cdnjs/v2/script-min.js"></script>
    <script type="text/javascript">
      const TEST = new Queestudiar()
      // Variable opcionales: En caso no venga de query parametros ?reference=REFERENCE_ID&institution=INSTITUTION_ID&fullname=FULLNAME&phone=PHONE&email=EMAIL
      TEST.institution = "" // Institution_id
      TEST.reference = "" // 
      TEST.fullname = "Manuel Vargaz"
      TEST.email = "juan@gmail.com"
      TEST.phone = "999999999"
      TEST.surname = "Romero"
      TEST.school = "Maria de la encarnacion"
      TEST.career = "Ingeneri industrial"
      TEST.grade = "Estoy en 3ro o 4to secundaria"
      TEST.type = Queestudiar.INTEREST
      // End Variables opcionales
      TEST.go()
    </script>
  {% endhighlight %}

## Uso
  
Parámetros requeridos
   - institution: Es el id que les asignaremos como institución
   - reference: Es el id único de referencia que ustedes crean para identificar a un usuario, de esa manera si regresa podrá volver a ver su resultado.
   - fullname: El nombre y apellido para personalizar la evaluación.
   - email: Enviar al crm para el envío de correo
   - phone: Celular para validar propiedad

  * Pueden pasar las variables de 2 maneras, colocándolos en javascript como indica el ejemplo anterior o pasándolo por query parametros.
    * Variables
        {% highlight html %}
          TEST.institution = "INSTITUTION ID"
          TEST.reference = "REFERENCIA ID"
          TEST.fullname = "Manuel Vargaz"
          TEST.email = "juan@gmail.com"
          TEST.phone = "999999999"
        {% endhighlight %}

  * Query parametros: https://usil.edu.pe/test?fullname=juan&reference=556565565F5G&institution=ba346110-5c59-474a-8504-093d3a7c91e4&email=juan@gmail.com&phone=934765765
  * La apariencia de la página deberá ser la siguiente:
    ![My helpful screenshot](https://cdn.discordapp.com/attachments/955522800918085683/1032045892603232266/unknown.png)
  
  * Datos para enviar a CRM
      {% highlight html %}
          {
            reference: “43534535345fd3434df”,
            careers:[
              {
                name:”Administración”.
                percentage: 25
              },
              {
                name:”Psicología”.
                percentage: 25
              }
            ],
            result:“https://descubre.usil.edu.pe/test/que-estudiar/graicas.php?reference=dfdf33df....”
          }

      {% endhighlight %}

## Agregar nueva institución

Para agregar 1 institución adicional que use test express, se tiene que editar un dato de la tabla **institution**  
- Busca en la tabla **institution**   el nombre de la institución que quieres editar, por ejemplo  `select * from institution where name like '%paraguay%';`
- Verificar que exista la institución y copiar su **id** para que lo puedas actualizar o puedes agragar una nueva.
- Una vez que tienes un resultado, tienes la columna **test_product**, por defecto es **0**, significa que no puede ser usado con producto test express, pero si se quiere que la institución pueda utilizar test epxress se tiene que **cambiar por valor a 1**.  `update institution set test_product = 1 where id = '42bf2a5f-2167-11eb-903e-027ec83d3421';`
