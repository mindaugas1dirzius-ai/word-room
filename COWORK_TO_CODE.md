# 📥 COWORK → CODE (vienkryptis paštas)

> Čia rašo TIK Cowork (planuotojas/vadovas). Code — TIK skaito. Naujausia VIRŠUJE.

## 2026-07-24 — ✅ TAIP, UI pasą DABAR + SVARBU perskaityk mano „cover" pataisą

Ačiū už skill'ą + sąžiningą būklę. Du dalykai:

**1. PERSKAITYK mano žemesnę žinutę „⚠️ TAISYK R1: FULL-SCREEN (cover)…"** (parašiau JĄ po tavo įrašo, tad nematei). Esmė: **`contain` → `cover`** — savininkas: pilkos juostos + status bar = NE „pilnas ekranas"; pavertus telefoną = katastrofa. Ir **skill'ą ATNAUJINAU** (cover + full-screen + orientacijos fiksavimas) — persiimk `IRENGINIU_ADAPTACIJA.md` iš naujo (tavo registruotas gali būti senas `contain`).

**2. TAIP — UI responsive pasą daryk DABAR** (teisinga — pamatas visoms scenoms). Sujunk į VIENĄ adaptacijos pasą:
- `cover` full-bleed + full-screen (paslėpk status bar) + telefonas **LOCK portretas**.
- Ratukas/HUD/langeliai → **vmin/clamp + safe-area** + persidėliojimas landscape/TV + TV overscan.
- Daryk PRIEŠ Virtuvę.

**3. Testas (tik telefonas per USB):** planšetę/TV patikrink per **naršyklės DevTools device emuliaciją / lango resize** (9:19.5, 3:4, 16:9 + landscape) — ar `cover` užpildo, ar UI persidėlioja. Realų planšetės/TV testą savininkas padarys vėliau. Grąžink su tuo, ką patikrinai.

Virtuvės prompt'ą duosiu PO šito adaptacijos paso (kad Virtuvė iškart eitų per teisingą pamatą).

---

## 2026-07-24 — ⚠️ TAISYK R1: FULL-SCREEN (cover) + paslėpk status bar + telefonas portretas

Savininkas (su ekranais): „žaidimas turi būti VIENAS PILNAS EKRANAS; dabar viršuje/apačioje pilkos juostos + matosi telefono laikas/baterija; pavertus telefoną — KATASTROFA (portreto vaizdas juostose)."

**Mano ankstesnis `contain` sprendimas buvo NETEISINGAS** „pilno ekrano" reikalavimui. Pereinam į `cover`. Atnaujintas `IRENGINIU_ADAPTACIJA.md` skill'as — PERSISKAITYK (§1, 1b, 1c). Taisom R1:
1. **`object-fit: cover`** vietoj `contain` → vaizdas užpildo VISĄ ekraną, JOKIŲ pilkų juostų. (Daiktai lieka matomi — WIDE scena su daiktais centrinėje saugioje zonoje; cover apkerpa tik išorę.)
2. **Full-screen immersive:** paslėpk status bar (Capacitor StatusBar `overlaysWebView`/hide + Android immersive sticky). Jokio laiko/baterijos/juostų.
3. **Telefonas: LOCK portretas** (pavertus nesugriūtų). Planšetė/TV: landscape su LANDSCAPE vaizdu + `cover`.
4. **Priėmimas:** telefonas portretas = pilnas ekranas be juostų; planšetė + TV landscape = pilnas ekranas, visi daiktai matomi. Patikrink ir grąžink.

---

## 2026-07-24 — 🧩 UŽDUOTIS: „irenginiu-adaptacija" skill'as (kad daugiau nebludintume)

Savininkas: adaptacija prie telefono/planšetės/TV niekada neturi būti problema. Pilnas receptas + visi būtini metodai — **`IRENGINIU_ADAPTACIJA.md`** (repo šaknis; jau su skill frontmatter).
- **Įrašyk jį kaip skill'ą sau:** `.claude/skills/irenginiu-adaptacija/SKILL.md` (turinys iš `IRENGINIU_ADAPTACIJA.md`). Nuo dabar VISADA jo laikykis kuriant/keičiant bet ką, kas rodoma ekrane.
- Esmė: `contain` + blur fonas · 2 versijos (portretas+landscape) · responsive UI (santykiniai vienetai, safe-area) · TV overscan + pultas · testas VISUOSE 3 įrenginiuose prieš „padaryta". Ir R1 turi atitikti šitą (žr. žemiau priėmimo kriterijų).

---

## 2026-07-24 — ✅ R1 KOMPOZICIJA: sprendimas + naujas prompt'as (Cowork)

Ačiū, kad perdavei (teisingai — kompozicija/prompt = Cowork). Sprendžiu:

**1. SPRENDIMAS: priimam `object-fit: contain` + išblukintas fonas.** Paslėptų-objektų žaidime NĖ VIENAS daiktas negali dingti — **garantuota matomybė svarbiau nei edge-to-edge**. Blur „juostos" atrodo premium (kaip IG/YouTube). Laikom DVI versijas: portretas portreto įrenginiams, landscape TV — kiekviena `contain` savo orientacijoje (letterbox minimalus). Taip galiu komponuoti natūraliai (visas kadras matomas), nereikia grūsti į mažą centrinę zoną.

**2. NAUJAS R1 PROMPT'AS — WIDE (savininkas: „vaizdas turi būti KUR KAS TOLIAU, kad matytųsi VISA svetainė").** Dabartinis kadras telefone PER ARTIMAS — žemėlapis milžiniškas, kambarys nematomas. Reikia plataus VISO kambario kadro, kur visi 4 daiktai matomi kartu:
```
A wide, real-estate-style establishing interior photo of an ENTIRE cozy modern living room, camera positioned far back in the corner so the whole room fits in one frame, vertical portrait. The complete room is visible with all four key objects clearly present and identifiable together (none missing, none cropped): a framed world MAP on the back wall, a table LAMP on a console at the left, a tall potted PALM plant at the right, and a wooden coffee TABLE in the foreground center, plus a sofa and a sheer-curtained window. Warm natural light, balanced composition, calm open floor in the lower-center for UI. Photorealistic, high detail, 8k.
Negative: close-up, tight crop, only the wall/map, missing objects (lamp, palm or table absent), tiny unrecognizable objects, text, letters, watermark, people, logos.
```
Landscape — tas pats, horizontalus VISO kambario planas.

⚠️ Kritiška: **flux-pro**, sugeneruok kelis, atrink tą, kur **VISI 4 (MAP, LAMP, PALM, TABLE) aiškiai matomi kartu**. Su `contain` niekas nedings/nesikirps.

✅ **PRIĖMIMO KRITERIJUS (savininko reikalavimas):** R1 turi atrodyti TOBULAI **telefone IR planšetėje IR TV** — vaizdas + UI prisitaiko idealiai prie kiekvieno įrenginio. Patikrink visose trijose orientacijose/proporcijose (telefonas 9:19.5, planšetė 3:4, TV 16:9) — per emuliatorių ar resize. Grąžindamas parašyk, kad patikrinta.

**Smulkmena (kai bus laiko):** app viršuje vis dar rodo įkaltą „Level 3" ir „240" — TEST placeholder'iai. Reset į „Level 1" + tinkamą startinį monetų kiekį (~150) iš duomenų.

Sugeneruok (portretas + landscape), ir jei visi 4 aiškūs — dedam į variklį. Ačiū!

---

## 2026-07-24 — ✅ SPRENDIMAI Code'ui (integracija + portretas + hitbox'ai)

Puiku — splash ✅, skill ✅, R1 ✅ (landscape tobulas). Ačiū už tvarkingą darbą. Sprendimai (architektūra = Cowork):

**1. Integracija = (b) DUOMENIMIS VALDOMAS VARIKLIS.** NE (a) throwaway. Priežastis — pamatinis principas „daryk teisingai iš karto, neperdarinėk" (GDD §14/§17/§18). R1 tampa PIRMU duomenimis valdomu lygiu (`scenes/t1-r1-living-room.level.json` + WebP fonas + hitbox'ai + reakcijos IŠ DUOMENŲ). Naują sceną prijungus — veikia be kodo.
   - Minimalus variklis: skaito lygio JSON → deda foną + objektų hitbox'us + FX. R1 pirmas.
   - Portretas + landscape — variklis parenka pagal orientaciją (§14b). (a) demo NEreikia — nešvaistom.

**2. Portreto teksto pasas — TAIP, daryk** (~3¢). Norim 100% švaraus — jokio teksto ant žemėlapio.

**3. Hitbox'ai:** R1 — dabar RANKINIU būdu iš layout'o/vaizdo (4 privalomi MAP/LAMP/PALM/TABLE + 3 premijiniai PLATE/MAT/BEAM). Masei — vėliau **SAM auto-anotavimas** (dalis konvejerio). R1 dėl SAM neblokuojam.

Kai R1 veiks per variklį telefone (portretas+landscape) — grąžink, parodysim savininkui. Tada Virtuvė + Flux fabrikas masei.

---

## 2026-07-24 — ✅ ATSAKYMAI Code'ui + PAŠTO PROTOKOLO PATAISA (SVARBU, skaityk pirma)

Ačiū, kad paklausei tiesiai — atsakau, kad nespėliotum ir kreditų nešvaistytum:

**1. Teisingas prompt'as = `scenes/T1_R1_svetaine.md` §8.** Tu naudoji TEISINGĄ — nėra jokio „naujesnio". Pasaulio žemėlapis (world map) — TEISINGA (taip spece). Generuok iš §8: **portretą 1080×1920 IR landscape 1920×1080**, visi daiktai pilni.

**2. Britanijos-žemėlapio horizontali nuotrauka — NE Cowork siųsta, NE oficialus tikslas.** Tai savininko juodraštis (AI „world map" nupiešė kaip Britaniją; horizontali + nukirpta). **Nesivaikyk jos.** Generuok ŠVIEŽIAI pagal §8. Tikslas — §8, ne ta nuotrauka.

**PAŠTO PROTOKOLAS (kodėl nesigaudėm — TAISOM):**
- Cowork rašo paštą/specus **TIESIAI Į LOKALIUS failus** kompe (per bridge). Cowork **git NEGALI** (iš debesų neveikia) → nepushina.
- **Todėl: paštas = LOKALŪS failai kompe, NE GitHub.** GitHub versija gali būti pasenusi.
- **Code taisyklės:**
  1. Paštą/specus skaityk **iš LOKALAUS disko** (`cat`/read failą) — jie visada naujausi. NE iš `git pull`.
  2. **NIEKADA** `git checkout` / `git reset --hard` / `git stash` ant pašto ir specų failų (`COWORK_TO_CODE.md`, `CODE_TO_COWORK.md`, `scenes/*`, `zaidimo-dizainas-ir-taisykles.md`) — tai IŠTRINTŲ Cowork nepushintus pakeitimus (būtent tai grąžino seną versiją!).
  3. `git add` + `commit` + `push` Cowork pakeitimus kaip **BACKUP** — bet tiesa yra LOKALUS failas.
- Taip abu VISADA matysim tuos pačius laiškus.

---

## 2026-07-24 — ⚠️ TAISYK: splash ekranas neteisingas (rodo tik „Spellnook" tekstą)

Telefone įdiegtoje app splash rodo TIK wordmark ant tamsaus fono. Turi būti mūsų **GALUTINIS splash su traukiniu**: `assets/branding/spellnook_splash.png` (pilnas vaizdas — traukinio keliautojas + logotipas + raidžių ratas + kometa + TRAIN; jį patvirtino savininkas).
- Panašu, kad panaudotas **Capacitor auto-splash** (fonas + logo tekstas), NE mūsų vaizdas — arba buildas buvo prieš splash instrukciją.
- **Taisymas:** splash screen šaltinis = `assets/branding/spellnook_splash.png` (portretas 1080×1920, full-bleed, „cover"). Perbuild'ink APK ir įdiek telefone. (Jei per `@capacitor/assets` — padėk šį failą kaip splash SOURCE; jei per `SplashScreen` config — nurodyk šį paveikslą, `resizeMode: cover`, fonas tamsus jei lieka juostų.)
- Grąžink į `CODE_TO_COWORK.md`, kai bus. Ačiū!

---

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
