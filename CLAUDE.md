# CLAUDE.md — projektas „Word Room" (fotorealistiškas žodžių žaidimas)

> Claude Code šį failą skaito AUTOMATIŠKAI. Universalūs principai — `DARBO_PRINCIPAI.md`.

## Kas aš (sesijos vaidmuo)
- Jei esi Claude Code — tu **Code** (koduoji/stato). Planuotojas/dizaineris = **Cowork** (kita aplinka).
- Savininkas — Mindaugas; kalbam lietuviškai, paprastai. Jokių leidimo popup'ų. Pilna autonomija aptartam darbui.

## Cowork ↔ Code sistema (per failus)
| Info | Failas | RAŠO | SKAITO |
|---|---|---|---|
| Žinutės cowork→Code | `COWORK_TO_CODE.md` | Cowork | Code |
| Žinutės Code→cowork | `CODE_TO_COWORK.md` | Code | Cowork |
Protokolas: `git pull` + skaityk `COWORK_TO_CODE.md` → dirbk → rašyk į `CODE_TO_COWORK.md` → `commit` + `push`.

## Projekto specifika
- **Esmė:** mobilus fotorealistiškas žodžių/paslėptų-objektų žaidimas. Žaidėjas mato kambario nuotrauką, randa daiktus ir iš raidžių ratuko sudėlioja jų pavadinimus. Radus — kamera prizoomina, daiktas sureaguoja, garsai.
- **Tiesos šaltinis (skaityk pirma):** `zaidimo-dizainas-ir-taisykles.md` (dizainas, ekonomika, pagalbos, roadmap) → `README.md` → `COWORK_TO_CODE.md`.
- **Aplankas:** `C:\Users\minda\Projects\word-room`
- **Repo (GitHub):** dar nėra — Code sukuria (žr. COWORK_TO_CODE.md).
- **Stack:** viena savarankiška byla `index.html` (nuotrauka įsiūta base64, veikia offline). Vėliau — **Capacitor** Android/iOS.
- **Deploy/test:** GitHub Pages (nuoroda telefonui). Vėliau — app store'ai: Amazon (Fire tablets + TV) → Samsung/Xiaomi/Huawei → Apple → Google Play.
- **Ko NELIESTI:** žaidimo dizaino/mechanikos sprendimų nekeisti be Cowork/savininko (jie surašyti taisyklių doke).
