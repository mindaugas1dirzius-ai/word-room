# Scenos specas — Tema 1 „Namai" · R1 „Svetainė" (Living Room)

> Pirmoji scena = onboarding/tutorial. Turinys-PIRMA: aprašom → generuojam pagal specą (žr. GDD §15). Šis failas — šablonas visoms scenoms.

## 1. Metaduomenys
- **id:** `t1-r1-living-room`
- **theme:** home (Namai) · **round:** 1 iš 5 · **difficulty:** labai lengva (tutorial)
- **title (EN):** Living Room

## 2. Daiktai (žodžiai)
**Privalomi tikslai — 4** (juos radus baigiamas lygis):
| Daiktas | Žodis | Kas tai scenoje |
|---|---|---|
| Žemėlapis | **MAP** (3) | įrėmintas pasaulio žemėlapis ant sienos |
| Lempa | **LAMP** (4) | stalinė lempa ant konsolės |
| Palmė | **PALM** (4) | palmė vazone |
| Stalas | **TABLE** (5) | žemas kavos staliukas |

**Premijiniai daiktai scenoje — 3** (matomi; radus → +monetos, bet NEbūtini; ta pati raidžių aibė):
| Daiktas | Žodis | Kas tai scenoje |
|---|---|---|
| Lėkštė | **PLATE** (5) | dekoratyvinė lėkštė ant lentynos/stalo |
| Kilimėlis | **MAT** (3) | mažas kilimėlis prie durų / po staliuku |
| Sija | **BEAM** (4) | medinė lubų sija |
*(R1 lieka lengvas — reikia tik 4; premijiniai apdovanoja akylumą, scena turtingesnė.)*

## 3. Raidžių rinkinys (ratukas)
**A · B · E · L · M · P · T** (7 raidės).
*(Kilmė: LAMP=L,A,M,P · MAP=M,A,P · PALM=P,A,L,M · TABLE=T,A,B,L,E → sąjunga = A,B,E,L,M,P,T. B ir E ateina iš TABLE.)*

## 4. Premijiniai žodžiai (iš tų pačių raidžių, teigiami)
PALE, PLATE, MAPLE, AMPLE, BEAM, LAMB, ABLE, TAME, MEAL, MEAT, BEAT, LEAP, MALT, PELT, BALE, BLAME, LAME, PEAL, PLEA, TAMP.
*(Rodom ne visus — sprendiklis parenka; radus — +monetos.)*

## 5. Kompozicija (VISI daiktai pilni kadre, su paraštėmis)
Portretas 1080×1920. Šviesi, jauki skandinaviška svetainė, šilta rytinė šviesa.
- **MAP** — ant sienos, viršus-kairė. Centras ~ (300, 600).
- **LAMP** — ant medinės konsolės, vidurys-kairė. Centras ~ (300, 1150).
- **PALM** — vazone, dešinė. Centras ~ (860, 1050).
- **TABLE** — kavos staliukas, apačia-vidurys-kairė. Centras ~ (430, 1500).
- **PLATE** (premijinis) — dekoratyvinė lėkštė ant lentynos, viršus-dešinė. Centras ~ (820, 620).
- **MAT** (premijinis) — kilimėlis ant grindų, apačia-dešinė. Centras ~ (830, 1660).
- **BEAM** (premijinis) — medinė lubų sija skersai, viršus. Centras ~ (540, 250).
- **Rami zona UI (ratukui):** centras-apačia (~ x380–720, y 1550–1900) — palikti tuščią/ramų.
- Be teksto, logotipų, žmonių, vandenženklių.

## 6. Reakcijos (radus daiktą)
- **LAMP** → užsidega (šiltas švytėjimas).
- **MAP** → blyksteli/žybteli.
- **PALM** → švelniai sūpuojasi.
- **TABLE** → lengvas „bounce".
+ kamera prizoomina į daiktą, garsas.

## 7. Sunkumas / onboarding
- Lengviausia: 4 dideli, akivaizdūs daiktai, 7 raidės, **be blaškytojų** (R1).
- **Tutorial (ranka veda):** parodo — rask LAMP → sudėliok L-A-M-P ratuke → kamera prizoomina, lempa užsidega → toliau žaidėjas pats.

## 8. Flux prompt (scenos generavimui) — GALUTINIS
```
A high-end, cozy, and aesthetically stunning modern living room interior, shot as a professional interior design photograph. The composition is clean and carefully framed so all objects are completely within the frame. In the upper-left, a large, detailed vintage-style world map hangs elegantly on a textured beige plaster wall. In the mid-left, a stylish designer table lamp stands on a sleek side cabinet, casting a warm, soft ambient glow. In the bottom-left, a minimalist chic wooden coffee table sits on a plush, cream-colored textured rug. On the right side of the room, a large, lush green potted palm tree in a minimalist ceramic pot adds vibrant life to the space. A decorative ceramic plate rests on a wall shelf in the upper-right, a small woven mat lies on the floor at the lower-right, and a single exposed wooden ceiling beam runs across the top of the room. The lower-center area of the composition is kept calm and uncluttered, showing only the clean textured rug and floor space. To make the room extra beautiful, a soft luxury fabric sofa in a warm taupe color, a few elegant ceramic vases, and large floor-to-ceiling windows with sheer curtains letting in soft morning sunlight are added in the background. Hyper-detailed, 8k resolution, cinematic warm lighting, photorealistic texture.
Negative: cropped objects at edges, text, letters, watermark, people, brand logos, clutter in the lower-center.
```
**Pastaba (svarbu — sunkumo principas):** sofa + vazos = tik FONO grožis (ne ieškomi daiktai; jų negalima sudėlioti iš A,B,E,L,M,P,T).
- Sunkumas ateina NE iš prominentiškumo, o iš to, kaip sunku daiktą PAMATYTI. Tikslų **pavadinimai** turi būti akivaizdūs (matai lempą → „LAMP"), bet patys daiktai gali būti sunkiai randami.
- **R1 = tutorial (lengviausia)** → 4 tikslai matomi lengvai, TYČIA (mokom žaisti). Tai NE bendra taisyklė.
- **Sunkesniuose raunduose (r4–r5):** pavadinimai lieka akivaizdūs, bet daiktai tampa vizualiai subtilūs (mažesni, prieblandoje, prisilieję prie fono) + daugiau blaškytojų — ten sunkumas (§5/§6).

Vėliau — fiksuota stiliaus nuoroda visoms scenoms (vientisumas).

## 9. Lygio JSON (struktūra, ką generuosim)
```json
{
  "id": "t1-r1-living-room",
  "theme": "home",
  "round": 1,
  "difficulty": "easy",
  "background": "scenes/t1-r1-living-room.webp",
  "letters": ["A","B","E","L","M","P","T"],
  "objects": [
    { "word": "MAP",   "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "glint" },
    { "word": "LAMP",  "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "lightUp" },
    { "word": "PALM",  "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "sway" },
    { "word": "TABLE", "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "bounce" }
  ],
  "bonusObjects": [
    { "word": "PLATE", "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "shine" },
    { "word": "MAT",   "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "ripple" },
    { "word": "BEAM",  "box": [x,y,w,h], "zoom": [x,y,w,h], "reaction": "dust" }
  ],
  "bonus": ["PALE","MAPLE","AMPLE","LAMB","ABLE","TAME","MEAL","LEAP"]
}
```
*(box/zoom koordinatės užsipildo po generavimo — iš mūsų layout'o arba SAM auto-segmentacijos.)*
