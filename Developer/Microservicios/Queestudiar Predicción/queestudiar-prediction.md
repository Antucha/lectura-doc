---
layout: page
title: Queestudiar Predicción
permalink: /Queestudiar Predicción/
parent: Microservicios
grand_parent: Developer
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


# Variables de entorno

| Variables                   | Valor                                 | Descripción |
| -----------                 | -----------                           | ----------- |
| DIRECTORY_PERSONALITY_CSV                  | ./lib/data/personalidad.csv                                 | Directorio del documento personalidad.csv  |
| DIRECTORY_PERSONALITY_3_CSV                  | ./lib/data/personalidad3.csv                                 | Directorio del documento personalidad3.csv  |
| DIRECTORY_VOCATION_3                  | ./lib/data/vocacion3.csv                                 | Directorio del documento vocacion3.csv  |
| DIRECTORY_VOCATION_2                  | ./lib/data/vocacion2.csv                                 | Directorio del documento vocacion2.csv  |
| DIRECTORY_PERSONALITY_PLK                  | lib/models/personality.pkl                                 | Directorio del documento personality.pkl  |
| DIRECTORY_VOCATION_PLK                  | lib/models/vocation.pkl                                 | Directorio del documento vocation.pkl |
| DATA_PERSONALITY_PLK                  | lib/models/dataStandardizePersonality.pkl                                 | Directorio del documento dataStandardizePersonality.pkl   |
| DATA_VOCATION_PLK                  | lib/models/dataStandardizeVocation.pkl                                 | Directorio del documento dataStandardizeVocation.pkl  |


# Instalar las dependencias
Se debe correr el siguiente comando: `python3 build_model.py`

# Iniciar la app
Se debe correr el siguiente comando: `python3 app.py`


# Generar predicción [POST]
Ruta: `{host}/predict/personality`

# Ver resultados [POST]
Ruta: `{host}/predict/vocational-result`
