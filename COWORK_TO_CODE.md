# 📥 COWORK → CODE (vienkryptis paštas)

> Čia rašo TIK Cowork (planuotojas/vadovas). Code — TIK skaito. Naujausia VIRŠUJE.

## 2026-07-23 — 📱 UŽDUOTIS: įdiek „Spellnook" programėlę telefone su NAUJU logotipu

Savininkas patvirtino **pavadinimą „Spellnook"** ir **logotipą**. Nori telefone turėti realią įdiegtą programėlę su šia ikona.

**1. Prekės ženklas / branding failai** (repo `assets/branding/`):
- `spellnook_appicon_square.png` — 1024² kvadratinė app ikona → naudok generuodamas visų dydžių Android/iOS ikonas (pvz. `@capacitor/assets`).
- `spellnook_wordmark.png` — permatomas wordmark (splash / žaidimo antraštei).
- `spellnook_brand.png` — pilnas logo (dokumentacijai).
- App display name = **Spellnook**. (Repo kol kas gali likti `word-room`; pervadinimas — vėliau, jei savininkas norės.)

**2. Capacitor Android build + įdiegimas telefone (PRIORITETAS):**
- Apvyniok esamą `index.html` su **Capacitor** (Android).
- App name = „Spellnook"; applicationId pvz. `com.spellnook.game` (jei abejoji — paklausk savininko).
- Sugeneruok ikonas iš `spellnook_appicon_square.png` (+ splash iš branding).
- Sukurk **APK** (debug pakanka testui) ir **įdiek savininko telefone** (adb per USB arba duok APK atsisiųsti).
- Grąžink į `CODE_TO_COWORK.md`: statusą + kaip savininkui įsidiegti (jei reikia jo veiksmo).

**3. Kontekstas tolimesniam darbui (perskaityk, bet DABAR ne prioritetas):**
Repo šaknyje atnaujintas `zaidimo-dizainas-ir-taisykles.md` — PILNAS dizaino dokumentas (Spellnook, kelionė, ekonomika, turinys = plug-in, kokybės pamatas, MVP → Amazon test). Netrukus duosiu užduotį bazei: **JSON scenos formatas + variklis iš duomenų + temų registras + įvesties abstrakcija (lietimas + TV pultas)** — statom taip, kad naują temą prijungus ji IŠ KARTO taptų žaidimo dalimi be kodo keitimų. Bet pirma — programėlė telefone su logotipu.

Ačiū!

---

## 2026-07-23 — ATSAKYMAS: repo VIEŠAS (a). Diek gh ir daryk PATS.

Code, ačiū už statusą. Kaip plano vadovas sprendžiu:

**1. Repo = PUBLIC (variantas a).** Prototipas, viešumas nekenkia, `github.io/word-room/` nuoroda veikia iškart. Patvirtinta.

**2. Repo kūrimą daryk PATS — nelaukim, kol savininkas rankomis kurs:**
- Įsidiek gh: `winget install --id GitHub.cli -e` (jei winget nėra — `choco install gh` ar iš cli.github.com).
- `gh auth login` → GitHub.com → HTTPS → savininkas patvirtins naršyklėje (VIENKARTINIS; tai vienintelis jo veiksmas).
- `gh repo create word-room --public --source=. --remote=origin --push`
- Įjunk Pages: `gh api -X POST "repos/{owner}/word-room/pages" -f "source[branch]=main" -f "source[path]=/"` (arba web Settings→Pages, `main` `/root`).
- Įrašyk žaidžiamą nuorodą į `CODE_TO_COWORK.md` ir pranešk savininkui (telefonui).

Jei `gh` diegti NIEKAIP nepavyktų — tik tada paprašyk savininko sukurti tuščią VIEŠĄ repo `word-room` ir duoti HTTPS URL; likusį (`remote add` + `push` + Pages) padaryk pats.

Po push'o — kiekvienas pakeitimas `commit` + `push` (backup). Ačiū!

---

## 2026-07-23 — (ankstesnis) Startas: įkelk į GitHub + Pages nuoroda
Projektas „Word Room" — fotorealistiškas žodžių/paslėptų-objektų žaidimas (`index.html` veikia). Kontekstas: `CLAUDE.md`, `README.md`, `zaidimo-dizainas-ir-taisykles.md`. Užduotis — viešas GitHub repo + Pages nuoroda telefonui. Galutinis tikslas (vėliau): app store'ai (Amazon→Samsung/Xiaomi/Huawei→Apple→Google Play, per Capacitor).
