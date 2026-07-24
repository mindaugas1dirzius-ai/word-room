# 🚀 SPELLNOOK — perdavimas naujai sesijai (VIENA TIESA)

> Šis failas = pilnas startas naujai Cowork sesijai. Perskaityk PRIEŠ pradedant. Viena tiesa, jokių šiukšlių.

## 0. Kas tu ir su kuo dirbi
- Tu — **Cowork** (planuotojas/dizaineris). Kalbam **lietuviškai, paprastai**. Pilna autonomija aptartam darbui, be leidimo popup'ų.
- Savininkas — **Mindaugas** (ne programuotojas). Jo nurodymas nustelbia viską.
- **Code** — Claude Code savininko kompiuteryje: git, buildai (Capacitor/APK), diegimas telefone/planšetėje/TV, Flux generavimas, skriptai, WebP.
- Vaidmenys pilnai: `VAIDMENYS.md` / skill `vaidmenys`.

## 1. Bendravimas (per failus — LOKALUS diskas = tiesa)
- `COWORK_TO_CODE.md` — rašo TIK Cowork (užduotys Code'ui). `CODE_TO_COWORK.md` — rašo TIK Code (statusas). Naujausia VIRŠUJE.
- Cowork rašo per „device bridge" į lokalų diską (git nepushina) → **lokalus failas visada naujausias**. Code skaito iš lokalaus disko.
- ⚠️ Code NIEKADA `git reset/checkout/stash` ant pašto/specų failų.

## 2. PRIVALOMOS TAISYKLĖS (savininko — nepažeisti)
1. **Paštą tikrink kas ~1 min, kai lauki** (`send_later` delay_minutes=1, „NIEKADA NEILGINK"). Dirbant — bent kas ~5 min.
2. **Jokių fal.ai / mokamų generacijų be savininko AIŠKAUS sutikimo** kiekvieną kartą. Kreditai riboti.
3. **Nediegti į telefoną nieko be savininko patvirtinimo.** Srautas: paruošk → PARODYK savininkui pokalbio lange (preview/nuotrauka) → jis „gerai" → TIK TADA Code diegia.
4. **VIENA nuotrauka scenai.** Jokių antrų/portretinių versijų, pratęsimų, pakartotinių generacijų.
5. Būk **sprendžiantis ir paprastas** — ne ilgi aiškinimai. Savininkas nori aiškaus rezultato.

## 3. Projektas
- **Spellnook** — mobilus fotorealistiškas žodžių / paslėptų-objektų žaidimas. Žaidėjas mato realią sceną, randa daiktus, iš raidžių ratuko sudėlioja pavadinimus; radus — kamera prizoomina, daiktas sureaguoja, garsai.
- **Tiesos šaltinis (skaityk pirma):** `zaidimo-dizainas-ir-taisykles.md` (dizainas, ekonomika, journey, roadmap, turinys=plug-in). Tada `README.md`, `CLAUDE.md`.
- **Aplankas:** `C:\Users\minda\Projects\word-room`
- **Repo:** https://github.com/mindaugas1dirzius-ai/word-room · **Pages (peržiūra telefone):** https://mindaugas1dirzius-ai.github.io/word-room/
- **Stack:** viena `index.html` (duomenimis valdomas variklis; scena = plug-in JSON) → vėliau Capacitor Android/iOS. Store'ai: Amazon (Fire tablet+TV) → Samsung/Xiaomi/Huawei → Apple → Google.

## 4. VAIZDO / EKRANO TIESA (svarbiausia — čia buvo daug painiavos)
- **Viena nuotrauka scenai:** `scenes/t1-r1-living-room_landscape.webp` (plati, savininko mylima).
- **Gulsčias:** nuotrauka per visą ekraną (`cover`) — IDEALU, NELIESTI.
- **Stačias:** TA PATI nuotrauka rodoma **VISA** (`contain`, sumažinta) — matosi VISKAS (komoda, abi palmės), niekas neapkerpta; aplink **šviesus dizainuotas fonas**; žodžiai viršuje, ratukas apačioje.
- **Fizika (kodėl):** plati nuotrauka siaurame stačiame ekrane pilnai neužpildo neapkerpant → todėl stačiame `contain` (visa matoma, mažesnė). Full-bleed/pratęsimas stačiame NUKERPA komodą/palmę → NEDAROM.
- Pilnas metodas: `IRENGINIU_ADAPTACIJA.md` (skill).

## 5. Kur esam (būsena 2026-07-24)
- ✅ R1 „Svetainė" scena veikia (duomenimis valdomas variklis). Landscape — idealus (pilnas ekranas).
- ⏳ **Stačio išdėstymas** (1 variantas: visa nuotrauka `contain` + šviesus dizainuotas fonas + UI) paruoštas Code, matomas **GitHub Pages** (NEĮDIEGTA telefone). **Laukiam savininko patvirtinimo telefone stačiai.**
- Kai savininkas patvirtins → Code diegia telefone.
- Code turi ištrinti šiukšlę `scenes/t1-r1-living-room_portrait.webp` (dublikatas, nenaudojamas).

## 6. Toliau (eilė)
1. Savininkas patvirtina stačią (Pages) → Code diegia telefone.
2. Persistent config (immersive+orientacija į patvarų config, kad `cap add` neištrintų).
3. Kitos scenos tuo pačiu principu (viena nuotrauka/scena). R2 „Virtuvė" — spec pradėtas GDD.
4. Užrakinti scenos-kūrimo recipe į skill'ą (kai R1 100% patvirtinta).

## 7. KLAIDOS, KURIŲ NEKARTOTI (iš praeitos sesijos)
- ❌ Rodyti/naudoti KITĄ nuotrauką nei mylimą landscape (buvo naudotas kitas renderis maketuose — savininkas pyko). Maketuose/preview — TIK `t1-r1-living-room_landscape.webp`.
- ❌ Full-bleed/„safe-zone"/pratęsimas stačiame (nukerpa daiktus). Stačias = `contain`, visa matoma.
- ❌ Generuoti ar diegti be savininko sutikimo.
- ❌ Ilgi hedge'inimai. Būk aiškus, paprastas, sprendžiantis.

## 8. Failų žemėlapis
- `zaidimo-dizainas-ir-taisykles.md` — GDD (dizaino tiesa).
- `scenes/T1_R1_svetaine.md` — R1 spec (daiktai, žodžiai, raidės, §10 ekrano tiesa).
- `scenes/t1-r1-living-room_landscape.webp` — VIENINTELĖ R1 nuotrauka.
- `IRENGINIU_ADAPTACIJA.md` — ekrano adaptacijos metodas (skill).
- `VAIDMENYS.md` — vaidmenys (skill).
- `CLAUDE.md` — Code auto-skaito (taisyklės, protokolas).
- `COWORK_TO_CODE.md` / `CODE_TO_COWORK.md` — paštas.
