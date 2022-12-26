---
layout: page
title: Entrega de dominios
permalink: /Entrega de dominios/
parent: Documentación funcional
grand_parent: Features
nav_order: 4
---

<details open markdown="block">
  <summary>
    Índice:
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Enlazar Namecheap con AWS

Configuración actual de Route 53 de aws.

![My helpful screenshot](https://cdn.discordapp.com/attachments/986727585381752863/1056944259737075772/image.png)

1. Al crear el Route53 aws te brindará DNS
2. Eso DNS los colocas en Namecheap
3. En nuestro caso nosotros manejamos con ApiGateway y cloudfront para colocar subdominios con CNAME.

Puede ver más detalle de como conectar en este tutorial:
1. [Tutorial 1](https://www.namecheap.com/support/knowledgebase/article.aspx/10371/2208/how-do-i-link-my-domain-to-amazon-web-services/){:target="_blank"}
2. [Tutorial 2](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/migrate-dns-domain-in-use.html){:target="_blank"}

# Cuadro de subdominio con los diferentes artefactos.

| Domio | Artefacto |
|-------|--------|
| https://queestudiar.la | Queestudiar Web |
| https://orientacion.queestudiar.la | Queestudiar Estudiante |
| https://school.queestudiar.la | Queestudiar Colegio |
| https://usil.queestudiar.la | Queestdiar USIL |
