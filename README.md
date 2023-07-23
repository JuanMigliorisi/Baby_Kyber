# Baby_Kyber
This is a repository o me introducing myself to python and Jupyter notebooks. With the objective to create a notebook with a working example of baby kybe

# Notas personales sobre Bare Metal Compiling para Embedded C

**Objetivo** : Aprender a generar una estructura para proyectos en C donde el objetivo del ejecutable sea un determinado microcontrolador ARM. Quiero lograrlo utilizando `make` para compilar, sin depender ningun IDE. 
 
## Cross compilation toolchain

Es el proceso en el cual se utiliza cierto `toolchain` en una computadora (host) para crear codigo que sera ejecutado en otro dispositivo (ARM MCU), diferente a la maquina en donde se creo.

Un `toolchain` es una coleccion de archivos binarios que permiten compilar, linkear y ensamblar las aplicaciones. Estos cuentan ademas con otros binarios que permiten analizar los ejecutables (ej: debug o dissaemble).

El `toolchain` mas popular para los procesadores ARM es el GCC-ARM compiler, basado en GNU, de codigo abierto. Para invocar este compilador se debe ejecutar : `arm-none-eabi-gcc` 
## Proceso de compilacion 
Esto hace el compilador.
1) Generacion de codigo: Archivos de alto nivel `.c` son convertidos en mnemonicos arquitecutates `.s`
2) Etapa de Ensamblado: Los mnemonicos en Assemlby son convertidos en `opcodes`, que es el codigo de maquina para las instrucciones, y se genera el archivo `.o` (Relocatable object file).
3) Los archivos `.o` son tomados por el `linker` y genera el "Excutable and debug file" o archivo `.elf`
4) Se puede tomar una herramienta de copiado y pasar de `.elf` a .`bin`

Todos estos pasos son realizados invocando `arm-none-eabi-gcc` con sus correspondientes argumentos

Si tenemos un directorio con esta estructura (puede cambiar a medida que escribo esto)
```
Embedded_bare_metal
├── led.c
├── led.h
├── main.c
├── main.h
``` 
y ejecutamos 
```
arm-none-eabi-gcc -c main.c -o main.o
``` 
nos devuelve:
```
 Error: selected processor does not support requested special purpose register
```
Esto significa que el ensamblador no pudo entender los mnemonicos porque no fue mencionada la arquitectura del procesador
