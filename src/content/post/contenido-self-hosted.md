---
title: "Aplicaciones y servicios autoalojados en mi servidor casero"
publishDate: 2025-08-02
draft: false
description: "Selección de aplicaciones y servicios que tengo autoalojados en mi servidor casero"
tags:
  [
    "Recopilación",
    "Aplicaciones",
    "docker",
    "Self-hosted",
    "Autoalojado",
    "Servidor casero",
  ]
---

Por aquí dejo un listado del equipo y el software que utilizo para los servicios que tengo autoalojados. Me permiten tener un mayor control sobre mi privacidad, gestionar mis documentos y notas, música, videos, fotos, etc.
Suelo levantar los servicios mediante docker en diferentes máquinas virtuales (en Debian y Alpine Linux sobre todo)
Proxmox también me permite "cacharrear" a buenos niveles de intensidad, así como tener los diferentes servicios encapsulados y separados junto a un sistema fiable y robusto de copias de seguridad.

**Equipo**: Un minipc con un procesador Intel N100 y 16gb de RAM.

**Sistema operativo**: [Proxmox Virtual Environment](https://www.proxmox.com)

## Stack de bloqueo de publicidad y protección DNS:

- **[DNSCrypt-proxy](https://www.dnscrypt.org/)**: Una aplicación proxy de cifrado de las peticiones DNS.
- **[Pihole](https://pi-hole.net/)**: Aplicación de bloqueo de publicidad.
- **[Cloudflared](https://github.com/cloudflare/cloudflared)**: Aplicación de cifrado de DNS sobre HTTPS

## Conexiones y VPN

- [**Wireguard**](https://www.wireguard.com/): como servicio VPN
- [**DuckDNS**](https://hub.docker.com/r/linuxserver/duckdns): actualiza la IP a la que apunta un subdominio de DuckDNS

## Notas

En esta parte me encanta ir probando servicios. En esta ocasión tengo en pruebas los siguientes:

- [**Docmost**](https://github.com/Docmost/docmost)
- [**Joplin**](https://joplinapp.org/)

Es cierto que Joplin me permite una mayor libertad de sincronización, ya que cuenta con [aplicación para Android.](https://f-droid.org/packages/net.cozic.joplin/).

## Música e imágenes

- [**Navidrome**](https://www.navidrome.org/): servidor propio de música.
- [**Immich**](https://immich.app/): servicio que me permite tener imagenes y videos subidos en el servidor y sincronizado entre dispositivos.

## Otros

- [**Transmission** ](https://transmissionbt.com/)un gestor de descargas de torrents.

\*_Actualizado a fecha de 2 de agosto de 2025_