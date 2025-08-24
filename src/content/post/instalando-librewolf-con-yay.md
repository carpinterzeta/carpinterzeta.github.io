---
title: "Instalando Librewolf con yay"
description: "Aprende a instalar el navegador Librewolf, un navegador centrado en la seguridad y la privacidad."
publishDate: 2024-05-25
tags: ["tutorial","arch","yay","navegador","librewolf","OpenSource"]
draft: false
---

## [Librewolf](https://librewolf.net/) es un navegador basado en Firefox, que se centra en la seguridad, la privacidad y la libertad.

Es un proyecto independiente del navegador del zorro. Busca aumentar la protección contra el rastreo. Sus características principales son:

- No tiene telemetría
- Basado en búsqueda privada con DuckDuckGo, Searx y Quant
- Tiene el bloquedor uBlock Origin incluido por defecto
- Código abierto, por supuesto :)

En tu sistema arch según la [documentación](https://librewolf.net/installation/arch/) de Librewolf podemos utilizar el helper **yay** (puedes consultar cómo instalar este helper en [esta entrada](https://krpntrz.xyz/instalando-yay/))

A mi me ha dado problemas la orden:

```
yay -S librewolf
```

Intuyo que por un problema de firmas. Pero no estoy totalmente seguro.

Lo he solucionado instalando en su lugar este paquete:

```
yay -S librewolf-bin
```

Gracias por leer!
Krpntrz.
