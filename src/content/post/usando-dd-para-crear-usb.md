---
title: "Cómo usar dd para grabar imágenes .iso en memorias USB"
description: "Comando práctico de la herramienta dd para grabar imagenes .iso en memorias USB."
publishDate: 2025-09-07
tags: ["tutorial", "dd", "linux", "iso", "void-linux"]
draft: false
---

Como no puede ser de otra manera, ayer estaba trasteando con un equipo viejuno, quería instalar void linux y me propuse aprender a usar dd para grabar la imagen iso en un pendrive.

En lugar de usar otro tipo de herramientas que relizan el proceso mediante una interfaz gráfica, como pueden ser:
- [Balena Etcher](https://etcher.balena.io/)
- [Rufus](https://rufus.ie/es/) (para Windows)


Me propuse utilizar una herramienta que viene instalada por defecto en muchos sistemas: ```dd```. Se trata de un programa de la familia de los sistemas operativos UNIX (POSIX)

El proceso con ```dd``` en realidad es bien sencillo, tenemos por ejemplo los siguientes argumentos:

``` bash
dd bs=4M if=/ruta/de la imagen/ejemplo.iso of=/dev/sdx status=progress oflag=sync
```
Donde con ```bs``` especificamos el tamaño del bloque de datos, con ```if=``` la ruta donde está alojada la imagen del sistema operativo en formato .iso, en ```of=``` determinamos la ruta de la memoria usb, con ```status=progress``` nos mostrará el proceso en vivo del copiado de datos y un porcentaje y con ```oflag=sync``` sincroniza datos y metadatos en E/S.

Dejo por aquí unos enlaces a la documentación oficial de ```dd ```:

[https://www.gnu.org/software/coreutils/manual/html_node/dd-invocation.html](https://www.gnu.org/software/coreutils/manual/html_node/dd-invocation.html)


¡Muchas gracias por leer!
