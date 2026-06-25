# STM32 Based Ultrasonic Radar: Precise Distance & Filtered Speed Measurement

This repository contains a low-level embedded system application developed in C for STM32 microcontrollers. The project interfaces with an HC-SR04 ultrasonic sensor to calculate real-time distance and implements a Digital Signal Processing (DSP) filter to estimate precise velocity.

## 🚀 Key Technical Features

* [cite_start]**Low-Level Microcontroller Management:** Configured hardware Timers (`TIM3`) for microsecond-precise delay generation (`delay_us`) and signal duration counting[cite: 6, 12].
* [cite_start]**Timeout & Exception Handling:** Implemented software timeout guards (30,000 cycles checks) during Echo pin polling to prevent the MCU from freezing in case of hardware disconnection or infinite loops[cite: 17, 21, 24].
* [cite_start]**Moving Average Filter (DSP):** Developed a custom Digital Signal Processing buffer (`FILTER_SIZE 5`) to calculate a rolling average of raw speed data[cite: 6, 9]. [cite_start]This mitigates sensor noise and spikes, providing a stabilized velocity output[cite: 9, 35].
* [cite_start]**Data Serialization & Telemetry:** Formatted raw measurements into telemetry packets (`H:000 M:000\r\n`) and transmitted them via **UART** (`USART1`) to external interfaces or loggers[cite: 11, 36, 37].

## 🛠️ Tech Stack & Hardware Components
* [cite_start]**Microcontroller:** STM32 Series (HAL & Core Peripherals) [cite: 14]
* **Sensor:** HC-SR04 Ultrasonic Sensor
* [cite_start]**Protocols:** UART (Universal Asynchronous Receiver-Transmitter) [cite: 7]
* **Development Environment:** STM32CubeIDE / Keil MDK
