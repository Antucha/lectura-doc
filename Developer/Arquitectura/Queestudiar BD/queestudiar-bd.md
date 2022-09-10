---
layout: page
title: Queestudiar BD
permalink: /Queestudiar BD/
parent: Arquitectura
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

# Estructura
La estructura general de la base de datos está organizada en la siguiente tabla:

![](https://cdn.discordapp.com/attachments/955522800918085686/983476697632473108/unknown.png)

- Consta de 24 tablas enlistadas secuencialmente.
- No se utilizan las expresiones de llave primaria o llave foránea(sí existe el `id` de un registro, sin embarg no está predefinido como llave primaria ), con la intención de dar agilidad en la selección de datos.

![](https://cdn.discordapp.com/attachments/955522800918085686/983479643514503239/unknown.png)

Esta es una muestra de los campos que contempla una tabla en la base de datos.

# Diagrama entidad relación

A continuación se muestra el diagrama Entidad Relación de la base de datos.

![](https://cdn.discordapp.com/attachments/955522800918085686/983482003460595833/Diagrama.png)

(Debido a que la base de datos contiene una cantidad considerable de tablas y la relación que existe entre ellas es amplia, se optó por mostra solo un pequeño sector del diagrama, y dejar el [Link del descargable](https://cdn.discordapp.com/attachments/955522800918085686/983482231651717211/Dyagram_ER.mwb))

Considerando que la base de datos contiene una cantidad considerable de tablas y la relación que existe entre ellas es amplia, se optó por mostra solo un pequeño sector del diagrama, y dejar el [Link del descargable](https://cdn.discordapp.com/attachments/955522800918085686/983482231651717211/Dyagram_ER.mwb)

# Importación de datos desde un script

## Requisitos

Debe tener instalado los siguientes programas:

  1. MySQL
  1. MySQL WOrkbench
Además, se debe descargar el arrchivo queestudiar_db.sql almacenado en el siguiente drive: [Link del descargable](https://drive.google.com/drive/folders/1glzulQhp71g_m70aHn0Y9-37mcLMz1dz?usp=sharing)%7B:target=%22_blank%22%7D

## Importación

  1. Abrir el programa MySQL Workbench.
  2. En la pestaña Server acceder a la opción Data Import.
    ![](https://cdn.discordapp.com/attachments/955522800918085686/1017519711992430673/unknown.png)
  3. La pantalla lucirá de la siguiente manera.
    ![](https://cdn.discordapp.com/attachments/955522800918085686/1017520758215413792/unknown.png)
  4. Damos click en los tres puntos para seleccionar el archivo descargado queestudiar_db.sql.
    ![](https://cdn.discordapp.com/attachments/955522800918085686/1017521211661631580/unknown.png)
  5. Seleccionamos el archivo y click en Start Import.
  6. El proceso de importación demorará un tiempo considerable, luego tendremos un mensaje exitoso que lucirá de la siguiente manera.
    ![](https://cdn.discordapp.com/attachments/955522800918085686/1017513761407516672/unknown.png)
Imagen
Imagen
Imagen
Imagen

