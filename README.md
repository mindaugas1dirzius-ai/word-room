# Word Room — photorealistic word / hidden-object game

Mobile word puzzle: the player sees a **photorealistic room photo**, must find objects in it, and spell each object's name on a transparent letter wheel. Correct word → the camera zooms to the object, it reacts (lamp lights, map glints, plant sways), + sounds.

## Files
- `index.html` — the full, self-contained game (photo embedded as base64, works offline). Open it in any browser to play.
- `zaidimo-dizainas-ir-taisykles.md` — full design doc: rules, gameplay, helps, economy, monetization, launch order.
- `assets/` — (optional) source room photos.

## Current state (Level 1, working)
- Photoreal room (cozy living room: MAP, LAMP, PALM, TABLE).
- 4 hidden objects from an 8-letter set (A,B,E,L,M,P,T). No markers — you must find them by looking. Fair difficulty (no trick words; extra real words = positive bonus).
- Transparent wheel + transparent letter circles (blend into the photo). Static image (no mouse parallax). Camera moves only on a correct find / ZOOM help.
- Helps: **LETTER** (💡 −20◈, reveals a random letter of an unsolved word; reveal all → auto-found) and **ZOOM** (🔍 −50◈, peeks a different object each press). Earn: find +20◈, bonus word +5◈.
- Sounds (WebAudio, no files). English UI. "Next Level" fully resets.

## Scene (photo) rules — IMPORTANT for new levels
- All findable objects must be **fully in frame**, not cropped at edges; leave margins.
- Portrait 1080×1920, bright/fresh photoreal interior, no text/watermark/people, calmer center for UI.
- Object names must be **obvious** for what's visible (LAMP, MAP, TABLE…). No synonym traps.
- Free photo sources: Canva AI (control composition), or Pexels/Pixabay/Unsplash (commercial-safe).

## Roadmap
1. Polish gameplay/design (now).
2. Full economy + level progression.
3. Monetization (ads / IAP).
4. Launch: **Amazon (Fire tablets + Fire TV) → Samsung / Xiaomi / Huawei → Apple → Google Play.**

## Packaging for app stores
Wrap this HTML5 game with **Capacitor** → one codebase produces Android (.aab/.apk for Amazon, Samsung, Xiaomi, Huawei, Google Play) and iOS (App Store, via Xcode).

## To publish a test link (GitHub Pages)
1. Create a new GitHub repo.
2. Upload `index.html` (Add file → Upload files) OR push this folder.
3. Settings → Pages → Source: `main` `/root` → Save.
4. Public URL: `https://<user>.github.io/<repo>/` — open on phone.
