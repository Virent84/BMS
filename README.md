# Smart EV Battery Monitoring and Protection System using ESP32

A student project repository for monitoring battery-related electrical and thermal parameters with an ESP32, displaying measurements locally, and reporting data through an IoT dashboard.

> **Repository status:** This is a documentation scaffold. Add your existing, tested Arduino `.ino` sketch to `firmware/` before treating any feature as implemented. The dashboard is reported by the project owner to be working; add screenshots and document its actual widgets and data streams.

## Project goals

- Monitor voltage, current, and temperature.
- Display measurements locally (if implemented in the current firmware).
- Send telemetry to an IoT dashboard (the owner reports that this already works).
- Provide alerting and relay-based cutoff (only mark as verified after testing).
- Explore state-of-charge (SOC) and state-of-health (SOH) estimation, with their limitations documented.

## Current implementation status

Update this table to match the code and tests you actually have. Do not claim a feature works merely because it is planned.

| Feature | Status | Evidence |
|---|---|---|
| Arduino IDE firmware | Existing `.ino` file(s) to be added | Firmware compile/test record |
| IoT dashboard | Reported working | Add screenshot and describe configured datastreams |
| Voltage measurement | Confirm against your sketch | Calibration readings |
| Current measurement | Confirm against your sketch | Comparison against a reference meter/load |
| Temperature measurement | Confirm against your sketch | Comparison against a reference thermometer |
| LCD display | Confirm against your sketch | Photo/video |
| Relay cutoff / protection | Confirm against your sketch | Controlled low-risk functional test |
| SOC estimation | Document actual algorithm; voltage-only estimate is approximate | Test notes and battery chemistry |
| SOH estimation | Experimental or planned unless validated by a capacity test | Capacity-test procedure/results |
| Motor/load demo | Confirm actual wiring and tests | Photo and test notes |

## Hardware

The project has previously been discussed with these modules; verify the actual assembled hardware and update the BOM:
- ESP32 DevKit V1
- ADS1115 ADC module
- ACS712 current sensor
- DS18B20 temperature sensor
- I²C LCD (confirm display size)
- Relay module
- LM2596 buck converter
- LEDs and buzzer
- Suitable, fused DC source and load for testing

See [`hardware/BOM.csv`](hardware/BOM.csv) and [`hardware/wiring.md`](hardware/wiring.md).

## Repository layout

```text
firmware/     Existing Arduino sketches and firmware notes
dashboard/    Dashboard description and screenshots
hardware/     Bill of materials and wiring notes
docs/         Architecture, SOC/SOH notes, and limitations
tests/        Calibration and test records
```

## Setup

1. Install Arduino IDE.
2. Install the ESP32 board support package matching your board.
3. Install the libraries required by your actual sketch. Record their names and versions in `firmware/README.md`.
4. Copy `firmware/secrets.example.h` to a local file named `secrets.h` only if you update your sketch to include it. Keep `secrets.h` private; it is ignored by Git.
5. Open the main `.ino` file in Arduino IDE. Arduino sketches generally need their primary `.ino` file in a folder with the same name; if needed, make a local sketch folder such as `SmartEVBMS/SmartEVBMS.ino` and preserve the published source.
6. Select the correct ESP32 board and port, then compile and test before connecting a real battery.

**Important:** This repository does not contain your existing working firmware because it was not provided in this conversation. The scaffold intentionally does not invent code or claim unverified hardware behavior.

## Safety

- Start with a current-limited, low-voltage test setup where practical.
- Use suitable fusing and correctly rated wiring, sensors, relay contacts, and loads.
- Do not connect a motor directly to an ESP32 GPIO.
- Verify the battery chemistry, voltage limits, and sensor calibration before using protection thresholds.
- Do not rely on this student prototype as the sole protection system for a real EV battery pack.
- Stop testing immediately if any component overheats, smells burnt, or behaves unexpectedly.

## Test records

Record date, setup, reference instrument, measured value, expected value, error, and pass/fail in `tests/test-results.csv`. Do not publish fabricated measurements.

## License

This repository includes an MIT License template. Confirm that you own or have permission to publish all code, images, and design files before publishing.
