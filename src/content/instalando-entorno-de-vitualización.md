---
title: Instalando un entorno de virtualización en Fedora, Debian y dervidadas.
date: 2026-11-21
draft: false
description: Pasos para instalar un entorno de virtualizacion en Fedora, Arch Linux y Debian (y sus derivadas).
tags:
  - Fedora
  - Linux
  - Tutorial
  - Virtualización
  - virt-manager
  - Debian
---


Creo que la mayoría de mis visitas a este rincón de internet, más allá de releer las entradas publicadas para corregir errores de ortografía y errores tipográfico, suele ser para revisar y reutilizar comandos para procesos que realizo de vez en cuando y que todavía no he memorizado del todo. Por ejemplo, [Cómo usar el comando dd](https://carpinterzeta.com/c%C3%B3mo-usar-dd-para-grabar-im%C3%A1genes-.iso-en-memorias-usb/) o [SCP, qué es y cómo usarlo](https://carpinterzeta.com/scp-qu%C3%A9-es-y-c%C3%B3mo-usarlo/).

Pues bien, hoy toca otra de esas entradas que se que revisitaré en el futuro. Cómo instalar un entorno de virtualización en Fedora (en algún momento actualizaré la entrada para )

En el caso de Fedora, estos serían los comandos:

Para instalar las dependencias necesarias:
```
sudo dnf install @virtualization
```

Inicializamos y habilitamos el servicio de virtualización:
```
sudo systemctl start libvirtd
```
```
sudo systemctl enable libvirtd
```

Para verificar que todo está correcto ejecutamos:

```
lsmod | grep kvm
```
Si muestra en salida kvm_intel o kvm_amd, KVM ya estaría correcto.

Ahora podríamos utilizar la línea de comandos con la orden ```virt-install``` o si prefieres interfaz de usuario, puedes ejecutar la aplicación virt-manager.

En el caso de Debian y el resto de distribuciones basadas en Debian, que utilicen Aptitude (apt) como gestores de paquetes, los comandos a utilizar serían los siguientes:

```
sudo apt update && sudo apt upgrade
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager
sudo systemctl start libvirtd
sudo systemctl enable libvirtd
```

Con estos comandos, actualizamos la base de datos y los paquetes que tenemos intalados.
Con el segundo instalamos las dependencias necesarias para la virtualización.

```qemu-system:q``` instala los módulos y herramientas de KVM (Kernel-bassed Virtual Machine)

```libvirt-daemon-system``` y ```libvirt-clients``` gestionan los servicios de virtualización.

```virt-manager``` es la interfaz gráfica para crear y conectar con las máquinas virtuales.

```bridge-utils``` gestiona y ayuda en la configuración de máquinas virtuales.


- Documentación oficial de Fedora:
	- [Virtualización – una Reseña](https://docs.fedoraproject.org/es/quick-docs/virtualization-an-overview/)
	- [Virtualización - Emperzar](https://docs.fedoraproject.org/es/quick-docs/virtualization-getting-started/)
- Documentación oficial de Debian
	- https://wiki.debian.org/KVM