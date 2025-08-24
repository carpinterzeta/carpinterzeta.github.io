---
title: "Instalando GrapheneOS"
publishDate: 2024-11-24
tags: ["grapheneOS", "recursos", "tutorial", "software libre", "móvil", "F-droid"]
description: "Aprende a instalar el sistema operativo para móviles Android, GrapheneOS basado en la privacidad" 
---

Usaré esta publicación como repositorio de aplicaciones y procedimientos para instalar Graphene OS.
La idea es mantener un sistema minimalista y con un uso controlado.

#### Dispositivo: Pixel 7 Pro

#### Sistema operativo previo: Android 15

Pasos:

- **Habilitar Desbloqueo de OEM** -> está en los opciones de desarrollador, que se activan pulsándooslo 5 veces en la opción “Número de compilación” en Ajustes -> Información del teléfono.

- Seguir todos los pasos de la **[instalación web](https://grapheneos.org/install/web)**
- **IMPORTANTE**: lee bien la documentación y utiliza el navegador y las dependencias que necesites en función del sistema operativo que estés utilizando para realizar el proceso. - Estos pasos consisten en ir haciendo click en los pasos y manipulando el teléfono: - Desbloqueo de bootloader en el teléfono - Flash de la imagen en función del dispositivo pixel que tengamos conectado. - Bloqueo de bootlader de nuevo - Y por arte de magia ya está instalado.
  Recuerdo aquellos tiempos en los que este proceso de instalación de otras imágenes de android… tiempos en los que falsear manualmente, TWRP… el Nexus 4 con su flamante Lineage / Carbon ROM…

El siguiente paso es ya la configuración del sistema operativo del teléfono, y luego ya tomar decisiones sobre si necesitamos tener los servicios de Google Apps (encapsulados en este caso en el teléfono, sin posibilidad de recopilación de datos, más allá de los que nosotros decidámosla aceptar)

**Listado de aplicaciones privativas/ Fuente Google Play (+ alternativa en F-Droid)**

- Banca (Solo Google Play)
- Gmail (Thunderbird)
- Tiempo (Breezy Weather)
- Twitch (Twire)
- Youtube (NewPipe)
- Whatsapp (Solo Google Play)
- Google Maps (Organic Maps)

**Listado de aplicaciones no privativas / Fuente: [F-Droid](https://f-droid.org/)**

- Moshidon
- Bitwarden (necesario añadir [repositorio adicional en F-Droid](https://mobileapp.bitwarden.com/fdroid/repo))
- Telegram
- Lagrange
- Disroot
- Firefox

Esta será una entrada viva, así que se irá actualizando en función de la evolución de la configuración de Graphene OS y las aplicaciones que vaya utilizándo.

## Actualización 25/11/2024

Gracias al feedback de [Pedro J. Hdez](https://mastodon.social/deck/@ecosdelfuturo@mstdn.social) recibido a través de Mastodon, os dejo por aquí los comentarios que han realizado los desarrolladores de GrapheneOs respecto a su opinión sobre qué tienda de aplicaciones es más seguro usar:

1. **Los desarrolladores recomiendan instalar desde los servicios de Play Store (desde el entorno seguro que proporciona GrapheneOS)** por encima de Aurora y por encima de F-Droid debido a la falta de transparencia respecto a la verificación de firmas. [(Fuente)](https://xcancel.com/GrapheneOS/status/1803185925112934533)
2. En el foro de soporte de Graphene, los desarrolladores vuelven a insistir en que **los metadatos de los repositorios de F-Droid está mal diseñado y tiene fallas graves de seguridad**. [(Fuente)](https://discuss.grapheneos.org/d/14452-how-to-explain-why-accrescent-over-f-droid/19)

Tras revisar esta nueva información, lo más lógico sería utilizar aquellas aplicaciones que estén disponibles en [Accrescent](https://accrescent.app/) mediante la instalación de esta tienda a través de la App Store de Graphene. Para aquellas apps no disponibles en Accrescent, instalar a través de Google Play en el entorno seguro.
Luego dependiendo de las necesidades de seguridad de cada persona, podremos jugar con diferentes perfiles, para tener un mayor control y estanqueidad de los permisos.

Gracias por leer :)
