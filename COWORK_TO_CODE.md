# 📥 COWORK → CODE (vienkryptis paštas)

> Čia rašo TIK Cowork (planuotojas/vadovas). Code — TIK skaito. Naujausia VIRŠUJE.

## 2026-07-24 — 🧩 UŽDUOTIS: įregistruok „vaidmenys" skill'ą

Savininkas nori, kad ABI pusės (Cowork ir Code) automatiškai vadovautųsi vaidmenų pasidalinimu. Turinys jau paruoštas — **`VAIDMENYS.md`** (repo šaknis; jau su frontmatter: name/description).
- **Įrašyk jį kaip skill'ą:** `.claude/skills/vaidmenys/SKILL.md` (aš į `.claude` per bridge rašyti negaliu — tu gali). Turinį imk iš `VAIDMENYS.md`.
- Nuo tada — abu vadovaujamės juo. Jei kuri pusė imasi NE savo darbo → primename: „pagal vaidmenis — tai X darbas". Cowork — pagrindinis priminėjas.

---

## 2026-07-23 — 🏭 UŽDUOTIS: Flux „vaizdų fabrikas" (spec → vaizdas su kontrole)

**Eiliškumas:** 1) app telefone su logotipu (žemiau) — PIRMA; 2) šis Flux fabrikas — po to (arba paraleliai, jei turi laiko).

**Tikslas:** pastatyti turinio konvejerį, kuris iš scenos SPECO generuoja būtent tokį vaizdą (ne atsitiktinį), su kompozicijos kontrole. Pilna eiga — GDD **§15** („Turinys-PIRMA eiga" + „Scenos speco pavyzdys"). Optimizacija — §14b.

**Ką padaryti:**
1. **Flux API** per **fal.ai** arba **Replicate** (rekomenduoju fal.ai — greitas). Reikės API rakto. ⚠️ Savininkui — tik susikurti paskyrą + pridėti mokėjimą (generavimas centai/vaizdas). Jei reikia — parašyk į CODE_TO_COWORK.md, ką tiksliai savininkui paspausti.
2. **Generavimo skriptas** (untracked/laikinas ok kol MVP), kuris:
   - Ima scenos specą (JSON: tema, daiktai, žodžiai, layout, prompt).
   - Kviečia Flux (pradžiai — **flux dev** kokybė/kaina; hero — pro). Jei įmanoma — ControlNet/layout daiktų pozicijoms; jei ne — prompt + pergeneravimas kol atitinka.
   - Gauna vaizdą → **auto-optimizacija į WebP** (tinkamas dydis).
   - Išsaugo vaizdą + paruošia lygio JSON „stub" (objects su vietomis — v1 gali būti iš mūsų layout'o; v2 auto-segmentacija).
3. **TESTAS #1 (PIRMAS) — R1 „Svetainė":** pilnas specas su premium prompt'u repo — **`scenes/T1_R1_svetaine.md`** (ten: galutinis Flux prompt'as, 4 privalomi + 3 premijiniai daiktai, layout, JSON). Sugeneruok **portretą 1080×1920 IR landscape 1920×1080** iš to paties prompt'o, optimizuok (WebP), grąžink rezultatą į CODE_TO_COWORK.md (ar visi daiktai pilni). *(Savininkas jau matė horizontalų juodraštį — kokybė puiki; reikia portreto+landscape per Flux + hitbox'ai.)*
4. **TESTAS #2 — Virtuvė** (specas ŽEMIAU) — po R1.

**TEST SPECAS — „Namai / R2 Virtuvė" (lengva):**
- Daiktai (žodžiai): **POT, PAN, CUP, CAN**. Raidės: A,C,N,O,P,T,U. Premijiniai: TACO, PACT, CAP, OAT, NUT, CUT, TAN, ACT.
- Layout (grubiai, 1080×1920, daiktui centras): POT ~ (270,920) ant viryklės; PAN ~ (820,520) kabo ant sienos; CUP ~ (300,1320) ant stalo; CAN ~ (860,1010) lentynoje. Visi PILNI, su paraštėmis; rami zona centre-apačioje UI.

**FLUX PROMPT (Virtuvė):**
```
Photorealistic vertical interior photograph of a bright, cozy home kitchen in warm morning light, portrait 1080x1920. Every object fully visible with margins, nothing cropped at the edges: a metal cooking POT on the stovetop at center-left, a frying PAN hanging on the wall at upper-right, a ceramic coffee CUP on a wooden table at lower-left, a metal tin CAN on an open shelf at right. Keep a calmer, less cluttered area in the lower-center for game UI. Soft natural shadows, high detail, inviting, clean. No text, no letters, no words, no numbers, no watermark, no people, no brand logos.
Negative: cropped objects, text, watermark, people, clutter in center.
```
Stiliaus pastaba: fotorealizmas, jauku, šviesu. Vėliau užfiksuosim vieną stiliaus nuorodą (LoRA/seed), kad VISOS scenos atrodytų vientisai — bet testui užtenka šito.

Kai bus rezultatas — pridedu daugiau specų (visos 3 temos §22). Ačiū!

---

## 2026-07-23 — 📱 UŽDUOTIS: įdiek „Spellnook" programėlę telefone su NAUJU logotipu

Savininkas patvirtino **pavadinimą „Spellnook"** ir **logotipą**. Nori telefone turėti realią įdiegtą programėlę su šia ikona.

**1. Prekės ženklas / branding failai** (repo `assets/branding/`):
- `spellnook_appicon_square.png` — 1024² kvadratinė app ikona → naudok generuodamas visų dydžių Android/iOS ikonas (pvz. `@capacitor/assets`).
- `spellnook_wordmark.png` — permatomas wordmark (splash / žaidimo antraštei).
- `spellnook_brand.png` — pilnas logo (dokumentacijai).
- ✅ **`spellnook_splash.png` — GALUTINIS splash / paleidimo ekranas (PATVIRTINTA savininko). Naudok kaip Capacitor splash screen.**
- App display name = **Spellnook**. (Repo kol kas gali likti `word-room`; pervadinimas — vėliau, jei savininkas norės.)

**2. Capacitor Android build + įdiegimas telefone (PRIORITETAS):**
- Apvyniok esamą `index.html` su **Capacitor** (Android).
- App name = „Spellnook"; applicationId pvz. `com.spellnook.game` (jei abejoji — paklausk savininko).
- Sugeneruok ikonas iš `spellnook_appicon_square.png` + **splash screen iš `spellnook_splash.png`** (jau galutinis, patvirtintas).
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
