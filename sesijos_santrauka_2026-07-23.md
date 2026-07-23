# Sesijos santrauka — 2026-07-23 (Word Room)

## Kas nuveikta
- Sukurtas fotorealistiškas žodžių/paslėptų-objektų žaidimo prototipas — **1 lygis** (`index.html`, savarankiška byla, nuotrauka įsiūta base64).
- Nuotrauka sugeneruota **Canva** (kambarys: MAP, LAMP, PALM, TABLE). Žemėlapio tekstūra iškirpta iš tos pačios nuotraukos.
- Mechanika: permatomas raidžių ratukas + permatomi raidžių apskritimai; statiškas vaizdas; radus žodį — kamera prizoomina + daikto reakcija (lempa užsidega, žemėlapis blyksteli, palmė svyruoja); garsai (WebAudio, be failų).
- Sunkumas: 4 objektai (LAMP, MAP, PALM, TABLE) iš 8 raidžių (A,B,E,L,M,P,T), BE žymeklių, sąžininga (jokių „apgaulės" žodžių; premijiniai teigiami).
- Pagalbos: **LETTER −20◈** (atsitiktinė raidė iš neatspėtų; atskleidus visas žodžio raides → auto-užskaito), **ZOOM −50◈** (priartina vis kitą daiktą, neišsprendžia). Uždarbis: daiktas **+20◈**, premija **+5◈**. „Next Level" išvalo viską.
- Žaidimas angliškai.
- Sukurtas projekto aplankas `C:\Users\minda\Projects\word-room` su Cowork↔Code sistema (CLAUDE.md, COWORK_TO_CODE.md, CODE_TO_COWORK.md, DARBO_PRINCIPAI.md, .claude/settings.json, README.md, index.html, taisyklių dokas, 2 skill'ai .claude/skills/).
- Į `COWORK_TO_CODE.md` įrašyta užduotis Code'ui: įkelti į GitHub (viešas repo) + įjungti Pages + grąžinti nuorodą telefonui.

## Priimti sprendimai
- **Kryptis:** fotorealizmas per 2.5D nuotraukas, NE tikro laiko 3D (3D prototipas `word-fps-3d` atmestas kaip „pigus" be brangių 3D modelių).
- **Vaidmenys:** Cowork = vadovas/planuotojas; Code = koduotojas (Claude Code kompe).
- **GitHub/hostingas — TIK per Code** (Cowork iš debesų negali: git per mounted FS neveikia, viešieji hostai blokuoti, GitHub connector'io nėra, tokenų liesti negalima).
- **Nuotraukų taisyklė:** visi ieškomi objektai PILNAI kadre, su paraštėmis (nieko nenukirsta).
- **Paleidimo tvarka:** Amazon (Fire tablets + TV) → Samsung/Xiaomi/Huawei → Apple → Google Play (per Capacitor).

## Laukiam / atviri
- Code turi įkelti į GitHub ir grąžinti Pages nuorodą (`CODE_TO_COWORK.md`) → testas telefone.
- 2 lygio scena sugeneruota Canvoje (4 kandidatai), laukia savininko atsisiuntimo.

## Kitas žingsnis
Patikrinti Code atsakymą (nuoroda); po testo telefone — turinys (2 lygis), ekonomikos balansas.
