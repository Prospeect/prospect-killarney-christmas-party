# Prospect Killarney Christmas Party — GitHub Pages PWA

## Upload these files

Upload the **contents of this folder** to the root of your GitHub repository:

- `index.html`
- `manifest.webmanifest`
- `sw.js`
- `icons/`

## Turn on GitHub Pages

1. Open the repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select **main** and **/(root)**.
5. Click **Save**.
6. Open the HTTPS GitHub Pages URL shown by GitHub.

GitHub Pages supplies HTTPS, which is required for normal PWA/service-worker behavior and phone location permissions.

## What this package does now

- Installs to iPhone/Android Home Screen as a PWA.
- Registers a service worker.
- Provides in-app iPhone/Android setup instructions.
- Can request notification permission from a user gesture.
- Can send a **local test notification** from the installed app.
- Can request phone GPS permission for Find Crew.

## What still needs a backend

The static GitHub Pages package **cannot by itself send a Red Alert, Round Call, check-in, or GPS update from one person’s phone to everybody else**. For that, connect a realtime backend plus Web Push sender (for example Supabase/Firebase + a small server/edge function).

The included `sw.js` already has a `push` event handler ready to display incoming Web Push notifications once subscriptions and a push sender are added.

## iPhone

Recommended flow: Safari → Share → Add to Home Screen → turn on **Open as Web App** → Add → open the new Prospect icon → Install App tab → Enable notifications → Allow → Enable location / Share my GPS.

## Android

Recommended flow: Chrome → three-dot menu → Install app / Add to Home screen → open the Prospect icon → Install App tab → Enable notifications → Allow → Enable location / Share my GPS.


## v7 optimized GitHub version

The large inline images have been moved from `index.html` into the `assets/` folder, so `index.html` is now small enough to edit directly in GitHub.

### CARTO map API key

Open `index.html` and search for exactly:

`INSERT API KEY HERE, JOHN`

Replace only that quoted text with your full CARTO API key. Keep the quote marks and do not add spaces. Example:

```js
const CARTO_API_KEY = "your-full-key-goes-here";
```

Do not delete the rest of the line.
