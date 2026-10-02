# MILO playtest kit (v1211)

Two ways to get the game to playtesters. **Start with Way 1.** It works on Android *and* iPhone, and updating is one file.

---

## Way 1 — a link (about 10 minutes)

1. Make a free account at **github.com**, then tap **+ → New repository**. Name it `milo`. Set it to **Public** (free Pages needs that). Create it.
2. In the new repo choose **Add file → Upload files**. Drag in **everything inside this folder** (`docs`, `scripts`, `resources`, `package.json`, `capacitor.config.json`, `.gitignore`). Press **Commit changes**.
   - Easiest on a computer. Phone browsers can't drag folders.
   - Hidden folders like `.github` often don't upload. That's fine, see Way 2, step 1.
3. Go to **Settings → Pages**. Under *Build and deploy* pick **Deploy from a branch**, branch **main**, folder **/docs**, then **Save**.
4. After a minute your link appears: `https://YOURNAME.github.io/milo/`

**Tell testers:**
- **Android (Chrome):** open the link → ⋮ menu → **Install app** (or *Add to Home screen*).
- **iPhone (Safari):** open the link → Share button → **Add to Home Screen**.
- Play in **landscape**. It opens full screen and works offline after the first load.

*Don't want your code public?* Drag the `docs` folder onto **app.netlify.com/drop** instead. You get a link with no GitHub at all.

---

## Way 2 — a real .apk file (Android only)

The robot in the cloud builds it for you. You don't need Android Studio.

1. In your repo choose **Add file → Create new file**. In the name box type exactly `.github/workflows/build-apk.yml` (typing the slashes makes the folders). Open **COPY-THIS-build-apk.yml.txt** from this kit, copy everything, paste it in, **Commit**.
2. Open the **Actions** tab. A run called *Build Android APK* starts by itself (about 5–8 minutes). Wait for the green tick.
3. Tap the run → scroll to **Artifacts** → download **MILO-apk**. It's a zip with `app-debug.apk` inside.
4. Send that file to testers. They tap it and allow **Install unknown apps** when Android asks. Play Protect may say "unrecognized app". Tap **Install anyway**.

**Red ✗ instead of green?** Open the run, copy the red error text, and send it to me. I haven't been able to run this cloud build myself, so the first attempt may need a small fix.

---

## Updating after you change the game

1. Replace `docs/index.html` in the repo (open the file → pencil/trash → or *Upload files* again).
2. Change `milo-v1211` to something new inside `docs/sw.js` (for example `milo-v1212`).
3. The link updates itself. The APK rebuilds automatically (Way 2).

## Good to know
- **Back button (Android app):** pauses the game instead of closing it. On the title screen it exits.
- **Saves** live on each phone. Uninstalling the app or clearing browser data wipes them.
- The `.apk` is **debug-signed**: fine for sharing, **not** for Google Play. For Play I'd set up a proper signed bundle with you.
- Icon is a paw + collar-lightning bolt. Swap the PNGs in `docs/` and `resources/android/` if you want different art.
