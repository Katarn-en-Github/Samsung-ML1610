# Samsung ML-1610 en Raspberry Pi OS Trixie (Raspberry Pi Zero W) usando CUPS 2.4.10

## Índice
1. Introducción
2. Arquitectura de impresión
3. Requisitos
4. Instalación paso a paso
5. Explicación de los componentes
6. Configuración desde la interfaz web de CUPS
7. Verificaciones
8. Restauración desde un respaldo
9. Solución de problemas de software
10. Conclusiones
11. Anexo A – Archivos del respaldo

## Introducción
Esta guía explica cómo configurar una Samsung ML-1610 en una Raspberry Pi Zero W con Raspberry Pi OS Trixie y CUPS 2.4.10. Se asume que el sistema operativo y CUPS ya están instalados.

## Arquitectura de impresión
```text
Aplicación
   |
   v
 CUPS
   |
application/vnd.cups-raster
   |
   v
rastertoqpdl
   |
   v
 QPDL
   |
   v
Samsung ML-1610
```

## Requisitos
- Raspberry Pi Zero W.
- Raspberry Pi OS Trixie instalado.
- CUPS 2.4.10 instalado y operativo.
- Acceso a la interfaz web de CUPS.
- Conectividad USB funcional.

## Instalación paso a paso
```bash
sudo apt update
sudo apt install printer-driver-splix
lpinfo -m | grep -i ML-1610
```
Agregue la impresora desde la interfaz web de CUPS y seleccione **Samsung ML-1610, 2.0.0**.

## Explicación de los componentes
### rastertoqpdl
Convierte el formato raster de CUPS al lenguaje QPDL utilizado por la impresora.

### pstoqpdl
Convierte trabajos PostScript a QPDL cuando es necesario.

### splix-samsung.drv
Define el controlador que CUPS utiliza para generar el PPD correspondiente.

### Samsung_ML-1610.ppd
Contiene la configuración específica utilizada por CUPS para esta impresora.

## Configuración desde la interfaz web de CUPS
Administration → Add Printer → Samsung ML-1610 Series (USB) → Samsung ML-1610, 2.0.0.

## Verificaciones
```bash
lpinfo -m | grep -i ML-1610
lpstat -t
sudo cupstestppd /etc/cups/ppd/Samsung_ML-1610.ppd
sudo grep cupsFilter /etc/cups/ppd/Samsung_ML-1610.ppd
```
Debe aparecer:
```
*cupsFilter: "application/vnd.cups-raster 0 rastertoqpdl"
```

## Restauración desde un respaldo
Copiar:
- /usr/lib/cups/filter/rastertoqpdl
- /usr/lib/cups/filter/pstoqpdl
- /usr/share/cups/drv/splix-samsung.drv
- /etc/cups/ppd/Samsung_ML-1610.ppd

Reiniciar CUPS:
```bash
sudo systemctl restart cups
```

## Solución de problemas de software
- La ML-1610 no aparece en la lista.
- Error "Filter failed".
- Falta `rastertoqpdl`.
- El PPD no pasa `cupstestppd`.
- `cupsFilter` incorrecto.
- Trabajos retenidos en cola.

## Conclusiones
La combinación de CUPS 2.4.10 y SPLIX proporciona compatibilidad funcional con la Samsung ML-1610 en Raspberry Pi OS Trixie.

## Anexo A – Archivos del respaldo

| Archivo | Ruta | Función |
|---|---|---|
| rastertoqpdl | /usr/lib/cups/filter | Raster → QPDL |
| pstoqpdl | /usr/lib/cups/filter | PostScript → QPDL |
| splix-samsung.drv | /usr/share/cups/drv | Definición del controlador |
| Samsung_ML-1610.ppd | /etc/cups/ppd | Configuración de la impresora |
