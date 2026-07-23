---
name: github-naujas-projektas
description: >-
  Kaip prisijungti prie GitHub ir įkelti NAUJĄ projektą (sukurti repo, push,
  įjungti GitHub Pages ir gauti viešą nuorodą telefonui). Aktyvuoti kai:
  „įkelk į github", „push į github", „sukurk repo", „padaryk pages nuorodą",
  „pridėk projektą į github", „backup į github". Skirta Claude Code pusei
  (savininko kompe, kur yra git + internetas + prisijungimai).
---

# GitHub — įkelti naują projektą (repo + push + Pages nuoroda)

> Vykdo Claude Code savininko kompe (git + internetas + prisijungimai). Cowork/debesys to negali.

## 1. Prisijungimas (vieną kartą)
- gh auth status ; jei ne — gh auth login (GitHub.com → HTTPS → patvirtinti naršyklėje).

## 2. Git repo projekte
- cd C:\Users\minda\Projects\word-room
- jei liko: rm -rf .git _git_broken_TODELETE
- git init ; git add -A ; git commit -m "pradinis įkėlimas"

## 3. Repo + push (viena komanda)
- gh repo create word-room --public --source=. --remote=origin --push
- ⚠️ Nemokama Pages veikia TIK viešam repo → naudok --public.

## 4. Įjunk Pages
- gh api -X POST "repos/{owner}/word-room/pages" -f "source[branch]=main" -f "source[path]=/"
- arba web: Settings → Pages → main /(root) → Save.
- Nuoroda: https://<vartotojas>.github.io/word-room/  (po ~1 min).

## 5. Grąžink nuorodą
- Įrašyk į CODE_TO_COWORK.md ir pasakyk savininkui (telefonui).

## Po to
- git add -A ; git commit -m "..." ; git push  (backup po kiekvieno žingsnio).

## Gotcha'os
- Pages 404 iškart → palauk ~1 min. Privatus repo + nemokamas planas → Pages neveiks (daryk viešą).
- gh nerastas → winget install GitHub.cli, arba web UI.
