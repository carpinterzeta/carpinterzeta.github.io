---
title: "SCP - Qué es y cómo usarlo"
publishDate: 2025-05-04
draft: false
description: "Cómo usar scp y en qué consiste"
tags: ["Herramientas", "SCP", "Linux", "Software libre"]
---

SCP son las siglas de Secure Copy Protocol y es una herramienta que se ejecuta desde la línea de comandos para copiar archivos entre diferentes máquinas dentro de una red, utilizando el puerto de SSH (Secure Shell) mediante el protocolo SFTP (Secure File Transfer Protocol).

SCP está basado en RCP (Remote File Copy) que apareció por primera vez en el sistema 4.2BSD

Estas son las opciones básicas que nos ofrece el manual de SCP:

`scp [other options] [source username@IP]:/[directory and file name] [destination username@IP]:/[destination directory]`

Vamos a analizar el siguiente código de ejemplo:

```
scp -r /home/user1/carpeta1 user2@192.168.1.90:/home/user2/
```

Indicamos que copiaremos de forma recursiva (incluyendo las carpetas) el directorio alojado en el escritorio de user1, en el escritorio de user2 en la máquina con ip 192.168.1.90

Como se puede apreciar, es una herramienta muy útil que nos permite un amplio margen de maniobra en la gestión de archivos a través de las diferenes máquinas en red.

Gracias por leer :)
