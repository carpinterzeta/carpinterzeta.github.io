---
title: "Soluciones de fin de mes"
description: "Hay veces que el tema tecnológico y más específicamente, el informático, es algo puñetero."
publishDate: 2024-12-25
tags: ["Teclado","Git","Novato","GRUB","Dual Boot" ]
---


Hay pequeñas cosas dejan de funcionar, ya sea por actualizaciones que "rompen", o por acciones que llevamos a cabo sin tener en cuenta las implicaciones que pueden tener en el sistema. (Esto último suele ser un copia/pega de código que hemos encontrado en Internet).

Pero no hay nada que una buena búsqueda solucione, foros, artículos en blogs, video-tutoriales... hay una infinidad de tiempo que ahorramos gracias a otras personas que han dedicado el suyo y sus recursos a aportar solución a estos problemas que nos asaltan a diario. 

Desde aquí solo quiero dar las gracias a todas las personas que comparten su sabiduría con la sociedad.

Y aquí dejo la sabiduría que he ido necesitando estos días pasados para un par de temas:

1. Instalar GRUB en la configuración de Arch Linux en un modelo de arranque doble con Windows 11. Al terminar el script de instalación de Arch, no se por qué, pero el gestor de arranque no se instala de forma correcta y hay que ejecutar unas operaciones en la terminal para poder lanzarlo correctamente en el arranque y que no sea el arranque de Windows el que tome el control. El método lo he sacado de este [artítulo de KSK Royal](https://kskroyal.com/arch-win11-dualboot-2024/).
    * Los comandos a ejecutar son los siguientes:
    
    ```pacman -S grub efibootmgr dosfstools mtools```
    
    ```grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB```
    

    ```grub-mkconfig -o /boot/grub/grub.cfg```
    
    * Una vez reiniciado, veremos que ya carga GRUB, pero no nos aparece la partición con el arranque de Windows. Para solucionarlo, tendremos que entrar dentro de nuestro sistema operativo e instalar os-prober: ```sudo pacman -Sy os-prober``
    
    * El siguiente paso es editar la configuración de GRUB en /etc/default/grub y descomentar la línea GRUB_DISABLE_OS_PROBER=false
    (en mi caso estaba al final del archivo, lo podéis editar con permisos root con vuestro editor de confianza.)
    
    * Ya el último paso el volver a regenerar la configuración de  grub y con os-prober ya nos detecta la entrada de Windows y nos lo añade al menú de arranque.
    ```grub-mkconfig -o /boot/grub/grub.cfg```
    

2. De pronto, la tecla Super me dejó de funcionar (en Arch/Gnome) y después de pensar en sacar un teclado nuevo, me dió por buscar y encontré la solución: estaba deshabilitada (o la había deshabilitado yo sin querer) y solo tenía que pulsar Fn + Super para volver a habilitarlo. Creo que la solución la encontré en un comentario de reddit, que ya soy incapaz de encontrar.


Felices fiestas y que la paz informática os acompañe en vuestras noches de cacharreo.

Gracias por leer :)


