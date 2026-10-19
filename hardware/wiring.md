# Hardware wiring notes

Fill this document from your actual circuit and verify each connection against the board/module datasheets. Do not assume this template represents a verified schematic.

| Module | Signal | ESP32 pin / connection | Notes |
|---|---|---|---|
| ADS1115 | SDA | Confirm actual GPIO | ESP32 I²C SDA is often GPIO 21, but verify your sketch |
| ADS1115 | SCL | Confirm actual GPIO | ESP32 I²C SCL is often GPIO 22, but verify your sketch |
| ADS1115 | VDD/GND | Per module specification | Common ground required |
| ACS712 | IP+/IP− | In series with measured load path | Verify current rating and polarity |
| DS18B20 | DATA | Confirm actual GPIO | Pull-up resistor commonly required; verify wiring |
| I²C LCD | SDA/SCL | Confirm actual I²C wiring/address | Check LCD backpack voltage compatibility |
| Relay module | IN/VCC/GND | Confirm actual GPIO and module logic | Verify contact ratings and fail-safe behavior |
| Buzzer / LEDs | Control | Confirm actual GPIO and drivers | Use suitable resistors/drivers |

**Safety:** Never treat this table as a wiring plan without checking the actual circuit. The ADS1115 input must remain within its permitted voltage range. Use a correctly designed divider and verify the resistor values and measurement reference before connecting a source.
