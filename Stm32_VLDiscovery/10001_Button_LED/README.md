# 🌟 STM32 VLDiscovery: 01 - Control de LED por Botón

## 📖 Objetivo del Proyecto

Este proyecto demuestra la configuración y uso básico de la **Entrada/Salida Digital (GPIO)**. El firmware lee el estado de un 
pin configurado como entrada (el botón de usuario) y utiliza ese valor para controlar un pin configurado como salida (el LED a bordo).

En esencia, el LED se enciende solo mientras el botón está presionado.

---

## ⚙️ Hardware Utilizado

Este proyecto está configurado para la placa **STM32 VLDiscovery**.

| Componente | Pin del Microcontrolador | Función en el Código | Descripción |
| :--- | :--- | :--- | :--- |
| **Botón de Usuario** | **PA0** | `GPIO_PIN_0` | Entrada digital. Activo en alto (presionado = `SET`). |
| **LED LD4 (Verde)** | **PC9** | `LD4_Pin` | Salida digital. Controlado por el estado del botón. |

### Configuración del Microcontrolador

* **Chip:** STM32F100RB (Familia STM32F1 Value Line).
* **Clock:** Configurado a la frecuencia interna por defecto (**HSI**).
* **Periféricos:** Se inicializa únicamente el GPIO.

---

## 🛠️ Entorno de Desarrollo

El proyecto está configurado para ser compilado y flasheado usando **PlatformIO**.

### Archivo `platformio.ini`

```ini
[env:disco_f100rb]
platform = ststm32
board = disco_f100rb
framework = stm32cube
upload_protocol = stlink