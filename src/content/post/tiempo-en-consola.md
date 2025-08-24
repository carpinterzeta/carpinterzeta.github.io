---
title: "Viendo el tiempo en consola con Wttr"
description: "Aprende a chequear el tiempo que hace a través de la consola con esta herramienta."
publishDate: 2025-08-02
tags: ["tutorial", "wttr", "consola", "alacritty", "arch"]
---

En esta entrada rápida quiero compartir un recurso para chequear el reporte del tiempo directamente en consola, de forma muy rápida.
El servicio que vamos a estar utilizando es [wttr.in](wwttr.in), un recurso creado por _Igor Chubin_.
Aquí podéis revisar el repositorio del [proyecto](https://github.com/chubin/wttr.in).

En mi caso he creado un alias en _.zshrc_ (esto me lleva a pensar en futuras entradas sobre cambiar la SHELL por defecto de Arch y explicar que es zsh y cómo manejarla.)
Pero también puedes recrear los pasos de gestión de alias si tu SHELL por defecto es BASH, editando y añadiendo el alias en .bashrc

El servicio en cuestión mediante un curl te muestra el tiempo en formato ASCI.

Por ejemplo:

```
curl wttr.in

```

Mostraría el tiempo de la ubicación de tu ip:

```
Weather report: *ubicación de tu ip*

     \  /       Partly cloudy
   _ /"".-.     21 °C
     \_(   ).   ← 11 km/h
     /(___(__)  10 km
                0.2 mm
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤  Sun 09 Jun ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│  _`/"".-.     Patchy rain ne…│  _`/"".-.     Patchy rain ne…│     \   /     Sunny          │     \   /     Sunny          │
│   ,\_(   ).   19 °C          │   ,\_(   ).   +27(28) °C     │      .-.      +27(28) °C     │      .-.      21 °C          │
│    /(___(__)  ↖ 15-23 km/h   │    /(___(__)  ↗ 26-31 km/h   │   ― (   ) ―   → 10-14 km/h   │   ― (   ) ―   ← 5-11 km/h    │
│      ‘ ‘ ‘ ‘  10 km          │      ‘ ‘ ‘ ‘  10 km          │      `-’      10 km          │      `-’      10 km          │
│     ‘ ‘ ‘ ‘   0.0 mm | 70%   │     ‘ ‘ ‘ ‘   0.0 mm | 69%   │     /   \     0.0 mm | 0%    │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤  Mon 10 Jun ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│  _`/"".-.     Patchy rain ne…│    \  /       Partly Cloudy  │  _`/"".-.     Moderate rain …│  _`/"".-.     Patchy rain ne…│
│   ,\_(   ).   21 °C          │  _ /"".-.     +23(25) °C     │   ,\_(   ).   19 °C          │   ,\_(   ).   17 °C          │
│    /(___(__)  ↑ 7-11 km/h    │    \_(   ).   ↑ 10-14 km/h   │    /(___(__)  ↗ 9-14 km/h    │    /(___(__)  ↖ 12-24 km/h   │
│      ‘ ‘ ‘ ‘  10 km          │    /(___(__)  10 km          │    ‚‘‚‘‚‘‚‘   8 km           │      ‘ ‘ ‘ ‘  10 km          │
│     ‘ ‘ ‘ ‘   0.1 mm | 100%  │               0.0 mm | 0%    │    ‚’‚’‚’‚’   3.7 mm | 100%  │     ‘ ‘ ‘ ‘   0.1 mm | 100%  │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘
                                                       ┌─────────────┐
┌──────────────────────────────┬───────────────────────┤  Tue 11 Jun ├───────────────────────┬──────────────────────────────┐
│            Morning           │             Noon      └──────┬──────┘     Evening           │             Night            │
├──────────────────────────────┼──────────────────────────────┼──────────────────────────────┼──────────────────────────────┤
│    \  /       Partly Cloudy  │  _`/"".-.     Patchy light d…│  _`/"".-.     Patchy rain ne…│     \   /     Sunny          │
│  _ /"".-.     +23(25) °C     │   ,\_(   ).   +24(26) °C     │   ,\_(   ).   +23(25) °C     │      .-.      17 °C          │
│    \_(   ).   ↑ 15-17 km/h   │    /(___(__)  ↗ 18-24 km/h   │    /(___(__)  ↑ 14-26 km/h   │   ― (   ) ―   ↗ 9-19 km/h    │
│    /(___(__)  10 km          │      ‘ ‘ ‘ ‘  5 km           │      ‘ ‘ ‘ ‘  9 km           │      `-’      10 km          │
│               0.0 mm | 0%    │     ‘ ‘ ‘ ‘   0.7 mm | 100%  │     ‘ ‘ ‘ ‘   1.4 mm | 100%  │     /   \     0.0 mm | 0%    │
└──────────────────────────────┴──────────────────────────────┴──────────────────────────────┴──────────────────────────────┘

Follow @igor_chubin for wttr.in updates

```

Puedes indicar directamente una localización con el nombre de la ciudad:

```
culr wttr.in/madrid
```

El alias en cuestión sería el siguiente:

```
alias tiempo='curl wttr.in/madrid'
```

Una vez guardado y en una nueva instancia de la terminal, podremos escribir "tiempo" y aparecerá el bonito reporte.

Este servicio _wttr.in_ he visto que se usa mucho para extraer información del tiempo y "pintarlo" mediante scripts en las barras de estado tipo sway/polybar/i3status y similares.

Gracias por leer
