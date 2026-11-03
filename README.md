# Embedded practice

Working through embedded systems from the ground up, one project per folder. Each has its
own README with what it does, how to run it, and what it taught me.

Studying BEng Computer Engineering at UCLan Cyprus, heading for embedded systems and edge
AI. The C++ fundamentals live in [cpp-practice](https://github.com/syedromanai/cpp-practice);
this repo is where they meet hardware.

Projects run in [Wokwi](https://wokwi.com), a free browser-based ESP32 simulator, until the
work needs a real board.

## Projects

| | Project | Concepts | Simulator |
|---|---|---|---|
| 01 | [Blink](esp32-01-blink) | `setup` vs `loop`, digital output, `pinMode` / `digitalWrite` / `delay`, serial-monitor debugging, wiring an LED to a GPIO pin | [Wokwi](https://wokwi.com/projects/479677462580232193) |

## Planned

| | Project | New skill |
|---|---|---|
| 02 | Button | digital input, pull-up resistors, debouncing |
| 03 | Potentiometer | analog input, the ADC |
| 04 | PWM | dimming an LED, driving a servo |
| 05 | Sensor over I2C | talking to another chip |
| 06 | Wi-Fi | what the ESP32 is actually for |
