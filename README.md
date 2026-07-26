# Samsung ML-1610 + CUPS 2.4.10 + Raspberry Pi OS Trixie

Repositorio dedicado a documentar una instalación completamente funcional de la impresora **Samsung ML-1610** utilizando **CUPS 2.4.10** sobre **Raspberry Pi OS Trixie**, ejecutándose en una **Raspberry Pi Zero W**.

El objetivo de este proyecto es preservar una solución completamente funcional para una impresora que, aunque ya tiene varios años en el mercado, continúa siendo ampliamente utilizada.

---

# Objetivos

Este repositorio tiene cuatro objetivos principales:

- Documentar una instalación funcional desde cero.
- Explicar cómo funciona el controlador SPLIX dentro de CUPS.
- Conservar un respaldo de los archivos indispensables para futuras instalaciones.
- Facilitar la restauración del controlador incluso si en el futuro los paquetes dejan de estar disponibles.

---

# Contenido del repositorio

```
backup/
│
├── etc/
│   └── cups/
│       └── ppd/
│           └── Samsung_ML-1610.ppd
│
├── usr/
│   ├── lib/
│   │   └── cups/
│   │       └── filter/
│   │           ├── pstoqpdl
│   │           └── rastertoqpdl
│   │
│   └── share/
│       └── cups/
│           └── drv/
│               └── splix-samsung.drv
│
└── printer-driver-splix-info.txt

docs/
└── Samsung-ML1610-CUPS-Trixie.md
```

---

# Requisitos

Esta guía asume que el sistema ya cuenta con:

- Raspberry Pi Zero W
- Raspberry Pi OS Trixie
- CUPS 2.4.10 correctamente instalado y funcionando
- Acceso a la interfaz web de CUPS

La instalación de Raspberry Pi OS y de CUPS **no forma parte de esta documentación**.

---

# Documentación

La guía completa puede encontrarse en:

```
docs/Samsung-ML1610-CUPS-Trixie.md
```

Allí se explica:

- Instalación
- Configuración
- Funcionamiento
- Restauración
- Arquitectura de impresión
- Solución de problemas de software

---

# Respaldo incluido

Este repositorio conserva los archivos mínimos necesarios utilizados durante la instalación documentada.

El respaldo incluido tiene fines de preservación y recuperación. Siempre que sea posible, se recomienda instalar el paquete oficial printer-driver-splix desde los repositorios de Raspberry Pi OS.

---

# Versiones verificadas

Hardware:

- Raspberry Pi Zero W

Sistema operativo:

- Raspberry Pi OS Trixie

Servidor de impresión:

- CUPS 2.4.10

Driver:

- SPLIX 2.0.0

Impresora:

- Samsung ML-1610

---

# Licencia

Este repositorio distribuye únicamente archivos necesarios para documentar una instalación funcional.

Todo el software conserva las licencias originales de sus respectivos autores.

---

# Agradecimientos

A la comunidad de software libre por mantener vivo CUPS, SPLIX y Raspberry Pi OS.

Y a todos los usuarios que continúan preservando hardware clásico mediante documentación técnica abierta, permitiendo que equipos perfectamente funcionales sigan siendo útiles muchos años después de haber sido descontinuados.
