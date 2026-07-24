---
name: irenginiu-adaptacija
description: Spellnook — kaip VIENA scenos nuotrauka tobulai prisitaiko prie telefono (stačio/gulsčio), planšetės ir TV. Gulsčias = pilnas ekranas; stačias = ta pati nuotrauka VISA (contain) + dizainuotas fonas + UI. Naudoti kuriant/keičiant sceną ar UI; PRIVALOMA prieš „padaryta".
---

# Įrenginių adaptacija — VIENA nuotrauka (GALUTINĖ TIESA)

**Auksinė taisyklė:** VIENA nuotrauka scenai. Jokių antrų/portretinių versijų, jokių pratęsimų (outpaint), jokių pakartotinių generacijų. Adaptacija — kodu, ne nauja nuotrauka.

## 1. Gulsčias (landscape · TV · planšetė landscape)
- Nuotrauka per VISĄ ekraną (`object-fit: cover`) — idealu. NELIESTI.
- Immersive (paslėpta status/nav bar).

## 2. Stačias (portretas)
- TA PATI nuotrauka rodoma **VISA** (`object-fit: contain`, sumažinta) — matosi VISKAS (komoda, abi palmės), niekas neapkerpta.
- Aplink laisvą plotą — **šviesus šiltas DIZAINUOTAS fonas** (ne pilka, ne juoda, ne tuščia).
- UI: **žodžių langeliai viršuje**, **LETTER/ZOOM + raidžių ratukas apačioje**, Level+monetos+⚙ viršuje (permatomi). Nieko neužstoja.
- ⚠️ NE full-bleed stačiame (nukirstų komodą/palmę). NE „safe-zone crop". VISA nuotrauka matoma.

## 3. Kodėl taip (fizika)
Plati (16:9) nuotrauka siaurame stačiame (9:19.5) ekrane pilnai užpildyti negali neapkerpant. Todėl: gulsčias = pilnas ekranas; stačias = visa nuotrauka mažesnė + dizainuotas fonas. Savininko patvirtinta.

## 4. Responsive UI
- Santykiniai vienetai (`vw/vh/vmin`, `clamp()`, flex/grid), safe-area insets, TV overscan ~5–10%.
- Orientacijai keičiantis (resize/orientationchange) — persidėlioja automatiškai.

## 5. Rezoliucija (planšetė/TV aštrumas)
- WebP; jei reikia — keli dydžiai (@1x telefonui, @2x planšetei, @3x/4K TV) pagal DPI.

## 6. Testas prieš „padaryta"
- Telefonas stačias (visa nuotr + fonas) IR gulsčias (pilnas ekranas); planšetė; TV. Per naršyklę/DevTools/resize.

## 7. Ko NEDARYTI
- ❌ Antros/portretinės nuotraukos, pratęsimų, pakartotinių generacijų.
- ❌ Full-bleed stačiame (apkerpa daiktus).
- ❌ Generuoti be savininko sutikimo; diegti be savininko patvirtinimo.
