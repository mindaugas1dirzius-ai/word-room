# 📥 COWORK → CODE (vienkryptis paštas)

> Čia rašo TIK Cowork (planuotojas/vadovas). Code — TIK skaito. Naujausia VIRŠUJE.

## 2026-07-23 — DABAR: įkelk projektą į GitHub + padaryk Pages nuorodą telefonui

Code, savininkas nori dabar. Prašau atlik (yra skill'as `.claude/skills/github-naujas-projektas`):

1. Jei liko nepilnas `.git` arba aplankas `_git_broken_TODELETE` — pašalink; tada `git init`, `git add -A`, `git commit`.
2. Prisijunk prie GitHub (`gh auth status` / `gh auth login`) ir sukurk **NAUJĄ VIEŠĄ** repo `word-room`, `push`.
   - Viešą — kad veiktų nemokama GitHub Pages. ⚠️ Prie kitų savininko repo NELĮSK, tik naujas.
3. Įjunk **GitHub Pages** (main / root) → gauk viešą nuorodą `https://<vartotojas>.github.io/word-room/`.
4. **Įrašyk gautą nuorodą į `CODE_TO_COWORK.md`** ir pasakyk savininkui — kad atidarytų telefone ir išbandytų.

**Kas tai per projektas:** fotorealistiškas žodžių/paslėptų-objektų žaidimas. Detalės — `CLAUDE.md`, `README.md`, `zaidimo-dizainas-ir-taisykles.md`. Žaidimas jau veikia: `index.html` (savarankiška byla, nuotrauka įsiūta base64). Reikia tik GitHub + Pages nuorodos.

**Galutinis tikslas (vėliau):** app store'ai — Amazon (Fire tablets + TV) → Samsung/Xiaomi/Huawei → Apple → Google Play (per Capacitor). Dabar UŽTENKA GitHub + Pages nuorodos.

**P.S.:** git iš Cowork (debesų) pusės neveikia (mounted FS), todėl `.git` nepilnas — tvarkyk savo (Code) pusėje, ten viskas veiks. Ačiū!
