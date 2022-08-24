---
layout: page
title: Api Queestudiar
permalink: /Api Queestudiar/
parent: Microservicios
grand_parent: Developer
nav_order: 0
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

# Loguin [POST]
La ruta en **producción** es la siguiente:
`https://service.qeestudiar.com/metric`


La ruta en **modo de desarollo** es la siguiente:
`http://localhost:2000/metric`

La notación para el acceso a cualquiera de las rutas será de la siguiente namera: `"{host}/"`

# Loguin [POST]
Ruta: `{host}/api/auth/login`

# Registro [POST]
Ruta: `{host}/api/auth/register`

# Verificar número de celular [POST]
Ruta: `{host}/api/auth/verify-number`

# Guardar contraseña [POST]
Ruta: `{host}/api/auth/recover`

# Extraer contraseña [GET]
Ruta: `{host}/api/auth/recover`

# Verificar contraseña [POST]
Ruta: `{host}/api/auth/recover/validate`

# Loguin social [POST]
Ruta: `{host}/api/auth/social/:social`

# Register V2 [POST]
Ruta: `{host}/api/v2/auth/register`

# Extraer atributos de un estudiante [GET]
Ruta: `{host}/api/student/attribute`

# Extraer carreras filtradas [GET]
Ruta: `{host}/api/student/careers-filter`

# Enroll [POST]
Ruta: `{host}/api/student/enroll`

# Enroll [GET]
Ruta: `{host}/api/student/enroll`

# Ectraer perfil de un estudiante [POST]
Ruta: `{host}/api/student/:studentId`

# Actualizar data de un estudiante [PUT]
Ruta: `{host}/api/student`

# Agregar atributo a un estudiante [POST]
Ruta: `{host}/api/student/:studentId/attribute`

# Extraer la guía vocacional [GET]
Ruta: `{host}/api/vocational`

# Extraer todos los atributos [GET]
Ruta: `{host}/api/vocational/personality/attribute`

# Buscar institución [GET]
Ruta: `{host}/api/vocational/professional`

# Extraer personalidad [GET]
Ruta: `{host}/api/vocational/personality/:type`

# Extraer inteligencia [GET]
Ruta: `{host}/api/vocational/intelligences`

# Extraer preguntas de personalidad [GET]
Ruta: `{host}/api/vocational/questions/personality`

# Extraer último resultado [GET]
Ruta: `{host}/api/vocational/last-result`

# Extraer último resultado de talento [GET]
Ruta: `{host}/api/vocational/last-result-talent`

# Extraer preguntas [GET]
Ruta: `{host}/api/vocational/questions/:vocationalId`

# Extraer resultados de progreso [GET]
Ruta: `{host}/api/vocational/progress/result`

# Actualizar referencia completa [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId/reference`

# Actualizar progreso vocacional complero [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId`

# Extraer datos personales de progreso institucional [GET]
Ruta: `{host}/api/vocational/progress/personality/:id`

# Extraer datos de progreso [GET]
Ruta: `{host}/api/vocational/progress/:vocationalId/public`

# Extraer datos de progreso  personal[GET]
Ruta: `{host}/api/vocational/progress/:vocationalId`

# Extraer atributo vovacional [GET]
Ruta: `{host}/api/vocational/vocations-attributes`

# Extraer progreso [GET]
Ruta: `{host}/api/vocational/progress`

# Enviar información [POST]
Ruta: `{host}/api/membership/information`

# Activar membresías de escuelas [GET]
Ruta: `{host}/api/membership/school`

# Verificar código de colegio [GET]
Ruta: `{host}/api/membership/verification`

# Actualizar estudiante [POST]
Ruta: `{host}/api/data-update/student`

# Extraer lista [GET]
Ruta: `{host}/api/school`

# Validar alianza [GET]
Ruta: `{host}/api/school/alliance/:allianceId`

# Buscar estudiante [GET]
Ruta: `{host}/api/school/student`

# Configuraciónvocacional [PUT]
Ruta: `{host}/api/school/vocational/config`

# Extraer último resultado [GET]
Ruta: `{host}/api/school/vocational/last-result`

# Extraer dashborad de institución [GET]
Ruta: `{host}/api/school/dashboard/institution`

# Extraer dashboard de carreras [GET]
Ruta: `{host}/api/school/dashboard/career`

# Lista de usuarios [GET]
Ruta: `{host}/api/school/:id/user`

# Crear usuario [POST]
Ruta: `{host}/api/school/:id/user`

# Crear código de escuelas [POST]
Ruta: `{host}/api/school/:id/school-code`

# Buscar institución [GET]
Ruta: `{host}/api/institution`

# Buscar estudiante [GET]
Ruta: `{host}/api/institution/student`

# Extraer carreras de instituciones [GET]
Ruta: `{host}/api/sitemap/institution/careers`

# Extraer carreras [GET]
Ruta: `{host}/api/institution/careers`

# Actualizar institución [PUT]
Ruta: `{host}/api/institution`

# Agregar carreras [POST]
Ruta: `{host}/api/institution/career/:careerId`

# Actualizar carreras [PUT]
Ruta: `{host}/api/institution/career/:careerId`

# Borrar carreras [DELETE]
Ruta: `{host}/api/institution/career/:careerId`

# Extraer carreras [GET]
Ruta: `{host}/api/institution/career/:careerId`

# Agregar curriculum de carrera por institución [POST]
Ruta: `{host}/api/institution/career/:careerId/curriculum`

# Extraer curriculum de carrera por institución [GET]
Ruta: `{host}/api/institution/career/:careerId/curriculum`

# Eliminar curriculum de carrera [DELETE]
Ruta: `{host}/api/institution/career/:careerId/curriculum/:curriculumId`

# Agregar modalidad [POST]
Ruta: `{host}/api/institution/modality`

# Borrar modalidad [DELETE]
Ruta: `{host}/api/institution/modality/:modalityId`

# Borrar localización [GET]
Ruta: `{host}/api/institution/location/:locationId`

# Agregar localización [POST]
Ruta: `{host}/api/institution/location`

# Extraer inscripción [GET]
Ruta: `{host}/api/institution/leads`

# Exytaer inscrición a conferencia [GET]
Ruta: `{host}/api/institution/leads-conference`

# Extraer detalles de modalidad [GET]
Ruta: `{host}/api/institution/:username/modality/:id`

# Extraer perfil [GET]
Ruta: `{host}/api/institution/:username`

# Extraer localización [GET]
Ruta: `{host}/api/institution/:username/location`

# Extraer carreras [GET]
Ruta: `{host}/api/institution/:username/career`

# Extraer modalidad [GET]
Ruta: `{host}/api/institution/:username/modality`

# Extraer modalidad por id [GET]
Ruta: `{host}/api/institution/:username/career/:slug`

# Enviar notificaciones express [POST]
Ruta: `{host}/api/institution/notification/express`

# Enviar notificaciones SMS [POST]
Ruta: `{host}/api/institution/notification`

# Estado de las notificaciones [GET]
Ruta: `{host}/api/institution/status-notification/:referenceId`

# Validar código de teléfono [GET]
Ruta: `{host}/api/institution/notification/validate`

# Extraer todas las referencias [GET]
Ruta: `{host}/api/institution/notification/reference`

# Buscar carrera [GET]
Ruta: `{host}/api/career/search`

# Extraer instituciones [GET]
Ruta: `{host}/api/career/:slug`

# Extraer todas las carreras [GET]
Ruta: `{host}/api/career`

# Enviar notificación [GET]
Ruta: `{host}/api//cron/notification/phone`

# Scraping [GET]
Ruta: `{host}/api/cron/scrapping`

# Scrapping e-mail [GET]
Ruta: `{host}/api/cron/scrapping-email`

# Extraer referencia de precios [GET]
Ruta: `{host}/api/cron/update-price-reference`

# Pagar [POST]
Ruta: `{host}/api/payment`

# Procesar pago [PUT]
Ruta: `{host}/api/payment`

# Extraer progreso de un colegio [GET]
Ruta: `{host}/api/school/student/:studentId/vocational/progress/:vocationalId`

# Extraer preguntas de un colegio [GET]
Ruta: `{host}/api/school/student/:studentId/vocational/questions/:vocationalId`

# Extraer todo [GET]
Ruta: `{host}/api/conference`

# Inscribir a un estudiante [POST]
Ruta: `{host}/api/conference/student`

# Extraer usuario activo [POST]
Ruta: `{host}/api/mailing/activecampaign/blog`