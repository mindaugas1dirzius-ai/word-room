---
name: cowork-code-pastas
description: >-
  Cowork↔Code bendravimo per failus metodika (paštas COWORK_TO_CODE.md /
  CODE_TO_COWORK.md). Aktyvuoti, kai dirbama projekte, kuriame yra šie failai
  arba CLAUDE.md su „Cowork ↔ Code" skyriumi; arba kai vartotojas sako
  „perduok code", „parašyk code", „bendravimas laiškais su code", „cowork/code
  paštas", „kas naujo iš code", arba kai reikia perduoti užduotį ar statusą tarp
  planuotojo (Cowork) ir koduotojo (Claude Code).
---

# Cowork ↔ Code — bendravimas per failus (metodika)

Dvi Claude pusės dirba tame pačiame git repo ir bendrauja PER FAILUS:
Cowork (planuoja/dizainuoja) ↔ Claude Code (koduoja/stato — savininko kompe). Dvi SKIRTINGOS aplinkos; bendras tik repo.

## Kas yra kas
- Cowork = planuoja, dizainuoja, vadovauja. RAŠO į COWORK_TO_CODE.md.
- Claude Code = koduoja, git, build, deploy. RAŠO į CODE_TO_COWORK.md.

## Paštai (griežta taisyklė)
- COWORK_TO_CODE.md — rašo TIK Cowork; Code skaito.
- CODE_TO_COWORK.md — rašo TIK Code; Cowork skaito.
- NIEKADA nerašyk į kito failą. Naujausia VIRŠUJE. Formatas: `## data — tema`.

## Protokolas (kaip Cowork)
1. Prieš darbą: perskaityk CODE_TO_COWORK.md (statusai/klausimai/nuorodos) + būklės failą.
2. Užduotį Code'ui: NAUJAS `## data — tema` įrašas VIRŠUJE COWORK_TO_CODE.md — KĄ + KODĖL.
3. Po pakeitimų — commit + push (debesų Cowork'e git gali neveikti → tvarko Code/savininkas).
4. Nedubliuok; viena tiesa vienoje vietoje.

## Vaidmens ribos
- Cowork NEDARO galutinio git/GitHub/deploy iš debesų — tai Code darbas. Cowork planuoja ir rašo užduotis per COWORK_TO_CODE.md; rezultatus/nuorodas skaito iš CODE_TO_COWORK.md.

Pilni principai — DARBO_PRINCIPAI.md.
