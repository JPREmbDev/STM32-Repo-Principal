# 🚀 Repositorio de Microcontroladores STM32: Blue Pill, Black Pill y más

[![STATUS](https://img.shields.io/badge/Estado-En%20Desarrollo-blue)](https://github.com/tu_usuario/tu_repo) 
[![PlatformIO](https://img.shields.io/badge/PlatformIO-STM32Cube-orange)](https://platformio.org/)
[![Toolchain](https://img.shields.io/badge/Toolchain-arm--none--eabi--gcc-success)](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-a/downloads)


Este repositorio actúa como un **laboratorio de código** para explorar y dominar diferentes periféricos y funcionalidades de los microcontroladores **STM32** de STMicroelectronics. Incluye proyectos completos y plantillas para diversas placas de desarrollo populares.

---

## 🧭 Tabla de Contenidos

1.  [Placas Soportadas](#-placas-soportadas)
2.  [Estructura del Repositorio](#-estructura-del-repositorio)
3.  [Requisitos](#⚙️-requisitos)
4.  [Cómo Empezar](#-cómo-empezar)
5.  [Proyectos Destacados](#-proyectos-destacados)
6.  [Contribuciones](#-contribuciones)

---

## 🗄️ Placas Soportadas

| Placa | Microcontrolador | Familia | Estado de Proyectos |
| :--- | :--- | :--- | :--- |
| **Blue Pill** | STM32F103C8T6 | STM32F1 | ✅ Ejemplos Iniciales |
| **STM32 VLDiscovery** | STM32F100RB | STM32F1 | ✅ Ejemplos Iniciales |
| **Black Pill** | STM32F401CCU6 (o similar) | STM32F4 | 🏗️ En Planificación |

---

## 📁 Estructura del repositorio

```text
/STM32-Repo-Principal
├── /BluePill_F103 (Microcontrolador STM32F103C8T6)
│   ├── /01_GPIO_Blink
│   │   ├── main.c              # Código fuente principal del ejemplo
│   │   ├── Makefile            # Archivo de build (o archivos de proyecto IDE)
│   │   └── README.md           # Documentación específica (Pinout, detalles de código)
│   ├── /02_UART_Echo
│   └── /...
├── /BlackPill_F401 (Microcontrolador STM32F401CCU6)
│   ├── /01_ADC_Lectura
│   └── /...
├── /STM32_VLDiscovery
│   └── /... proyectos ...
├── /Recursos                   # Documentación general y herramientas
│   ├── /Datasheets
│   └── /Herramientas
├── .gitignore                  # Archivos ignorados por Git (binarios, .o, etc.)
└── README.md                   # Documento principal
```
