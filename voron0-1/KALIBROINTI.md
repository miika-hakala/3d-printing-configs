# Voron 0 Kalibrointi

## Tehty
- Pressure Advance: 0.04 (PETG, DDE, PA Tower testi)
- Input Shaper: manuaaliset arvot (ei ADXL345 anturia)
  - shaper_freq_x: 60
  - shaper_freq_y: 60
  - shaper_type: mzv

## Tekemättä
- Sensorless homing SGTHRS kalibrointi (nykyinen arvo 55, ei kalibroitu)
- Input shaper kalibrointi ADXL345 anturilla
- Pressure advance uudelleenkalibrointi eri filamenteille

## Firmware
- Klipper v0.13.0
- MCU: BTT Pico (RP2040)
- Flashaus: UF2 via USB (make flash ei toimi, käytä flash_usb.py tai manuaalinen UF2)

## OrcaSlicer asetukset
- Start G-code: PRINT_START EXTRUDER=[nozzle_temperature_initial_layer] BED=[bed_temperature_initial_layer_single]
- End G-code: PRINT_END
