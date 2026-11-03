# 01 - Blink

An LED on GPIO 2 switching on and off, with the state also reported over the serial
monitor.

**Run it:** https://wokwi.com/projects/479677462580232193

## What it does

`setup` opens the serial channel and declares GPIO 2 as an output. `loop` drives the pin
HIGH, waits, drives it LOW, waits, and the chip repeats that forever. Each change is also
printed over serial.

## Wiring

`diagram.json` connects:

- `esp:2` to `led1:A` - GPIO 2 to the LED anode
- `led1:C` to `esp:GND.1` - LED cathode back to ground

Both wires are needed. Current has to return to ground or nothing flows.

On real hardware this LED would need a series resistor, roughly 220 ohm, or it burns out.
The simulator is forgiving about that.

## What it taught me

- **`setup` runs once, `loop` runs forever.** Firmware never ends, so it is shaped
  differently from a normal program that runs top to bottom and stops.
- **A digital pin has two states**, 3.3 V or 0 V, named HIGH and LOW. Nothing in between.
- **A pin on its own does nothing visible.** It only changes voltage. Something has to be
  connected for that to become light.
- **When you cannot trust what you see, make the chip tell you in words.** The LED appeared
  dead while the code was correct. The serial monitor proved the loop was running and
  narrowed the fault to the wiring.
- **`Serial.println` does nothing without `Serial.begin`.** The channel has to be opened
  before anything can travel down it.
- **The chip runs what was flashed, not what is in the editor.** Editing code changes
  nothing until you restart.

## Bugs I hit, in order

| Symptom | Cause |
|---|---|
| LED came on and stayed on | `digitalWrite` was in `setup`, so it ran once |
| Code correct, still no blink | Simulator was still running the previous build |
| No serial output | `Serial.begin(115200)` missing from `setup` |
| Serial working, LED still dark | Nothing was connected to GPIO 2 on this board |
