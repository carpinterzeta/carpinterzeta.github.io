---
title: "Compilando Aseprite en Ubuntu"
description: "Descubre como compilar el programa de edición pixel art Aseprite en Ubutnu"
publishDate: 2024-11-05
tags: ["tutorial","aseprite","pixel art","ubuntu","compilar","recursos"]
---

En mis aventuras como aprendiz de desarrollo de videojuegos y curioso profesional, me he topado con la necesidad de realizar algunas animaciones e ilustraciones del tipo pixel art.
Pueden generarse con [Krita](https://krita.org/es/), [Gimp](https://www.gimp.org/), realizando algunas modificaciones en fondos y pinceles, pero hay una aplicación específica (una entre otras muchas). En este caso hablamos de [Aseprite](https://www.aseprite.org/).
Un editor de sprites y una herramienta para diseño de pixel art.

A través de su web podemos adquirir el software para Linux, Mac o Windows por 19,99$. Pero en sus términos y condiciones nos dicen lo siguiente:

> If Aseprite source code is available, how is that you are selling it?

> Aseprite started being open source since its very beginning in 2001, and we were happy with that until August 2016. Now you can still download its source code, compile it, and use it for your personal purposes. You can make commercial art/assets with it too. The only restriction in Aseprite EULA is that you cannot redistribute Aseprite to third parties.""

Una vez fueron open source, pero podemos descargar su código, compilarlo y usar la aplicación sin mayor restricción que su redistribución.

Así que me dije, ¡Pues vamos a compilar!

Todo listo para empezar a leer la documentación para la instalación en el [Github de Aseprite](https://github.com/aseprite/aseprite/blob/main/INSTALL.md):

- Plataforma: Linux Ubuntu Bionic 18.04
- Compilador front end para C y C++ clang 10.0
- Dependencias necesarias:
  _ Git
  _ Cmake
  \_ Versión compilada de [Skia library](https://github.com/aseprite/skia#readme).
  [pre-built packages disponibles](https://github.com/aseprite/skia/releases). Esto significa que descargas la versión pre-built y te ahorras compilar el paquete tú. El que tienes que descargar exactamente es `aseprite-m102`. Lo descargas, lo descomprimes en la ruta `$HOME/deps/skia` o en la ruta que prefieras, pero recuerda que tendrás que modificar algún comando de abajo.
  - Para instalar las dependencias requeridas:
    `sudo apt-get install -y g++ clang libc++-dev libc++abi-dev cmake ninja-build libx11-dev libxcursor-dev libxi-dev libgl1-mesa-dev libfontconfig1-dev git`

# A compilar

Hora de usar clang y libc++-.
Creamos una carpeta llamada build dentro de la carpeta que hemos descargado de aserprite:

    cd aseprite
    mkdir build
    cd build

Ejecutamos el siguiente código para compilar:

    export CC=clang
    export CXX=clang++
    cmake \
      -DCMAKE_BUILD_TYPE=RelWithDebInfo \
      -DCMAKE_CXX_FLAGS:STRING=-stdlib=libc++ \
      -DCMAKE_EXE_LINKER_FLAGS:STRING=-stdlib=libc++ \
      -DLAF_BACKEND=skia \
      -DSKIA_DIR=$HOME/deps/skia \
      -DSKIA_LIBRARY_DIR=$HOME/deps/skia/out/Release-x64 \
      -DSKIA_LIBRARY=$HOME/deps/skia/out/Release-x64/libskia.a \
      -G Ninja \

Recuerda que si cambias la ruta donde descomprimiste los archivos de la versión compilada de skia, tendrás que actualizar la ruta de estos tres directorios

- DSKIA_DIR=$HOME/deps/skia \
- DSKIA_LIBRARY_DIR=$HOME/deps/skia/out/Release-x64 \
- DSKIA_LIBRARY=$HOME/deps/skia/out/Release-x64/libskia.a \

Y por último:

    ninja aseprite

Una vez ejecutado estos pasos (no te asustes, tarda su tiempo), podrás ejectuar aseprite dentro de la carpeta bin en el directorio build que creaste.
`~/"tunombredeusuario/aseprite/build/bin/`
Y ahí ejecutas `./aseprite`

Tienes todas las instrucciones en el archivo [INSTALL.md](https://github.com/aseprite/aseprite/blob/main/INSTALL.md) que se descarga desde el Github de Aseprite, o lo puedes consultar en el enlace.

Con eso tendrías ya una versión compilada de Aseprite, funcional en Ubuntu. Podrías crear un alias para ejectuar el programa o bien crear un acceso directo.

Muchas gracias por leer y hasta la próxima.
