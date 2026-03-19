# Jatko-ohje Claude-assistentille

## Tila 19.3.2026

### AKTIIVINEN ONGELMA: Voron Switchwire USB-yhteys
SKR Mini E3 V2.0 ei näy /dev/serial/by-id/ vaikka:
- Firmware flashattu onnistuneesti (FIRMWARE.CUR SD-kortilla)
- Communication interface vaihdettu USB:ksi menuconfig:ssa
- Pi Zero saa virran omasta virtalähteestä (PWR IN)
- USB-kaapeli Pi Zero USB-portissa -> SKR Mini micro USB -portissa
- lsusb näyttää vain: Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub

Seuraavaksi kokeile:
1. Toinen USB-kaapeli (data-kaapeli, ei pelkkä latauri)
2. Tarkista SKR Minin micro USB -portti fyysisesti
3. Kokeile kytkeä SKR Mini suoraan tietokoneeseen ja tarkista näkyykö se siellä
4. Tarkista onko SKR Minissä jumppereita jotka valitsevat USB/UART

Switchwire IP: 192.168.0.190
SSH: ssh miika@switchwire-1.local

### Voron 0 - TOIMII
- IP: 192.168.0.223
- SSH: ssh pi@voron0.local (käyttäjä pi)
- Klipper v0.13.0, firmware flashattu onnistuneesti
- Pressure advance: 0.04 (PETG)
- Input shaper: mzv, 60Hz (manuaalinen, ei mitattu)
- Kalibroimatta: SGTHRS sensorless homing

### Voron Switchwire - OSITTAIN TOIMII
- IP: 192.168.0.190
- SSH: ssh miika@switchwire-1.local
- Klipper v0.13.0 asennettu, Moonraker toimii
- MCU ei yhteydessä (USB-ongelma)
- printer.cfg tallessa: switchwire/printer.cfg

### Ender 3 V3 SE - TOIMII
- Firmware SWV1.1.0 päivitetty
- PETG: 235-240°C nozzle, 75-80°C bed

### PIB Robot - TYÖN ALLA
- Tulostetaan osia Elegoo Neptune 2S:llä ja Voroneilla
- Versio: pib #4 (V4.0.2)
- Aloitettu: laakeripesä D11-R (Ballbearing enclosure right)
- 40% Rectilinear, 0.2mm, TL3/BL3, P2, PETG

## GitHub repo
https://github.com/miika-hakala/3d-printing-configs

## Käytetyt työkalut
- OrcaSlicer (Voron + Ender)
- Mainsail (Klipper UI)
- Onshape (PIB CAD)
- Elegoo Neptune 2S (pib-osat)
- Voron 0.1 (pib-osat)
- Voron Switchwire (pib-osat, kun saadaan toimimaan)

## Tärkeät linkit
- PIB STL: https://github.com/pib-rocks/pib-stls/archive/refs/tags/V4.0.2.zip
- PIB BOM Onshape: https://cad.onshape.com/documents/775cd57fa655e34e0a8b6d93
- Voron Switchwire wiring: https://docs.vorondesign.com/build/electrical/sw_miniE3_v20_wiring.html
