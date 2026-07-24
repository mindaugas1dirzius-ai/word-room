---
name: irenginiu-adaptacija
description: Spellnook — kaip padaryti, kad žaidimas (vaizdas + UI) TOBULAI prisitaiko prie telefono, planšetės ir TV. Privalomas metodas, kad daugiadaikčio ekrano adaptacija niekada nebūtų problema. Naudoti kuriant/keičiant sceną, UI, splash ar bet ką, kas rodoma ekrane; PRIVALOMA patikrinti prieš „padaryta".
---

# Įrenginių adaptacija — privalomas metodas (telefonas · planšetė · TV)

**Principas:** adaptacijos logika parašoma VIENĄ kartą variklyje → paskui KIEKVIENA scena/ekranas prisitaiko automatiškai. Jokio darbo per sceną. Deterministinis kodas (NE AI agentas — jis nepatikimas ir brangus).

## 1. Vaizdo talpinimas
- **`object-fit: contain`** — visas vaizdas VISADA matomas, niekas nenukerpama jokiame ekrane. Letterbox juostas užpildo **išblukintas to paties vaizdo fonas** → atrodo premium (kaip IG/YouTube).
- **Dvi versijos:** portretas 1080×1920 (telefonas / planšetė portrete) + landscape 1920×1080 (TV / landscape). Variklis parenka pagal orientaciją/aspect.

## 2. Išdėstymas / UI (responsive)
- Tik **santykiniai vienetai:** `vw/vh/vmin/vmax/%`, `clamp()`, flexbox/grid. JOKIŲ fiksuotų px pozicijų.
- **Safe-area insets** (`env(safe-area-inset-*)`) — telefono „notch"/kampams.
- Ratukas / HUD / langeliai **persidėlioja pagal orientaciją:** portrete — apačioje; landscape/TV — šone arba apačioje, didesni.
- Testuok proporcijas: telefonas 9:19.5 ir 9:16, planšetė 3:4 ir 4:3, TV 16:9.

## 3. Scale mechanika
- Dabar: vanilla HTML + CSS (`contain` + responsive) — veikia.
- Upgrade (jei pereisim į Phaser): **Phaser Scale Manager** (`Scale.FIT` / `RESIZE`) tą daro „iš dėžės".

## 4. TV specifika (Fire TV)
- **Overscan saugi zona:** palik ~5–10% paraštę nuo kraštų (TV nukerpa kampus).
- **Pulto navigacija:** D-pad/žymeklis; fokuso būsenos; didesni fokuso taškai.
- Įvesties abstrakcija: lietimas IR pultas — viena logika.

## 5. Testavimas prieš „padaryta" (PRIVALOMA)
- Patikrink VISUOSE: telefonas + planšetė + TV (emuliatorius / resize / DevTools).
- Kriterijus: vaizdas + UI atrodo TOBULAI ir žaidimas pilnai žaidžiamas kiekviename.

## 6. Ko NEDARYTI
- ❌ Fiksuotų px pozicijų / vieno dydžio dizaino.
- ❌ `object-fit: cover` be saugios zonos (nukerpa daiktus).
- ❌ „Pataisysiu vėliau kitam įrenginiui" — statom universaliai IŠ KARTO.
