---
name: irenginiu-adaptacija
description: Spellnook — kaip padaryti, kad žaidimas (vaizdas + UI) TOBULAI prisitaiko prie telefono, planšetės ir TV su VIENA nuotrauka. Metodas: SAUGI ZONA + pratęstas fonas. Naudoti kuriant/keičiant sceną, UI, splash; PRIVALOMA patikrinti prieš „padaryta".
---

# Įrenginių adaptacija — VIENA nuotrauka, saugi zona (telefonas · planšetė · TV)

**Auksinė taisyklė:** VIENA nuotrauka scenai (NE kelios). Ji sukomponuojama taip, kad tiktų VISOMS orientacijoms per „saugią zoną" + pratęstą foną. Adaptacijos logika parašoma VIENĄ kartą variklyje → kiekviena scena prisitaiko automatiškai.

## 1. SAUGI ZONA (Safe Area) — svarbiausia
- **Visi svarbūs daiktai** (MAP, LAMP, PALM, TABLE + premijiniai + raidžių ratuko vieta) generuojami **centriniame „saugiame" kvadrate** (~1:1, arba centrinė 4:3 zona). NIEKADA prie kraštų.
- **Pratęstas fonas (extents):** nuotraukos kraštai (grindys, lubos, sienų šonai) generuojami **platesni/aukštesni, nei matys vartotojas.** Keičiantis ekranui, žaidimas rodo daugiau ar mažiau papildomo fono — bet svarbūs daiktai niekada neišeina iš kadro.
- **Master proporcija:** generuok ~**4:3 arba 16:10**, daiktai sukoncentruoti arti CENTRO, aplink — atsarginis fonas iš visų pusių.

## 2. Responsive mastelis (variklis)
- **Skaičiuok pagal TRUMPĄJĄ kraštinę:** `cover`/`contain` su apribojimais; mastelio „Match" tarp 0 (plotis) ir 1 (aukštis) dinamiškai pagal orientaciją.
- `cover` užpildo VISĄ ekraną (JOKIŲ juostų) — saugi zona garantuoja, kad daiktai niekada neapkerpami.
- Tik santykiniai vienetai UI: `vw/vh/vmin/vmax/%`, `clamp()`, flex/grid. JOKIŲ fiksuotų px pozicijų.

## 3. Enkaravimas (jei daiktai — atskiri PNG virš fono)
- Staliukas/lempa → `Bottom-Left`; žemėlapis → `Top-Center/Top-Left`; palmė → `Right-Center/Bottom-Right`; **ratukas → `Bottom-Center`.**
- Ekranui tempiantis, objektai „prilimpa" prie kampų, tuščia centro erdvė didėja/mažėja — daiktai proporcijų nepraranda.

## 4. Orientacijų išdėstymas (portrait ↔ landscape)
- Variklis reaguoja į orientacijos kaitą (OrientationBuilder / resize):
  - **Portretas:** ratukas apačioje; daiktai labiau susispaudę į viršų/centrą.
  - **Landscape / TV:** ratukas gali persikelti į šoną/centrą; daiktai išsisklaido plačiau.
- Full-screen **immersive** (paslėpta status bar + nav bar) — JOKIO laiko/baterijos/juostų.

## 5. Rezoliucijos klasteriai (planšetė / 4K TV aštrumas)
- Saugom kelis to paties vaizdo dydžius: **@1x telefonui, @2x planšetei, @3x/4K TV.**
- Programa pagal DPI/rezoliuciją pati užkrauna reikiamą failą → vaizdas visada aštrus, ne pikseliuotas.

## 6. Testas prieš „padaryta" (PRIVALOMA)
- Telefonas 9:19.5 (+pasukus), planšetė 4:3/3:4, TV 16:9 — per emuliatorių/DevTools/resize.
- Kriterijus: `cover` užpildo, VISI daiktai saugioje zonoje matomi, UI persidėlioja, JOKIŲ juostų.

## 7. Ko NEDARYTI
- ❌ Kelių/skirtingų nuotraukų tai pačiai scenai (VIENA + saugi zona).
- ❌ Daiktų prie kraštų (juos apkerpa).
- ❌ Fiksuotų px / vieno dydžio dizaino.
- ❌ Generuoti be savininko sutikimo; diegti be savininko patvirtinimo.
