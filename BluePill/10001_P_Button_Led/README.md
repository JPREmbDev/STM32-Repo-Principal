# 🚀 STM32 Blue Pill (CS32F103C8T6) – Desarrollo y Avances con PlatformIO

Este repositorio documenta el desarrollo de mi proyecto de electrónica y firmware basado en la placa **Blue Pill** (con el microcontrolador clon **CS32F103C8T6**), utilizando el entorno de **PlatformIO** y el framework **STM32Cube**.

## 📌 Estado Actual del Proyecto

| Característica / Módulo | Estado | Nota de Avance |
| :--- | :---: | :--- |
| **Configuración Base (PlatformIO/OpenOCD)** | ✅ Completa | Lograda la comunicación y depuración con el chip clonado. |
| **Ejemplo `Blinky` (LED PC13)** | ✅ Funcional | Primer *Hello World* confirmado. |
| **Control GPIO (Pulsadores)** | 🚧 En progreso (v0.1) | Configuración inicial de *pull-ups* y detección de flanco. |
| **Comunicación USART1** | ❌ Pendiente | Próximo objetivo: enviar datos a la terminal serial. |
| **Módulo I2C (Sensor X)** | 💡 Planeado | Integración de un sensor de temperatura/humedad vía I2C. |

-----

## 🧩 Solución para el Chip Clonado (CS32F103)

Como referencia para mí y otros desarrolladores, mantengo la configuración especial que permite trabajar con clones del STM32F103C8T6 que responden con un **CPUTAPID diferente** (`0x2ba01477`) al esperado por OpenOCD.

### Configuración de `platformio.ini`

```ini
[env:bluepill_f103c8]
platform = ststm32
board = bluepill_f103c8
framework = stm32cube

upload_protocol = custom
debug_tool = custom

debug_server =
  C:\openocd\xpack-openocd-0.12.0-7\bin\openocd.exe
  -s C:\openocd\xpack-openocd-0.12.0-7\scripts
  -f interface/stlink.cfg
  -c "transport select swd"
  -c "set CPUTAPID 0x2ba01477"  ; <-- ID CLONADO CS32F103
  -f target/stm32f1x.cfg
  -c "reset_config none"

; NOTA: Si la carga (upload) falla, usar la carga nativa del OpenOCD personalizado.
; upload_command = $DEBUG_TOOL -f ... [Comandos de flasheo] ...
```

-----

## 📚 Diario de Desarrollo (Changelog)

Esta sección se actualizará con cada avance significativo del proyecto.

### v0.1.0 - 20 de Octubre de 2025: Configuración Base y Blinky

  * **Logro:** Configuración exitosa de PlatformIO para reconocer el CS32F103.
  * **Problema resuelto:** Se logró superar el `Error: expected 1 of 1: 0x1ba01477` de OpenOCD personalizando el *debug\_server* en `platformio.ini`.
  * **Prueba inicial:** *Blinky* funcional en el LED de la placa (PC13). Comunicación con ST-Link V2 estable.

-----

## 🛠️ Requisitos del Entorno

  * [PlatformIO](https://platformio.org/) (v6+)
  * [xPack OpenOCD 0.12.0+](https://xpack.github.io/openocd/)
      * **Ruta de Instalación:** `C:\openocd\xpack-openocd-0.12.0-7` (Crucial para el `debug_server`).
  * Hardware: Placa Blue Pill (CS32F103C8T6) y ST-Link V2.

## 📁 Estructura del Proyecto

```
.
├── src/
│   └── main.c               # Código principal (logros y lógica)
├── include/
│   └── gpio_config.h        # Headers de configuración de periféricos
├── .vscode/                 # Configuración del IDE (debugging)
├── platformio.ini           # Configuración del entorno clonado (CRUCIAL)
└── README.md                # Este archivo de documentación y avances
```

## 🚀 Comandos Útiles de PlatformIO

| Comando | Función |
| :--- | :--- |
| `platformio run` | Compila el firmware. |
| `platformio run --target upload` | Sube el firmware al chip (usa la configuración `custom`). |
| `platformio device monitor` | Abre el monitor serial. |
| `platformio debug` | Inicia la sesión de depuración. |

-----
