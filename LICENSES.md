# Licencias y atribuciones

Este repositorio contiene documentación y archivos de respaldo utilizados para restaurar la compatibilidad de la impresora Samsung ML-1610 con CUPS 2.4.10 en Raspberry Pi OS Trixie.

## Documentación

Toda la documentación escrita en este repositorio se distribuye bajo la licencia MIT, indicada en el archivo `LICENSE`.

## Archivos incluidos

Los siguientes archivos forman parte del respaldo documentado:

- `/usr/lib/cups/filter/rastertoqpdl`
- `/usr/lib/cups/filter/pstoqpdl`
- `/usr/share/cups/drv/splix-samsung.drv`
- `/etc/cups/ppd/Samsung_ML-1610.ppd`

Estos archivos provienen de una instalación funcional de:

- Raspberry Pi OS Trixie
- CUPS 2.4.10
- paquete `printer-driver-splix`

No fueron modificados ni desarrollados por el autor de este repositorio.

Todos los derechos sobre dichos componentes pertenecen a sus respectivos autores y proyectos.

Este repositorio únicamente los redistribuye con fines de preservación, documentación y restauración de sistemas compatibles.

## Proyecto SPLIX

SPLIX es un proyecto de software libre destinado a proporcionar soporte para impresoras Samsung y Xerox compatibles con QPDL.

Más información:

https://splix.sourceforge.net/

## Raspberry Pi OS

https://www.raspberrypi.com/software/

## CUPS

https://openprinting.github.io/cups/
