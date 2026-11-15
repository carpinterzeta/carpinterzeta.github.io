---
title: "Listado de comandos útiles en SSH"
publishDate: 2025-12-24
draft: false
description: Una recopilación de comandos útles en SSH que tengo siempre que buscar porque no soy capaz de memorizarlos.
tags: ["Terminal", "Atajos", "SSH", "Seguridad", "Keygen", "Tutorial", "Servidor"]
---
Para añadir nuestra clave pública en las conexiones ssh del servidor/servicio que queramos:

```ssh-copy-id usuario@ipdelservidor```

**Ya tenemos que tener generada una clave ssh.
Si no lo tenemos y queremos generarla:
```ssh-keygen -t ed25519 -C "nombredeclave"```

Donde ed25519 es el algoritmo de encriptado de la clave.

Esta entrada ser irá actualizando. Fecha de la última actualización: 24 de diciembre 2025.

