# Työnjohtajan ohje

Tämä repo käyttää kolmea AI-terminaalityökalua. Claude (chat) toimii työnjohtajana —
se suunnittelee tehtävät ja delegoi ne sopivalle työkalulle.

## Työkalut

### Claude Code
- **Paras:** Monimutkaiset tehtävät useissa tiedostoissa, koko repon ymmärtäminen, automaattiset git commitit
- **Käyttö:** `claude` terminaalissa
- **Autentikointi:** Claude Pro/Max tilaus tai API-avain
- **Hyödynnä kun:** Refaktorointi, usean tiedoston muutokset, uudet ominaisuudet

### Gemini CLI
- **Paras:** Isot kontekstit (1M token = koko projekti kerralla), ilmainen peruskäyttö
- **Käyttö:** `gemini` terminaalissa
- **Autentikointi:** Google-tili (ilmainen tier: 1000 pyyntöä/päivä)
- **Hyödynnä kun:** Iso koodianalyysi, dokumentaation lukeminen, hakugrounding uusille kirjastoille

### Codex CLI
- **Paras:** Python/shell-skriptit, turvallinen sandbox-suoritus
- **Käyttö:** `codex` terminaalissa
- **Autentikointi:** ChatGPT Plus tai API-avain
- **Hyödynnä kun:** Dataskriptit, automatisointitehtävät

---

## Tehtävänjako tässä projektissa

| Tehtävätyyppi | Työkalu | Esimerkki |
|---------------|---------|-----------|
| Klipper config muutokset | Claude Code | printer.cfg editointi |
| Firmware build & flash | Claude Code | make menuconfig, make |
| Koko repon analyysi | Gemini CLI | "Mitä kalibroidaan seuraavaksi?" |
| Shell-skriptit | Codex CLI | Automaattiset backup-skriptit |
| SSH-komennot Pille | Claude Code | Switchwire/Voron0 etäkäyttö |

---

## Miten delegoida tehtäviä

Sano Claude-chatille mitä haluaa tehdä, niin Claude muotoilee tarkan ohjeen terminaalityökalulle.

**Esimerkki:**
> "Tee Claude Codella tehtävä: muuta switchwire/printer.cfg:ssä bed_mesh probe_count 6x6 -> 9x9"

---

## SSH-yhteydet
```bash
ssh miika@switchwire-1.local   # tai 192.168.0.190
ssh pi@voron0.local            # tai 192.168.0.223
```

---

## GitHub repo

https://github.com/miika-hakala/3d-printing-configs
