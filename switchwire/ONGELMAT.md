# Voron Switchwire Ongelmat ja Ratkaisut

## TMC2209 stepper-driveri jumittuu virran katketessa (RATKAISTU)
- Oireet: Z-akseli putoaa hallitsemattomasti alas homingissa, moottorit pitävät outoa ääntä
- Syy: Virta katkesi kesken tulostuksen, TMC2209-driverit jäivät virhetilaan
- Ratkaisu: Katkaise KAIKKI virrat (24V + Pi), odota 60 sekuntia, käynnistä uudelleen
- Huom: Pelkkä FIRMWARE_RESTART tai Klipper-restart ei riitä

## USB-yhteysongelma (RATKAISEMATTA)
- SKR Mini E3 V2.0 ei näy /dev/serial/by-id/
- Firmware flashattu onnistuneesti (FIRMWARE.CUR näkyy SD-kortilla)
- Communication interface: USB (vaihdettu UART->USB)
- Pi Zero virtalähde erillinen (PWR IN portissa)
- USB-kaapeli Pi Zero USB-portissa -> SKR Mini micro USB -portissa
- lsusb ei näytä SKR Miniä
- TODO: Kokeile toista USB-kaapelia, tarkista SKR Minin micro USB -portti

## Moonraker ongelmat päivityksen jälkeen
- dbus_fast puuttui -> pip install dbus-fast
- smart_open väärä versio -> pip install --upgrade smart-open
- libunistring.so.2 symlink rikki -> korjattu fsck + manuaalinen symlink
- System päivitys tuhosi kirjastoja -> uusi SD-kortti flashattu MainsailOS 2.2.2

## Klipper MCU firmware vanhentunut
- Päivitys v0.12 -> v0.13 vaatii MCU reflashausta
- STM32F103: käännä make menuconfig (STM32, F103, 28KiB bootloader, USB)
- Flashaus SD-kortilla: kopioi firmware.bin kortille, käynnistä uudelleen
