# Žaidimas: „Rask daiktus kambaryje ir sudėliok žodžius" — dizainas, taisyklės, strategija

Fotorealistiškas mobilus žodžių/paslėptų-objektų žaidimas. Žaidėjas mato tikrovišką kambario nuotrauką, turi surasti joje daiktus ir sudėlioti jų pavadinimus iš raidžių ratuko. Radus žodį — kamera prizoomina į daiktą, daiktas sureaguoja (lempa užsidega, žemėlapis blyksteli ir pan.), + garsai.

## Strateginis planas (roadmap) — dabartinis fokusas
Eiliškumas, kuriuo dirbame link paleidimo:
1. **Dabar:** grūniname/šlifuojame dizainą, veikimą ir patį žaidimą — kaip jis veikia, kokios pagalbos, mechanika.
2. **Paskui:** visa žaidimo **ekonomika** (monetos, pagalbų kainos, lygių progresija, balansas).
3. **Paskui:** **monetizacija** (kaip uždirbti — reklamos, pirkimai programėlėje ir pan.).
4. Visa tai — su galutiniu tikslu **PALEISTI** programėlę.

## Paleidimo tvarka (app store'ai)
1. Pirma → **Amazon**: planšetės (Fire tablets) ir **Amazon TV / Fire TV**, Amazon Appstore.
2. Paskui → **Samsung** (Galaxy Store), **Xiaomi** (GetApps), **Huawei** (AppGallery).
3. Po to → **Apple** (App Store).
4. Galiausiai → **Google Play**.

Technika: HTML5 žaidimas apvyniojamas su **Capacitor** → tas pats Android .apk/.aab tinka Amazon / Samsung / Xiaomi / Huawei / Google Play; iOS versija per Capacitor + Xcode (reikia Mac'o). Reikės developer paskyrų, ikonos, ekranų nuotraukų, privatumo politikos ir pilno žaidimo (daug lygių).

## Pasirinkta kryptis (svarbu)
- **Fotorealizmas per 2.5D nuotraukas**, NE tikro laiko 3D. Priežastis: gražiausi šio žanro žaidimai naudoja fotografinius/pre-render vaizdus, o „gyvybę" prideda kameros judesiais ir animacijomis. Laisvas 3D vaikščiojimas fotorealistiškai reikalauja brangių 3D modelių arba realaus namo skeno (Matterport) — nebent to konkrečiai norima.
- 3D pirmojo asmens prototipas (Three.js) padarytas kaip įrodymas (`word-fps-3d` artifact), bet baldai primityvūs → atrodo „pigiai". Fotorealizmui reiktų tikrų glTF modelių.

## Nuotraukų (scenų) kūrimo taisyklės — PRIVALOMA
- **Visi ieškomi daiktai turi matytis PILNAI kadre** — jokio nukarpymo prie kraštų. Pvz. visa palmė, visas paveikslas/žemėlapis, nenukirsti baldų (lovos/stalo) kampai.
- Palik erdvės (margin) aplink kraštus, kad daiktai nesiliestų su rėmu.
- Portretinė orientacija 1080×1920 (telefonui). Šviesus, gaivus, jaukus, fotorealistiškas interjeras.
- Be teksto, be vandenženklių (pvz. Canva „REALLYGREATSITE.COM" — venkti), be žmonių.
- Centre palikti ramesnę/tuštesnę zoną UI (ratukui, langeliams).
- Daiktai turi turėti aiškius, akivaizdžius pavadinimus (žr. žemiau).

## Žodžių dizainas — sąžiningas sunkumas (be „apgaulės")
- Objektų pavadinimai — AKIVAIZDŪS tam, kas matoma (pvz. LAMP, MAP, PALM, TABLE). NE sinonimų spąstai (netinka: matai palmę, bet teisinga „PLANT", o „PALM" neįskaito — tai vercia žmogų jaustis apgautu).
- Sunkumas ateina iš: daugiau tikrų daiktų, smulkesnių/subtilesnių objektų, be žymeklių (reikia surasti akimis).
- **Premijiniai žodžiai** (kiti tikri žodžiai iš tų pačių raidžių) — visada TEIGIAMA: duoda monetų, niekada nebaudžia. Nėra „decoy, kuris neįskaito".
- Vienas raidžių rinkinys → keli objektų žodžiai + premijiniai (pvz. A,B,E,L,M,P,T → LAMP, MAP, PALM, TABLE + premijiniai PALE, PLATE, MAPLE, BEAM…).

## Pagalbų ekonomika (dabartinė)
- **LETTER / RAIDĖ (💡, −20 ◈):** atskleidžia ATSITIKTINĘ raidę iš dar neatspėtų žodžių; kiekvienas paspaudimas — vis kitą. Atskleidus visas žodžio raides — daiktas automatiškai užskaitomas.
- **ZOOM (🔍, −50 ◈):** kamera trumpam priartina/parodo vieną iš paslėptų daiktų (NEišsprendžia); kiekvienas paspaudimas — vis kitą daiktą.
- Uždarbis: radus daiktą **+20 ◈**, premijinis žodis **+5 ◈**.
- (Pilna ekonomika ir balansas — kitas etapas pagal roadmap.)

## UI / pojūtis
- Žaidimo tekstai — **angliškai**.
- **Permatomas ratukas** ir **permatomi raidžių apskritimai** — susilieja su nuotrauka, matosi tik raidės (stiprus teksto šešėlis, kad įskaitoma).
- **Vaizdas statiškas** — jokio judesio nuo pelės (parallax išjungtas, nes erzino). Kamera juda TIK radus daiktą (arba ZOOM pagalba).
- Frosted-glass viršutinis HUD (Level, monetos), žodžių langeliai (matai ilgius; atskleistos raidės — auksinės).
- **Garsai** (WebAudio, be failų): raidžių jungimas, teisingas/neteisingas spėjimas, premija, ratuko maišymas, laimėjimas. Įsijungia po pirmo palietimo.
- „Next Level" išvalo viską (ir pagalbomis atskleistas raides) — naujas lygis prasideda švarus.

## Techninės pastabos / pristatymas
- Viskas viename savarankiškame HTML faile (nuotrauka įsiūta kaip base64), veikia be interneto. Failas įrašomas ir į vartotojo kompą: **Downloads/word-room-hard.html**.
- **Debesijos serveris NEGALI hostinti** (blokuoja Canva, viešus hostus). Nuoroda telefonui: vartotojas pats numeta failą į **app.netlify.com/drop** (arba tiiny.host / Cloudflare Pages) → gauna viešą https nuorodą. (Jei būtų prijungtas Claude Chrome plėtinys — būtų galima padaryti per naršyklę.)
- Canva GENERUOJA vaizdus (per generate-design → export-design PNG), bet failo iš Canva į debesijos aplinką parsisiųsti negalima (blokuota); vartotojas parsisiunčia pats, o failą paimam iš prijungto aplanko (device bridge).
- Adobe Firefly generavimas šioje aplinkoje išjungtas.

## Kur kas saugoma
- **Claude sistema (projektas):** šis dokumentas (`claude/zaidimo-dizainas-ir-taisykles.md`) + artifacts (žr. žemiau). Matomas visose sesijose.
- **Vartotojo kompas (Downloads):** žaidimo failas `word-room-hard.html` ir šio dokumento kopija.

## Artifacts (desktop Cowork galerijoje)
- `word-room-mockup` — pagrindinė fotorealistiška versija (4 objektai, permatomos raidės, garsai, LETTER/ZOOM pagalbos, angliški tekstai).
- `word-room-explore` — naršomo („explore") kambario variantas.
- `word-fps-3d` — Three.js pirmojo asmens 3D prototipas (placeholder baldai).

## Kiti galimi žingsniai
- Daugiau lygių = daugiau fotorealistiškų kambarių (pagal taisykles aukščiau).
- Turtingesnės, „prikimštos" scenos su daugiau smulkių daiktų (sąžiningas sunkumas).
- 360° turas tarp kambarių (jei norima „vaikščiojimo po namą" jausmo išlaikant fotorealizmą).
- Capacitor projektas (paruošti Android/iOS programėlei).
