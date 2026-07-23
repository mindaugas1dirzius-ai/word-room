# Spellnook — pilnas žaidimo dizaino dokumentas (GDD)

> Pavadinimas: **Spellnook** (buvęs darbinis „Word Room"). Patvirtinta 2026-07-23.

> **Vienas tiesos šaltinis.** Prieštarauja kitiems dokams → galioja ŠIS. Naujausi sprendimai apačioje „Sprendimų žurnale".
> Statusas: v2 juodraštis (perimta iš pavyzdžių analizės, 2026-07-23). Skaičiai = v1, derinami testu.

---

## 1. Vizija ir kabliukas

Fotorealistiškas mobilus **žodžių + paslėptų-objektų** žaidimas. Žaidėjas mato tikrovišką, **įdomią, ryškią, gražią sceną** — tai gali būti kambarys, **zoologijos sodas, Paryžiaus panorama, turgus, uostas — bet kokia netriviali vieta** — ir joje **randa daiktus** bei iš raidžių ratuko **sudėlioja jų pavadinimus**. Radus — kamera prizoomina, daiktas sureaguoja (lempa užsidega, gyvūnas krusteli), garsai. **Scenos niekada nuobodžios — turtingos daiktais, ne „du objektai".**

**Mūsų unikalus kabliukas:** kituose žanro žaidimuose (Words of Wonders, Zen Word) fonas — tik dekoracija. **Pas mus fonas YRA dėlionė.** Tai skiria mus rinkoje. Su konkurentais nekonkuruojam turinio kiekiu — laimim nauju mechaniku.

**Tikslas:** paleisti app store'uose, uždirbti (reklamos + pirkimai).

**Pamatiniai ramsčiai (nepamiršti):** sauga · motyvacija (žaidėją grąžinti) · gera monetizacija · optimalus dizainas · **kad NEstriktų** · **tiktų VISOMS platformoms** ateityje. Principas: **statom teisingai iš karto — neperdarinėjam.** Pilna kontrolė ir matomumas (klaidos, elgesys) nuo pirmos dienos.

---

## 1b. Kuo skiriamės — konkurencinė analizė + unikalūs elementai

**Rinkos spraga (2026-07-23 tyrimas):** tikslaus mūsų hibrido NĖRA. Gretimi žanrai (visi populiarūs) praleidžia po dalį:
- **Paslėptų objektų** (Find It, Where Is?, June's Journey) — duoda daiktų sąrašą, tik baksteli; **nėra dėliojimo** (pasyvu).
- **Žodžiai + fonas** (Wordscapes, Words of Wonders) — dėlioji raides, bet **fonas tik dekoracija**.
- **Nuotrauka → žodis** (4 Pics 1 Word, Pictoword) — statiška, vienas žodis, **jokio scenos tyrinėjimo**.

Mūsų derinys (tyrinėk sceną → rask kelis daiktus → sudėliok → kamera reaguoja → kelionė po pasaulį) — **niekas nedaro**. Įrodyta rinka, naujas kabliukas.

**Unikalūs elementai (PATVIRTINTA — statom):**
1. **„Nook" kolekcija (signature meta):** keliaudamas renki rastus daiktus/žodžius kaip **suvenyrus** į savo asmeninį jaukų „Nook" (lentyną/kambarį, kurį puoši). Personalizacija + kolekcija + retencija; tinka pavadinimui (Spellnook = tavo žodžių kertelė). → siejasi su §7 profiliu/meta.
2. **Didinamojo stiklo mechanika (signature, iš logotipo):** tempi stiklą po sceną — po lęšiu ryškėja smulkios detalės/raidės. Taktilu, unikalu; niekas žodžių žaidimuose to neturi. → siejasi su §8 pagalbomis (skiriasi nuo ZOOM).
3. **Gyva scena:** radus daiktus scena **atgyja/transformuojasi** (tuščia→jauki, diena→vakaras), pabaigoje „aha" momentas — vizualus atlygis, kurio word žaidimai neturi.
4. **Dvigubas iššūkis:** rask akimis + sudėliok — įveikia ir pasyvius hidden-object, ir bekontekstius word žaidimus.
5. **Foto-realizmas:** premium vizualas išsiskiria iš flat/cartoon konkurentų.

---

## 2. Pagrindinė kilpa (sekundė po sekundės)

1. Žaidėjas mato kambarį (foną) su keliais paslėptais daiktais.
2. Ratuke — raidės (bendras visų daiktų pavadinimų rinkinys).
3. Braukia per raides → viršuje formuojasi žodis; langeliai rodo, kiek daiktų ir kokio ilgio pavadinimai.
4. **Teisingas daikto pavadinimas** → kamera prizoomina į daiktą, daiktas sureaguoja + garsas, **+monetos**.
5. **Premijinis žodis** (kitas tikras žodis iš tų pačių raidžių) → **+monetos**, niekada nebaudžia.
6. Radus visus daiktus → **Level Complete** ekranas (progresas + monetų dovana + „Next Room").
7. Įstrigus → pagalbos (LETTER / ZOOM / Shuffle) už monetas.

---

## 3. Ekranai ir srautas

> **Meniu filosofija: MINIMALISTIŠKA.** Tik tiek, kiek būtina — neapkrauti nei žaidėjo, nei savęs. Pagrindinis „meniu" = kelionės žemėlapis su „Continue". Jokių perteklinių skirtukų/langų.

- **Intro (pirmą kartą):** trumpas (~5–10 s) animuotas pristatymas — išeini iš namų → atsiveria pasaulis/gaublys → pavadinimas. Perteikia esmę: „palik namus, apkeliauk pasaulį". Praleidžiamas. Pigus (keli animuoti sluoksniai, ne brangus video).
- **Loading / splash** — logotipas, cloud-save indikatorius.
- **Kelionės žemėlapis = PAGRINDINIS ekranas** — vietovės kaip taškai (aplankytos spalvotos, užrakintos pilkos); tavo „You" avataras ties dabartine vieta; didelis „Continue" mygtukas. Viršuje: monetos, ⚙️ nustatymai, 🎁 dienos dovana. Tai ir yra „home" — jokio atskiro apkrauto meniu.
- **Vietovės vaizdas** — kambariai/scenos toje vietovėje (progreso juosta).
- **Žaidimo ekranas** — kambarys + ratukas + langeliai + minimalus HUD.
- **Level Complete** — progresas (pvz. 3/5), monetų dovana, „Next Room".
- **Profilis („tavo info")** — avataras, aplankytos vietos/šalys, įveikti lygiai, serija, pasiekimai („kur jau buvai").
- **Parduotuvė** — monetų paketai, Remove Ads, bundle'iai, VIP.
- **Nustatymai** — garsas, kalba, privatumas, restore purchases.
- **Retencijos iššokimai** — welcome-back, dienos dovanos.

---

## 4. Scenos dizainas — SLUOKSNIŲ sistema (mūsų gamybos pamatas)

> **„Kambarys" = bet kokia įdomi SCENA** (interjeras, zoologijos sodas, miesto panorama, turgus, uostas…). Kokybės kartelė: **ryšku, gražu, turtinga daiktais, niekada „du objektai".** Plačiose/panoraminėse scenose daiktai natūraliai telpa pilni; ankštose — dedam sluoksniais (žr. žemiau).

**Sprendimas:** scena NĖRA (vien) viena AI nuotrauka. Kambarys = **fonas + atskiri daiktų sluoksniai (sprite'ai)**.

**Kodėl:**
- **Niekada nenukerpa** daiktų (dedam pilnus PNG) — tai buvo pagrindinė „vienos nuotraukos" problema.
- **Tiek daiktų, kiek reikia** — nenuobodu; sunkumą valdom kiekiu/dydžiu/paslėpimu.
- **Hitbox'ai DYKAI** — patys dedam daiktą → iškart žinom jo vietą (dingsta lėčiausia grandis — anotavimas).
- **Reakcijos lengvos** — daiktas atskiras sluoksnis → „uždegti/supti/blykstelėti" trivialu.

**Struktūra:**
1. **Daiktų biblioteka** — pilni PNG su permatomu fonu (sofa, lempa, augalas, laikrodis…). Daromi VIENĄ kartą, naudojami DAUG kartų.
2. **Fonų rinkinys** — kambarių tipai (svetainė, virtuvė, miegamasis…).
3. **Scenos dėliotojas** — uždeda daiktus į foną žinomose vietose → automatiškai JSON su hitbox'ais.

**Galimas hibridas:** foto-realistiškas AI fonas (nuotaikai) + ieškomi daiktai kaip pilni sluoksniai ant viršaus.

### Kompozicijos taisyklės (PRIVALOMA)
- Visi ieškomi daiktai — PILNI, su paraštėmis, niekur nenukirpti.
- Portretas 1080×1920. Šviesus, jaukus, fotorealistiškas.
- Rami zona centre/apačioje UI (ratukui, langeliams).
- Be teksto, vandenženklių, logotipų, žmonių (komercinė sauga).
- Daiktų pavadinimai — akivaizdūs (žr. §5).

---

## 5. Žodžių ir raidžių dizainas — sąžininga (be „apgaulės")

- Daiktų pavadinimai — AKIVAIZDŪS matomam daiktui (LAMP, MAP, PALM, TABLE). Jokių sinonimų spąstų (matai palmę → „PALM" įskaito; ne „PLANT" reikalauja).
- Sunkumas ateina iš: daugiau daiktų, smulkesni/subtilesni, be žymeklių.
- **Premijiniai žodžiai** (kiti tikri žodžiai iš to paties rinkinio) — VISADA teigiami: +monetos, niekada nebaudžia.
- Vienas raidžių rinkinys → keli daiktų žodžiai + premijiniai (pvz. A,B,E,L,M,P,T → LAMP, MAP, PALM, TABLE + PALE, PLATE, MAPLE, BEAM…).
- **Iš anksto atskleista raidė** (kaip Zen Word mėlynos raidės) — leidžiama kaip švelnus startas lengviems lygiams.
- Ratukas — **permatomas**, raidės su stipriu šešėliu (įskaitoma ant nuotraukos).

### „Žodžių sprendiklis" (automatika)
Skriptas: paima temos daiktų-žodžių banką → randa poaibius, kurie dalinasi kompaktišką raidžių rinkinį → iš žodyno išveda visus premijinius. „Sugalvoti gerą dėlionę" tampa paieška, ne rankų darbu. Galima automatiškai pagaminti šimtus tinkamų dėlionių ir atsirinkti.

---

## 6. Sunkumas ir daiktų kiekis

- **Lengva:** 3–4 daiktai, TRUMPI žodžiai (3–5 raidės), 6–7 raidės ratuke. (galimas iš anksto atskleistas 1 raidė)
- **Vidutinė:** 5–6 daiktai, vidutiniai žodžiai (5–6 raidės), 7–8 raidės ratuke.
- **Sunku:** 7–8 daiktai (dalis smulkių/prieblandoje), ILGI/retesni žodžiai (6–9 raidės), „prikimšta" scena, 8–9 raidės ratuke.
- **Žodžių ILGIS = stiprus sunkumo svertas:** KIEKVIENOJE temoje r1 — trumpi akivaizdūs (3–5 raidės), r5 — ilgi/retesni (6–9 raidės, pvz. CROISSANT, CATHEDRAL, FOUNTAIN), daugiau objektų, didesnis ratukas. **Temai pasikeitus — VĖL nuo trumpų** (sunkumas resetinasi kiekvienoje temoje).
- Premijiniai visur: 3–8 per sceną.
- Sunkumas auga tolygiai per kelionę (§7), be staigių šuolių.
- **Daugiau daiktų nei užduotyje (blaškytojai):** sunkesniuose lygiuose scenoje yra DAUGIAU objektų, nei reikia rasti — kad nebūtų per paprasta (reikia akimis atsirinkti). Sąžininga: langeliai rodo, kiek/kokių žodžių ieškoti; jei blaškytojo pavadinimą pavyksta sudėlioti — jis tampa **premijiniu** žodžiu (teigiama), niekada nebauda.

---

## 7. Kelionės meta-struktūra (SPRENDIMAS: kelionė)

Kambariai sujungti į **kelionę**: namas → gatvė/kaimynystė → miestas → pasaulis.

- **Skyrius = vietovė** su N kambarių/scenų (pvz. „Tavo namai": svetainė, virtuvė, miegamasis, vonia, biuras, vaikų, garažas, palėpė).
- Baigus vietovę → atsirakina kita (kito namo, kavinės, viešbučio, tada užsienio miestų interjerai — kaip WOW pasaulio kelionė).
- **Kelionės žemėlapis** rodo progresą, atrakinimus, kur esi.
- Duoda: temą, natūralią sunkumo kreivę, geriausią retenciją.
- **MVP:** startuojam kaip paprastą lygių sąrašą; kelionės žemėlapį uždedam ant viršaus antru etapu (tie patys lygiai, gražesnė „obertka").

### Raundų struktūra (sunkumo kreivė)
- Kelionė iki vietovės (pirmo tikslo) = **~5 raundai (lygiai).**
- Raundų sunkumas AUGA: **1 raundas — lengviausias … 5 raundas — sunkiausias.**
- Įveikus 5 raundus → **pasieki vietovę (tikslą)** — matosi profilyje/žemėlapyje kaip „parėjai".
- Tada prasideda **kita kelionė** — vėl 5 raundai tuo pačiu principu (lengva → sunku), nauja vietovė.
- **Sunkumas RESETINASI kiekvienoje temoje:** naujos temos r1 vėl lengvas (NE tęsia nuo praeitos temos r5). Kreivė — „dantyta" (sawtooth): kyla temoje, krinta naujai temai. Todėl temų TVARKA — labiau naratyvas/įvairovė, ne raw sunkumas. (Opcija vėliau: labai lengvas globalus kilimas.)
- Progreso juosta „1/5" (kaip Zen Word). Turinys: 1 vietovė = ~5 scenos → 100 scenų ≈ 20 vietovių.
- **Kiekviena vietovė turi TEMĄ:** visos 5 scenos susijusios **tema** (ne vizualiai vienodos). Pvz. „Paryžius": Eifelio zona, Paryžiaus kavinė, Luvras, gatvės turgus, Senos panorama. **Bendra visos kelionės tema — kelionė po pasaulį.**

### Istorija (naratyvas)
Prielaida: **išeini iš namų ir leidiesi apkeliauti pasaulį.** Kiekvienas įveiktas kambarys/scena = aplankyta vieta, žingsnis kelionėje. Įveikta vietovė = pasiektas tikslas (miestas, įžymybė). Naratyvas **lengvas, ne sunkus** — sakinys vienai vietovei + progreso pojūtis. Duoda emocinę giją ir priežastį tęsti.

### Profilis („tavo info")
Rodo, **ką jau „parėjai":** aplankytos vietos žemėlapyje (spalvotos vs pilkos), įveiktų lygių skaičius, serija, pasiekimai, monetos. Kiekvienas įveiktas lygis matosi kaip pasiektas tikslas.

---

## 8. Pagalbos

| Pagalba | Ką daro | Kaina (v1) |
|---|---|---|
| **LETTER** 💡 | Atskleidžia atsitiktinę raidę iš dar neatspėtų žodžių; atskleidus visas → daiktas auto-užskaitomas | −20 |
| **ZOOM** 🔍 | Trumpam parodo vis kitą paslėptą daiktą (NEišsprendžia) | −50 |
| **Shuffle** 🔀 | Sumaišo raides ratuke | Nemokama |
| **Pre-reveal** (opcija) | Pirma raidė duota starte (lengvi lygiai) | Nemokama/lengviems |

Vėliau galima „reveal object" (kaip plaktukas WOW) — atviras klausimas.

---

## 9. Ekonomika (viena valiuta: MONETOS)

**Tikslas:** žaidėjas monetų uždirba, bet jos ribotos → nekantriems patogiau PIRKTI / žiūrėti reklamą. BET niekada nefrustruoja (visada yra nemokama alternatyva; progresas neblokuojamas). Modelis pagal Words of Wonders (§9.4).

### 9.1. Psichologijos principai
- **Sąžininga riba:** monetos perka tik pagalbas/patogumą, NIEKADA progresą. Įveikti visada gali mąstydamas.
- **Dosnu pradžioje** (hook), **griežčiau vėliau** (pressure).
- **Premijinių žodžių kilpa:** rasti extra žodžius duoda monetų → pats finansuoji pagalbas → įsitraukimas (pagrindinis „faucet" žaidžiant).
- **Visada NEMOKAMA alternatyva** (rewarded reklama, dienos dovana) PRIEŠ paywall → pirkimas = nekantrumui, ne būtinybei.
- **„Beveik užtenka"** pojūtis — laikom žaidėją prie ribos.
- **Level-complete visada duoda monetų pliūpsnį** (dopaminas), net jei pagalbos „suvalgė".
- **Viskas per remote config** → balansuojam GYVAI pagal analitiką.

### 9.2. Uždarbis (faucets, v1 — tyčia SAIKINGA)
| Šaltinis | Monetos |
|---|---|
| Rastas užduoties daiktas | +5 |
| Premijinis (extra) žodis | +2 |
| Raundo pabaiga | +10 (r.1) … +20 (r.5) |
| Vietovės (5 raundų) pabaiga — chest | +60 |
| Dienos dovana (login kalendorius) | d1 50 … d7 300 |
| Serija (streak) | mažas priedas kasdien |
| Rewarded reklama (iki ~5/dieną) | +30 |
| Pasiekimai (pvz. 10 lygių be pagalbų) | +100 (vienkartinis) |
| Startas (onboarding) | ~150 banke; pirmos pagalbos pigios/nemokamos |

### 9.3. Išlaidos (sinks, v1)
| Pagalba | Kaina |
|---|---|
| LETTER (atskleisk raidę) | −25 |
| ZOOM (parodyk daiktą) | −60 |
| „Reveal object" (opcija, didelė) | −120 |
| Shuffle | 0 |

### 9.4. Žanro principai — pritaikyti SAVAIP (NE kopija)
Imam tik įrodytus žanro dėsnius, bet žaidimas — MŪSŲ (paslėptų-objektų kabliukas, savas menas/UI, sava kelionė, BE sukamo rato ir kitų „nurašytų" elementų).
- Premijinių žodžių → monetų kilpa (pagrindinis įsitraukimo variklis).
- Riboti faucet'ai (login kalendorius, pasiekimai, rewarded reklamos, chest'ai) subalansuoti prieš pagalbų kainas.
- „Gali žaisti nemokamai" filosofija → aukšti reitingai; pirkiniai neprivalomi, bet nekantriems patogiau.
- Dosnu pradžioje, griežčiau toliau.
- **Sukamo rato ATSISAKOM** — kad žaidimo nevadintų kopija.

### 9.5. Balanso taikinys
- Vidutinis žaidėjas (saikingai naudoja pagalbas) kas kelias sesijas nusileidžia žemai → stumteklis: rewarded reklama arba pirkinys.
- Įgudęs (retai naudoja pagalbas) — kaupia (įgūdžio kelias yra, sąžininga).
- Grynasis srautas ilgainiui šiek tiek neigiamas naudojantiems pagalbas → pirkimo spaudimas, be blokavimo.

### 9.6. Per-raundo skaičiavimas (santykis MŪSŲ pusėje)
Skaičiai sudėti taip, kad uždarbis būtų LĖTAS, o pagalbos — brangios; tad sunkūs raundai neša neigiamą balansą.

| Raundas | Max uždarbis (be pagalbų) | Tipinis uždarbis | Tipinės pagalbos | Neto |
|---|---|---|---|---|
| r1 lengvas | ~40 | ~34 | 0 | **+34** |
| r3 vidutinis | ~60 | ~50 | −25 (1 LETTER) | **+25** |
| r5 sunkus | ~80 | ~66 | −110 (1 ZOOM+2 LETTER) | **−44** |

- Kelionė (5 raundai): tipinis neto **+30…+110** jei mažai pagalbų; **neigiamas**, jei naudoja daug (sunkūs r4–r5 „suvalgo").
- **Kur slypi pinigai:** sunkūs raundai (daug daiktų + blaškytojai, be laikmačio) → žmogus stringa/nekantrauja → naudoja pagalbas → monetos senka greičiau nei uždirba.
- **SVARBI TIESA (sąžiningai):** priversti VISUS nueiti į nulį neįmanoma nefrustruojant. Įgudęs žaidėjas, retai naudojantis pagalbas, išsilaikys — ir tai GERAI (jis palieka gerus atsiliepimus, pritraukia kitus nemokamai). Taikinys: **vidutinis / nekantrus / įstrigęs** žaidėjas trendina į nulį → reklama/pirkinys.
- **Kalibruojam per remote config + analitiką** iki taikinio metrikos (pvz. „X% žaidėjų per savaitę pasiekia žemą monetų būseną ir konvertuoja"). Pradiniai skaičiai — startas, ne tiesa.

**Techninis:** **server-authoritative** (monetos/atrakinimai serveryje) — kai bus serveris; MVP be jo. **Visi skaičiai = v1**, derinami testu + remote config gyvai. (Startas prototipe įkalta 240 — TEST reikšmė, keisim į ~200.)

---

## 10. Retencija

- **Dienos serija (streak)** 🔥 — grįžk kasdien, augantis atlygis.
- **Welcome-back dovanos** — po pertraukos: monetos, pagalbos, „1h be reklamų".
- **Level Complete progresas** — „3/5", vizualus judėjimas pirmyn.
- **Cloud save** (Google Play Games / Game Center) — progresas neprapuola.
- (Vėliau) dienos dėlionė, pasiekimai, kolekcijos.

---

## 11. Monetizacija

**Ekonomikos įtampa (esmė):** monetos — ribotas resursas. Žaidėjas jų uždirba, bet jos „baigiasi": pagalbos kainuoja tiek, kad įstrigus dažnai pritrūksta → norint tęsti/gauti daugiau: **perki, žiūri rewarded reklamą arba suki ratą**. Tai pagrindinis pajamų variklis.

**Sąžiningumo riba (NELIESTI):** monetos gatė tik **PAGALBAS ir patogumą**, NIEKADA patį progresą. Įveikti lygį visada įmanoma vien žiūrint ir mąstant (šerdis = įgūdis, ne pinigai). Jokio pay-to-win / pay-to-pass. Atitinka mūsų „sąžininga, be apgaulės" principą ir saugu app store'uose.

**Reklamos:**
- **Rewarded video** — žiūrėk → monetos/pagalba (pagrindinis nemokamų pajamų šaltinis; žaidėjui naudinga).
- **Interstitial** — tarp lygių, saikingai.
- **Banner** — apačioje (išjungiamas per Remove Ads).

**Pirkimai (IAP) — v1 kainos pagal rinką (derinsim):**
- **Remove Ads** — ~0.99–5.99 € (pvz. „Forever + 300 monetų").
- **Monetų paketai** — pvz. ×300 (3.29 €), ×800 (5.99 €), ×2050 (10.99 €), ×5000 (21.99 €), ×13500 (54.99 €).
- **Value bundle'iai** — Super/Mega (monetos + pagalbos, „+150% More").
- **VIP** — be reklamų + bonusai.

---

## 12. Vizualas ir garsai

- **Stilius:** fotorealistiškas jaukus interjeras; švarus, minimalistinis UI (Zen Word kryptis).
- **Ratukas ir langeliai:** permatomi, susilieja su nuotrauka; raidės su šešėliu.
- **HUD:** frosted-glass (Level/vietovė, monetos, nustatymai).
- **Langeliai:** matai ilgius; atskleistos raidės — auksinės.
- **Garsai** (WebAudio, be failų MVP; vėliau tikri SFX): raidžių jungimas, teisingas/klaidingas, premija, maišymas, laimėjimas. Įsijungia po pirmo palietimo.
- **Tekstai — angliškai** (produktas globaliai).

---

## 13. Onboarding

- Pirmas lygis — vedamas: „rask lempą", parodyk kaip braukti raides, kaip veikia zoom/reakcija.
- Be teksto sienų; mokoma darant.

---

## 14. Techninė architektūra

- **Duomenimis valdomas variklis:** žaidimas krauna lygius iš JSON sąrašo, NE įkaltus kode. 1 ar 100 lygių = tas pats kodas. (Dabar 1 lygis įkaltas `index.html` — perdaryti.)
- **Lygio (scenos) JSON schema (stuburas):** `id, theme, difficulty, background, letters[], objects[{word, box[x,y,w,h], zoom[], reaction}], bonus[]`.
- **Temos/nuotykio manifestas:** `{id, title, location, order, scenes:[…]}`. Kelionė = temų registras → žemėlapis, atrakinimai, progresas generuojami AUTOMATIŠKAI.
- **Turinys = ĮSKIEPIS (plug-in), NULIS kodo keitimų:** tema/nuotykis = duomenų paketas (manifestas + ~5 scenų JSON + vaizdai). **Prijungei naują temą → ji IŠ KARTO tampa žaidimo dalimi** (atsiranda žemėlapyje, atsirakina eilėje, žaidžiama) — jokio kodo, jokio perkompiliavimo. Visa mechanika (radimas, ratukas, ekonomika, pagalbos, reakcijos) — universali, veikia bet kuriai temai. Tai privaloma nuo pirmos kodo eilutės.
- **Sprite biblioteka** — daiktų PNG + metaduomenys, daugkartiniai.
- **Pakavimas:** HTML5 + **Capacitor** → Android (.aab/.apk) + iOS (per Xcode/Mac).
- **Variklio kryptis (svarstoma):** likti web (HTML5/Phaser) → Capacitor, ar Godot/Unity native. MVP — web.
- **Server-authoritative ekonomika** — kai bus serveris.

---

## 14b. Kokybės, stebėjimo ir kontrolės pamatas (statom TEISINGAI iš karto)

Tikslas: tokia bazė, kad paskui NEREIKTŲ perdaryti. Pilnas matomumas ir kontrolė nuo 1 dienos.

- **Cross-platform pamatas:** HTML5 + Capacitor → tas pats kodas Amazon (Fire), Samsung, Xiaomi, Huawei, Apple, Google. Jokių vienai platformai pririštų sprendimų.
- **TV valdymas (Amazon Fire TV):** TV neturi lietimo — navigacija pultu (D-pad/žymeklis). Įvestį projektuojam **abstrahuotai** nuo pradžios (lietimas IR pultas), kad TV nereiktų perrašinėti. ⚠️ Sprendimas §21: TV pilnai nuo starto, ar planšetės pirma + TV iškart po to.
- **Našumas (kad NEstriktų):** lengvi/suspausti vaizdai, optimizuotas piešimas; veikia ir ant silpnų Fire planšečių. Testuojam ant tikro low-end įrenginio.
- **Stebėjimas (matyti VISKĄ):** nuo 1 dienos — **analitika** (kur stringa, kur meta žaisti) + **crash/error reporting** (klaidos realiu laiku). Pvz. Firebase Analytics + Crashlytics ar analogas.
- **Nuotolinis derinimas (remote config):** ekonomikos skaičius, sunkumą, reklamų dažnį keičiam **be naujo build'o** — reguliuojam gyvai pagal duomenis.
- **Atnaujinamumas:** lygiai — duomenimis (JSON) → naujus lygius/pataisas tiekiam be pilno resubmit (kur platforma leidžia).
- **Sauga:** IAP kvitų validacija; ekonomika **server-authoritative** (kai bus serveris) — netikrinam tik kliente; privatumas (GDPR; jei visiems amžiams — vaikų reklamų/COPPA taisyklės).

---

## 15. Turinio konvejeris (kaip gaminti 100 kambarių GREITAI)

Bazė, atidirbama VIENĄ kartą → paskui kambarys per minutes:
1. **Lygio JSON formatas** (susitart) → turinys atsietas nuo kodo.
2. **Variklis iš duomenų** (Code).
3. **Vaizdų šablonas + temų×sunkumo lentelė** (~25 temos × variantai = 100).
4. **Daiktų biblioteka + fonai** (sprite'ai, daugkartiniai).
5. **Žodžių sprendiklis + temų žodžių bankai** (auto dėlionės).
6. **Anotavimas:** v1 rankinis įrankis (~3–5 min/kambarys) → v2 auto (SAM + atpažinimas, sekundės).

Po to procesas: tema+sunkumas → sprendiklis duoda žodžius → dėliotojas sudeda sceną → JSON → į lygių aplanką → veikia. Kambarys #10 ir #100 kainuoja vienodai mažai.

**Įrankiai:** Canva (kokybė patvirtinta) startui; Flux (kontrolė/vientisumas) ir Firefly (komercinė sauga) — vėliau, jei reikės. Stock (Pexels/Adobe Stock) kaip bazė + adaptacija.

---

## 16. App store paleidimo tvarka

1. **Amazon** (Fire tablets + Fire TV, Appstore) →
2. **Samsung** (Galaxy Store) / **Xiaomi** (GetApps) / **Huawei** (AppGallery) →
3. **Apple** (App Store) →
4. **Google Play**.

**Pradžia:** Amazon **Live App Testing** (beta) ant Fire planšečių + Fire TV → patikra → viešas Amazon → toliau kitos platformos.

Reikės: developer paskyrų, ikonos, screenshot'ų, privatumo politikos, pilno žaidimo (daug lygių).

---

## 17. MVP apibrėžimas — PILNA sistema, MAŽAI lygių

**Principas:** mažai lygių, bet **PILNAI veikianti sistema.** Ne tik žaidimo šerdis — ir monetizacija, stebėjimas, cross-platform bazė, kad paskui NEREIKTŲ perdaryti. Įkeliam į **Amazon test track (Live App Testing)** → patikrinam ant tikrų Fire įrenginių (planšetė + TV) → jei viskas veikia, **dakuriam lygius** → tik tada viešas paleidimas.

**MVP (v1) turi turėti:**
- Šerdis (radimas + žodžiai + zoom/reakcija). ✅ dalinai yra.
- Sluoksnių kambariai + JSON variklis (perdaryti iš įkalto).
- ~5–10 kambarių (mažai, bet PILNAS srautas: intro → žemėlapis → žaidimas → level complete → parduotuvė).
- Bazinė ekonomika (monetos, LETTER/ZOOM/Shuffle) + monetizacijos karkasas (reklamos + IAP prijungti).
- **Analitika + crash reporting + remote config** nuo starto.
- **Cross-platform bazė** (Capacitor) + įvesties abstrakcija (lietimas + TV pultas).
- Garsai, onboarding, minimalistinis meniu.

**Vėliau (po test track patikros):**
- Daug lygių, kelionės žemėlapis pilnai, streak/welcome-back/ratas, cloud save.
- Server-authoritative, auto-anotavimas, kitos platformos (Samsung/Xiaomi/Huawei/Apple/Google).

---

## 18. Roadmap

1. **Dabar:** dizainas + bazė (JSON formatas, variklis iš duomenų, sluoksnių sistema).
2. Turinys (kambariai per konvejerį) + sunkumo kreivė.
3. Ekonomikos balansas.
4. Kelionės meta + retencija.
5. Monetizacija.
6. Capacitor buildai → app store'ai (§16).

---

## 19. Vaidmenys ir darbas

- **Cowork** = vadovas/planuotojas/dizaineris (šis dokas, užduotys Code'ui, dizainas, vaizdai).
- **Code** = koduotojas kompe (git, build, deploy, variklis, įrankiai).
- Bendravimas per failus: `COWORK_TO_CODE.md` / `CODE_TO_COWORK.md` (naujausia viršuje). Paštas: dirbant ~5 min, laukiant ~1 min.
- GitHub/hostingas — TIK per Code.

---

## 20. Sprendimų žurnalas

- **2026-07-23** Kryptis: 2.5D/sluoksniai (NE viena AI nuotrauka; NE realaus laiko 3D). *Kodėl: „viena nuotrauka" nukerpa daiktus; sluoksniai duoda pilnus daiktus + hitbox'us + reakcijas.*
- **2026-07-23** Meta-struktūra: **kelionė** (namas → miestas → pasaulis). *Geriausia retencija; MVP — paprastas sąrašas, žemėlapis ant viršaus vėliau.*
- **2026-07-23** Valiuta: **viena — monetos**.
- **2026-07-23** Vaizdai: Canva pakanka startui; komercinė sauga per modifikuotą sceną; „geriau" (Flux/Firefly) tik esant poreikiui.
- **2026-07-23** Naratyvas: kelionė turi istoriją — „palik namus, apkeliauk pasaulį"; profilis rodo aplankytas vietas / pasiektus tikslus.
- **2026-07-23** Monetizacija: monetos ribotos (įtampa) → tęsi perki/reklama/ratas; BET gatė tik pagalbas/patogumą, ne progresą (sąžininga).
- **2026-07-23** Intro: trumpas animuotas pristatymas (išeini iš namų → pasaulis). Meniu — minimalistinis (žemėlapis = home).
- **2026-07-23** Pamatas: statom teisingai iš karto (cross-platform, analitika+crash, remote config, sauga, našumas) — neperdarinėjam. MVP = pilna sistema + mažai lygių → Amazon test track → patikra → dakuriam lygius → viešas.
- **2026-07-23** Struktūra: kelionė = ~5 raundai (1 lengviausias → 5 sunkiausias) → vietovė/tikslas → kita kelionė tuo pačiu principu. Sunkiuose lygiuose daugiau daiktų nei užduotyje (blaškytojai), sąžininga.
- **2026-07-23** Scenos: platesnės nei kambariai (zoologijos sodas, panorama, turgus…), ryškios/turtingos, niekada „2 objektai". 5 vietovės scenos susietos TEMA (ne vizualiai); bendra tema — kelionė po pasaulį.
- **2026-07-23** Architektūra: turinys = plug-in. Tema/nuotykis = duomenų paketas; prijungus naują temą ji AUTOMATIŠKAI tampa žaidimo dalimi (žemėlapis/atrakinimai/žaidimas) be jokio kodo keitimo. Mechanika universali. Privaloma nuo starto.
- **2026-07-23** Ekonomika: detalus v1 (§9 earn/spend lentelės, psichologija). Esmė: monetos ribotos → pirkimo/reklamos spaudimas, bet visada nemokama alternatyva + progresas neblokuojamas (nefrustruoja). Balansas per remote config gyvai.
- **2026-07-23** Ekonomika v2: atsisakyta sukamo rato (kad nevadintų kopija); uždarbis sumažintas (saikingas), pagalbos pabrangintos; §9.6 per-raundo skaičiavimas — santykis mūsų pusėje (sunkūs raundai neša neigiamą balansą). Sąžininga tiesa: taikinys = vidutinis/nekantrus žaidėjas, įgudę išsilaiko (geri reitingai). Kalibruojam per remote config/analitiką.
- **2026-07-23** Sunkumas: kyla VIDUJE temos (r1→r5), naujai temai RESETINASI (dantyta kreivė) — kad po 10 temų nereiktų 20-raidžių žodžių. Žodžių ilgis — svertas.
- **2026-07-23** Turinys PATVIRTINTA: pirmi 3 temai (Namai, Miestas, Paryžius), po 5 scenas = ~15 scenų MVP (§22).
- **2026-07-23** Pavadinimas PATVIRTINTA: **Spellnook** (spell + nook; patikrinta — nėra tokio žaidimo/įmonės/TM). Domeną pirkti artimiausiu metu; formali TM patikra prieš paleidimą.
- **2026-07-23** Konkurencija ištirta: tikslaus hibrido nėra (§1b). PATVIRTINTA unikalūs elementai: „Nook" kolekcija (signature meta), didinamojo stiklo mechanika, gyva scena, dvigubas iššūkis, foto-realizmas.
- **2026-07-23** Logotipas + pavadinimas PADARYTA: Spellnook logo (`assets/branding/`), užduotis Code'ui — įdiegti programėlę telefone su logotipu (Capacitor Android).
- **2026-07-23** GitHub: viešas repo, Pages nuoroda — https://mindaugas1dirzius-ai.github.io/word-room/

## 21. Atviri klausimai
- **Fire TV nuo starto pilnai, ar planšetės pirma + TV iškart po to?** (įvesties abstrakciją darom nuo pradžios bet kuriuo atveju)
- Ar reikia „reveal object" pagalbos (kaip plaktukas)?
- Variklis: Phaser (web) ar Godot/Unity (native)?
- Kambario „tema" – realistiniai kambariai ar ir fantastiniai/teminiai (Kalėdos, kosmosas)?
- Ar daiktų pavadinimai tik EN, ar vėliau lokalizacija?
- ✅ IŠSPRĘSTA — Pavadinimas: **Spellnook** (patikrinta — laisvas; domeną pirkti artimiausiu metu, formali TM patikra prieš paleidimą).

---

## 22. Turinio planas — pirmi 3 temai (PATVIRTINTA 2026-07-23)

Kiekviena tema = 5 scenos (raundai); sunkumas kyla VIDUJE (r1 trumpi → r5 ilgi/daug), naujai temai — reset. Daiktai — pavyzdiniai; tikslius raidžių rinkinius + premijinius užbaigia sprendiklis. Iš viso ~15 scenų = MVP turinys.

### Tema 1 — „Namai" 🏠 (startas + onboarding)
- R1 Svetainė — MAP, LAMP, PALM, TABLE
- R2 Virtuvė — POT, PAN, CUP, CAN
- R3 Miegamasis — BED, BOOK, CLOCK, PILLOW
- R4 Vonia — SOAP, TOWEL, MIRROR, BRUSH
- R5 Kiemas — TREE, BENCH, FLOWER, FOUNTAIN, BIRDHOUSE

### Tema 2 — „Miestas" 🌆 (reset → r1 vėl trumpi)
- R1 Gatvė — CAR, SIGN, TREE, DOOR
- R2 Kavinė — CUP, CAKE, CHAIR, TABLE
- R3 Turgus — BREAD, APPLE, FLOWER, BASKET
- R4 Parkas — BENCH, BRIDGE, PIGEON, FOUNTAIN
- R5 Stotis — TRAIN, SUITCASE, PLATFORM, TIMETABLE

### Tema 3 — „Paryžius" 🗼 (reset → r1 vėl trumpi)
- R1 Kavinė — CUP, PLATE, CHAIR, TABLE
- R2 Gatvė — TOWER, LAMP, CAR, SIGN
- R3 Luvras — ART, FRAME, GLASS, STATUE
- R4 Krantinė — BOAT, BRIDGE, LANTERN, FOUNTAIN
- R5 Panorama — ROOFTOP, CHIMNEY, MONUMENT, CATHEDRAL, HORIZON
