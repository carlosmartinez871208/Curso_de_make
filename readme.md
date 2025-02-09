# Curso de Make
## Introducción.
### Bienvenida.
> Hola mi nombre es Carlos Martinez, me dedico al desarrollo de software embebido desde el 2015.
A lo largo de mi experiencia en distintas organizaciones, surge la necesidad de hacer este curso
para brindar las bases de cómo se usa esta herramienta para soluciones reales en diversas
plicaciones.

:metal: Bienvenidos :metal:

### Objetivo.
> * Asentar las bases de la herramienta Make y sus aplicaciones.

> Este curso es **bottom to top**: lo que significa que vamos a ir desde lo más esencial hasta lo más
complejo, de tal manera que el aprendizaje se vuelva acumulativo.

### Para quien es este curso.
> Este curso va dirigido a toda persona que quiera aprender las bases de **make** y como esta herramienta
nos permite automatizar procesos en la generación de archivos que no son código fuente a partir de 
archivos de código fuente.

> Se presentan diversos ejercicios de práctica para asentar mejor los conocimientos, despues de todo
este tipo de herramientas se aprenden practicando.

### Requisitos.
> Se requiere tener conocimientos basicos de lenguage C o C++.

### Links.
#### Make oficial site.
> https://www.gnu.org/software/make/
#### Manual.
> https://www.gnu.org/software/make/manual/make.pdf


## Set up
Para este curso debemos instalar las siguientes herramientas de desarrollo en nuestros equipos de computo.

> * Herramienta make.

> * Compilador de C/C++.

### Setup para Windows.
> Las herramientas de desarrollo, son paquetes de software necesarias para nosotros poder realizar nuestros proyectos de desarrollo de software.

**Nota: En el caso de windows lo normal es que estas no esten incluidas**

#### Verificamos si tenemos make instalado.
> Para verificar si tenemos **make** instalado, ingresamos en la terminal el siguiente comando:

	make --version

> En caso de ya tener **make** instalado, nos saldra un mensaje similar al siguiente:

![win_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_make_installed.png)

#### Verificamos si tenemos el compilador de C/C++ instalado.

> Para verificar si tenemos instalado el compilador para lenguage C, ingresamos el comando siguiente:

	gcc --version

o

> Para verificar si tenemos instalado el compilador para lenguage C++, ingresamos el comando siguiente:

	g++ --version

> En caso de ya tener instalado el compilador, nos saldra un mensaje similar al siguiente.

![win_compiler_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installed.png)

**Nota: Si este tu caso te puedes saltar esta sección.**

#### Instalación de las herramientas de desarrollo.

> Como ya antes se habia mencionado, lo mas común es que estas herramientas de desarrollo no esten instaladas en nuestro equipo,
> por lo que será necesario instalarlas.

> Si ingresamos el siguiente comando:

	make --version

> Al no tener **make** instalado nos regresaría en la terminal un mensaje similar al siguiente:

![win_no_make_tool](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_no_make_tool.png)

> De la misma manera, si ingresamos cualquiera de los siguientes comandos:

	gcc --version

o

	g++ --version

> Al no tener el compilador instalado nos regresaría en la terminal un mensaje similar al siguiente:

![win_no_compiler](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_no_compiler.png)

#### Instalación de make.

> Para instalar **make** usamos el siguiente comando:

	winget install ezwinports.make

![win_make_installation](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_make_installation.png)

> Verificamos la instalación, nuevamente ingresamos en la terminal el siguiente comando:

	make --version

![win_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_make_installed.png)

> Como podemos ver **make** ya ha sido instalado.

#### Instalación del compilador.
Para instalar el compilador, hacemos el siguiente proceso.

> 1. Navegamos al sitio oficial de MSYS2: https://www.msys2.org

> 2. Bajamos un poco hasta encontrar el instalador, damos clic en el enlace para descargar.

![win_compiler_installer](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installer.png)

> 3. Una vez descargado, damos doble clic en el ejecutable.

> 4. Especificamos el directorio **C:\msys64** (mi caso en particular) donde sera instalado MSYS2 y damos clic en **Next**.

![win_compiler_path](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_path.png)

> 5. Nos pide agregar un acceso directo y damos **Next** nuevamente.

![win_compiler_shortcut](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_shortcut.png)

> 6. Esperamos un tiempo para que se instale.

![win_compiler_installation](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installation.png)

> 7. Damos clic en **Finish** para terminar una vez instalado.

![win_compiler_done](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_done.png)

> 8. Dirigete al directorio de instalación y ejecuta **msys2.exe**.

![win_msys2_install](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_msys2_install.png)

> 9. Una consola comando se va a abrir, dentro de la consola ejecuta el comando **pacman -Syu** para actualizar las dependencias, al finalizar escribe la letra **Y** para terminar.

	pacman -Syu

![win_msys2_update](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_msys2_update.png)

> 10. Nuevamente nos dirigimos al directorio de instalación y ejecutamos nuevamente **msys2.exe**, ya con la consola abierta escribimos el comando **pacman -Su**, para actualizar las depedencias faltantes.

	pacman -Su

![win_msys2_upgrade](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_msys2_upgrade.png)

> 11. Nos dirigimos al directorio de instalacion y esta vez ejecutamos **mingw64.exe** para SO de 64 bits.

> Nota: usa **mingw32.exe** para SO de 32 bits.

![win_mingw_installer](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_mingw_installer.png)

> 12. Dentro de la consola que se ha abierto, escribimos el comando **pacman -S mingw-w64-x86_64-gcc** para SO de 64 bits.

> Nota: usa **pacman -S mingw-w64-i686-gcc** para SO de 32 bits.

	pacman -S mingw-w64-x86_64-gcc

o

	pacman -S mingw-w64-i686-gcc

![win_mingw_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_mingw_installed.png)

> 13. Copiamos el directorio de instalacion de mingw64 **C:\msys64\mingw64\bin** (mi caso en particular) y lo agregamos a las variables de entorno.
> > 13.1. Nos vamos a **Propiedades del sistema**: .
> > > 13.1.1. Ingresamos la tecla **windows** y escribimos **Propiedades del sistema.**.

![win_sys_settings](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings.png)

> > > > Damos doble clic en **Acerca de tu PC**, que nos abre la ventana de **Configuración**.

> > > 13.1.2. Dentro de la ventana de **Configuración**, al costado izquiero debajo de la opción de **Inicio**, encontraremos la opción de **Sistema** y le damos clic.

![win_sys_settings1](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings1.png)

> > > 13.1.3. Ya dentro de la ventana **Sistema**, vamos descartando las opciones hasta encontrar la opción: **Información**.

![win_sys_settings2](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings2.png)

> > > > Damos clic en **Información**.

> > > 13.1.4. Una vez seleccionada la opcion información, buscamos **Configuración avanzada del sistema**.

![win_sys_settings3](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings3.png)

> > > > Damos clic en **Configuración avanzada del sistema**, esto nos va a abrir la ventana de: **Propiedades del sistema**.

> > 13.2. Ya dentro de la ventana de **Propiedades del sistema** damos clic en **Opciones avanzadas**.

![win_sys_settings4](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings4.png)

> > > > Dentro de **Opciones avanzadas**, damos clic en **Variables de entorno**.

> > 13.3. Ya dentro de la ventana de **Variables de entorno** nos vamos a **Variables del sistema**.

![win_sys_settings5](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings5.png)

> > > 13.3.1. Buscamos la variable **Path** y la seleccionamos, después damos clic en **Editar** y nos abre la siguiente ventana.

![win_sys_settings6](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings6.png)

> > > 13.3.2. Damos clic en **Nuevo** e ingresamos el directorio del binario de nuestro compilador: **C:\msys64\mingw64\bin** (mi caso en particular).

![win_sys_settings7](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_sys_settings7.png)

> > 13.4. Ahora ya solo damos **Aceptar** a todas las ventanas para guardar nuestros cambios.

> Verificamos la instalación.

	gcc --version

o

	g++ --version

![win_compiler_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installed.png)

> Como podemos ver ya tenemos el compilador instalado.

### Setup para Mac.
> Las herramientas de desarrollo, son paquetes de software necesarias para nosotros poder realizar nuestros proyectos de desarrollo de software.

**Nota: En el caso de mac OS lo normal es que estas no esten incluidas**

#### Verificamos si tenemos make instalado.
> Para verificar si tenemos **make** instalado, ingresamos en la terminal el siguiente comando:

	make --version

> En caso de ya tener **make** instalado, nos saldra un mensaje similar al siguiente:

![mac_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_make_installed.png)

> #### Verificamos si tenemos el compilador de C/C++ instalado.

> Para verificar si tenemos instalado el compilador para lenguage C, ingresamos el comando siguiente:

	gcc --version

o

> Para verificar si tenemos instalado el compilador para lenguage C++, ingresamos el comando siguiente:

	g++ --version

> En caso de ya tener instalado el compilador, nos saldra un mensaje similar al siguiente.

![mac_gcc_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_gcc_installed.png)

**Nota: Si este tu caso te puedes saltar esta sección.**

#### Instalación de las herramientas de desarrollo.

> Como ya antes se habia mencionado, lo mas común es que estas herramientas de desarrollo no esten instaladas en nuestro equipo,
> por lo que será necesario instalarlas.

En este caso usaremos un gestor de paquetes para macOS: **Homebrew**.

#### Link al sitio de **Homebrew**: https://brew.sh
> En el link se muestra el sitio de donde descargaremos nuestra herramienta para gestion de paquetes **Homebrew**. Dentro del sitio nos muestra un comando para instalacion:

	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

> 1. Copiamos el comando y lo pegamos en nuestra consola:.

![mac_brew_install](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_brew_install.png)

> 2. Esperamos a que la instalación se termine, podemos observar que **brew** nos instala las herramientas de línea de comandos de xcode y demás dependencias para desarrollo. 

![mac_brew_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_brew_installed.png)

> > 2.1 Al final de la instalacion, los siguientes comandos nos ayudan a agregar **brew** al **PATH**

	echo >> /Users/tu_usuario/.zprofile
	echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/tu_usuario/.zprofile
	eval "$(/opt/homebrew/bin/brew shellenv)"

> > 2.2. Ingresamos el siguiente comando:

	brew help

![mac_brew_verification](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/brew_verification.png)

> 3. Una vez que tenemos **brew** instalado, verificamos que nuestras herramientas de desarrollo esten instaladas.

> > 3.1. Verificación de **make**, ingresamos el siguiente comando.

	make --version

![mac_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_make_installed.png)

> > 3.2 Verificacion de que el compilador de lenguage C/C++ (**clang**) ya está instalado.

	gcc --version

![mac_gcc_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_gcc_installed.png)

**Nota: para este curso estaremos usando el compilador de GNU.**

> Para instalar gcc de GNU, ingresamos el comando siguiente:

	brew install gcc

> Para verificar la instalacion de gcc de GNU, ingresamos el comando siguiente:

	gcc-14 --version

![mac_gnu-gcc_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_gnu-gcc_installed.png)

### Linux (ubuntu).

**Nota: normalmente ubuntu ya viene con todo el paquete de desarrollo instalado, solo debemos actualizar las herramientas.**
> Podemos corroborar con el siguiente comando:

	sudo apt-get install build-essential

![linux_toolset](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/linux_toolset.png)

Lo que debemos hacer es solo actualizar nuestras herramientas de desarrollo.

> 1. Actualizamos la lista de paquetes de software disponibles en los repositorios oficiales.

	sudo apt-get update

> 2. Actualizamos los paquetes instalados en un sistema a sus versiones mas recientes.

	sudo apt-get upgrade

> 3. Nuevamente actualizamos la lista de paquetes de software disponibles en los repositorios oficiales.

	sudo apt-get update

Esto suele tomar tiempo en lo que actualiza todo el entorno de desarrollo.

#### Instalación de las herramientas de desarrollo (en caso de no tenerlas instaladas).

> 1. Actualizamos la lista de paquetes de software disponibles en los repositorios oficiales.

	sudo apt-get update

> 2. El siguiente comando nos permite descargar las herramientas del entorno de desarrollo de ubuntu.

	sudo apt-get install build-essential

> 3. Nuevamente actualizamos la lista de paquetes de software disponibles en los repositorios oficiales.

	sudo apt-get update

> 4. Actualizamos los paquetes instalados en el sistema a sus versiones mas recientes.

	sudo apt-get upgrade

> 5. Nuevamente actualizamos la lista de paquetes de software disponibles en los repositorios oficiales.

	sudo apt-get update

> 6. Verficamos la instalación de make, con el siguiente comando:

	make --version

> 5. También podemos verificar los compiladores de lenguage C (gcc) y C++ (g++).

	gcc --version

ó

	g++ --version

![linux_complete_setup](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/linux_complete_setup.png)

**Nota: ya tenemos todas las herramientas de desarrollo instaladas para nuestro curso.**
Yo recomiento que instalemos un IDE (entorno de desarrollo integrado), ya que esto nos permitirá realizar nuestro curso de una manera más cómoda.

En lo personal me gusta mucho Visual Studio Code.

> Mac: https://code.visualstudio.com/docs/setup/mac

> Linux: https://code.visualstudio.com/docs/setup/linux

> Windows: https://code.visualstudio.com/docs/setup/windows

**Nota: dentro de los enlaces anteriores vienen las instrucciones de instalación para cada sistema operativo.**

Con esto demos terminada esta sección de set up.

**Nota: en mi caso en particular estaré haciendo los ejercicios en ubuntu**

## Sección 1: Proceso de compilación de un programa en lenguages C/C++.
El proceso de compilación de un programa en lenguage C/C++, se divide en las siguientes etapas:
> 1. Preprocesador (preprocessing).
> 2. Compilación (compilation).
> 3. Ensamblado (assembly).
> 4. Enlazado (linking).

Este proceso se muestra a continuacion.

![Compilation_process](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/Compilation_process.png)

En forma de bloques.

![Compilation](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/Compilation.png)

El proceso de compilación de un programa en C, nos lleva a convertir nuestro código fuente a un archivo ejecutable que realice la tarea que hemos desarrollado.

### Preprocessing.

En la etapa de preprocesador, se realizan los siguientes procesos:
> 1. Se hace la expansión de macros, el preprocesador se encarga de sustituir las macros con sus valores.
> 2. Se hace la expansion de la directivas **#include** con el contenido del archivo.
> 3. Hace la preparación de las condiciones para la compilacion, en esta etapa el preprocesador evalua las directivas: **#if**, **#ifdef**, **ifndef**, **#else**, **#elif**, **#endif**, de tal
> manera que incluye o excluye el código de acuerdo a la evaluación hecha.
> 4. Control de linea, si se usa un programa para combinar o reordenar los archivos de código fuente en un archivo intermedio que se será compilado, se usa el control del linea para informar al 
> compilador de que archivo de código fuente viene originalmente.
> 6. Diagnósticos, se pueden detectar prolemas al momento de compilar y documentar el error o advertencia.
> 5. Se reemplaca cada comentario con un espacio sencillo.

Para invocar el preprocesador usamos el comando:

	gcc -E

Por ejemplo:

	gcc -E main.c -o main.i

> La extension *.i, se refiere a un archivo intermedio que ya ha sido precompilado.

### Compilation.

Una vez que el preprocesado se ha hecho, pasamos a la etapa de **compilación** donde el código fuente se **compila** a un archivo de compilación intermedia. 
Este archivo contiene intrucciones en lenguaje ensamblador.
> 1. Esta etapa requiere de los archivos ya preprocesados con extension ***.i** .
> 2. El compilador toma los archivos ***.i** y los convierte a lenguaje ensamblador.
> 3. El lenguage ensamblador es un lenguaje de bajo nivel que usa mnemonicos por ejemplo: **MOV** para mover, **ADD** para añadir. Los mnemonicos son usados para representar operaciones del
> CPU, lo que hace que estas operaciones pueden ser leidas por personas.

Para invocar al compilador usamos el comando:

	gcc -S

Por ejemplo:

	gcc -S main.i -o main.s

### Assembly.

Una vez que la etapa de compilación ha terminado y como resultado tenemos nuestro archivo de compilación intermedia en lenguaje ensamblador, éste es **ensamblado** en un archivo tipo objeto (relocatable object file) que contiene instrucciones a nivel máquina.

> 1. Esta etapa requiere de los archivos  en lenguaje ensamblador con extension *.s o *.asm.
> 2. Cada instrucción en ensamblador representa a una instrucción en lenguage máquina.
> 3. Cada instrucción en lenguaje máquina es una secuencia de ceros y unos de los cuales una parte parte realiza operaciones y lo que resta son direcciones de memoria de las variables o algun valor numérico.
> 4. El lenguage ensamblador es independiente de la arquitectura del CPU, mientras que el lenguaje máquina si depende de la arquitectura del CPU.
> 5. Las instrucciones en lenguaje máquina para un tipo de CPU muy probablemente no van a poder correr en un CPU de arquitectura diferente si no hace una modificación.

Para invocar al ensamblador usamos el comando:

	gcc -c main.s -o main.o

o también se puede llamar el ensamblador directamente.

	as main.s -o main.o

La unidad mas pequeña de un archivo de tipo objeto es una **sección**.

> **section** o sección es un bloque de código o datos que ocupan espacio contiguo en el mapa de memoría. Cada sección de memoría de un archivo tipo objeto esta separado y es distinto uno del otro.

### Linking.

Los archivos tipo objeto generados en la etapa de ensamblado son **enlazados** para crear un programa ejecutable.
> 1. La entrada para esta etapa, son los archivos tipo objeto que contienen instrucciones en lenguaje máquina.
> 2. El enlazador o linker nos permite integrar los archivos tipo objetos de múltiples módulos en un solo archivo.
> 3. Si se usan funciones de librerías, el linker enlaza nuestro código a la librería que contiene la función que requerimos.
> 4. Las librerías estándar ya vienen integradas con el compilador, no es necesario recompilarlas.
> 5. Las librerías que no son estándar deben ser enlazadas manualmente.

Para invocar al linker usamos el siguiente comando:

	gcc main.o -o myexec

**myexec** es el nombre que le he dado a mi archivo ejecutable. Para correr el archivo solo usamos el siguiente comando:

	./you_executable_file

Siendo nuestro caso:

	./myexec

El resultado después del linkeo es un archivo de tipo ELF (Executable Linked File).
Con la siguiente estructura:

![ELF_format](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/ELF_format.png)

En cuestion de memoria virtual tenemos la siguiente estructura.

![Virtual_memory](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/Virtual_memory.png)

## Seccion 2: Conceptos básicos.
### Qué es make?
> **GNU make** es una herramienta la cual nos permite la generación de ejecutables y demás archivos que no son código fuente a partir de los archivos de código fuente de un programa.

### Qué hace make?
> **make** automáticamente determina cuales piezas (código fuente) necesitan ser compiladas o recompiladas y los comandos para hacerlo.

### Qué es un makefile?
> Para preparar el uso de **make**, debemos escribir un archivo que se llama **makefile** el cual describe la relación entre los archivos de un programa y provee los comandos para la actualización  de cada archivo.

### Para qué sirve un makefile?
> Un archivo **makefile** detecta cada cambio que se haga en cualquier archivo de código fuente, simplemente al escribir el siguiente comando:

	make

> **make** realiza las recompilaciones necesarias.

> **make** usa la información del **makefile** y la ultima modificación de los archivos de código fuente para decidir cuales archivos necesitan ser actualizados.

> Para cada uno de esos archivos, **make** usa las ordenes escritas en el **makefile**.

#### En pocas palabras se necesita un archivo **makefile** para decirle a **make** que hacer.

En nuestro curso usaremos **make** y **makefile** para compilar y linkear programas en lenguage C.

**Nota: cabe mencionar que make no solo se limita a los lenguages C/C++**