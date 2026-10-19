# System architecture

Intended high-level flow (adjust to match the implemented firmware):

DC source / battery and load → voltage/current/temperature sensing → ADS1115 / ESP32 acquisition → threshold checks and estimates → local display / buzzer / relay output → Wi-Fi telemetry → IoT dashboard.

This is a conceptual overview, not a verified schematic. Update it if your actual hardware differs.
