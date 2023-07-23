# Baby_Kyber
This is a repository o me introducing myself to python and Jupyter notebooks. With the objective to create a notebook with a working example of baby kybe
# Notas personales sobre Bare Metal Compiling para Embedded C

**Objetivo** : Convertir los archivos en C en un ejecutable especifico para un determinado microcontrolador ARM.
  
 
## Cross compilation toolchain

Es el proceso en el cual se utiliza cierto `toolchain` en una computadora (host) para crear codigo que sera ejecutado en otro dispositivo (ARM MCU), diferente a la maquina en donde se creo.

Un `toolchain` es una coleccion de archivos binarios que permiten compilar, linkear y ensamblar las aplicaciones. Estos cuentan ademas con otros binarios que permiten analizar los ejecutables (ej: debug o dissaemble).

El `toolchain` mas popular para los procesadores ARM es el GCC-ARM compiler, basado en GNU, de codigo abierto. Para

Estructura del directorio (puede cambiar a medida que escribo esto)
```
Embedded_bare_metal
├── led.c
├── led.h
├── main.c
├── main.h
```
