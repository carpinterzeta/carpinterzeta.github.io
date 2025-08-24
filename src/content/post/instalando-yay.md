---
title: "Instalando Yay"
description: "Instalando el gestor de paquetes del Arch User Repository más famoso" 
publishDate: 2024-05-13
tags: ["tutorial","arch","yay"]
---

En esta entrada corta quiero dejar reflejado el proceso de instalación del helper [yay](https://aur.archlinux.org/yay.git) de Arch Linux. Un helper es una herramienta que facilita la gestión en la instalación y mantenimiento de los paquetes AUR (abreviatura de [Arch User Repository](https://wiki.archlinux.org/title/Arch_User_Repository_(Espa%C3%B1ol))), donde la comunidad sube las descripciones de los paquetes (PKGBUILD) que permiten compilar un paquete desde código fuente con makepkg para su posterior instalación con pacman.

Los pasos serían los siguientes:
1. Actualizar paquetes y sincronizar repositorios de pacman
```
sudo pacman -Syu
```
2. Instalar los paquetes base-devel y git necesiarios para la gestión e instalación de yay
```
sudo pacman -S base-devel git
```
3. Clonar el repositorio de yay
```
git clone https://aur.archlinux.org/yay.git
```
4. Entrar al directorio clonado y compilar el código fuente:
```
cd yay

makepkg -si
```
Aceptando las preguntas en la instalación ya habríamos finalizado la instalación y podríamos proceder a instalar paquetes AUR.

En próximas entregas indagaremos en los diferentes comandos y funcionalidades que nos ofrece yay.

Gracias por leer :)
krpntrz.




