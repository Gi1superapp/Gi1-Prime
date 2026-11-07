# Gi1 Prime Card - hosted site (fast, public, no login)

What is inside
- index.html - the card experience (scroll journey, 3D card, camera AR, languages, share, save contact)
- card.glb - the real 3D card model used by "Place on table" (Android Scene Viewer / WebXR and iPhone Quick Look)
- assets/ - images, signature, the HD video (loaded only when the visitor scrolls to it)
- sw.js + manifest.webmanifest - caching so the 2nd visit opens instantly, and "Add to Home Screen"
- _headers - cache rules for Cloudflare Pages (GitHub Pages ignores it)

First screen weight is about 760 KB (video, 3D model and AR engine load later in the background).

## Option A - Cloudflare Pages (best: no bandwidth limit, 300+ locations)
1. Free account at dash.cloudflare.com -> Workers & Pages -> Create -> Pages -> "Upload assets".
2. Drag this whole folder in (unzipped). Name the project e.g. gi1card. Deploy.
3. Your address is https://gi1card.pages.dev  (add your own domain later under Custom domains).

## Option B - GitHub Pages (easiest if you already use GitHub)
1. New public repository, e.g. gi1card. Upload every file in this folder to the repo root.
2. Settings -> Pages -> Build and deployment -> Deploy from a branch -> main / (root) -> Save.
3. After a minute your address is https://YOURNAME.github.io/gi1card/
GitHub Pages limits: 1 GB site size, about 100 GB bandwidth per month (soft).

## Make the QR
1. Open your new address on your phone.
2. Tap the three-dot "More" button -> the QR shown there already points to your address -> Save QR.
   (Or send the address to Claude and ask for the card back regenerated with the new QR.)
3. Paste that QR on the back of the card. It is a normal static QR: unlimited scans, no middle service, no expiry.

## Test checklist (do this before printing)
- Open the address in a private tab: it must load with no login.
- Android Chrome: Scroll the 5 screens, tap "AR view" (camera), tap "Place on table" (Scene Viewer / WebXR).
- iPhone Safari: tap "Place on table" (Quick Look opens; it builds the file on the fly, first time takes a few seconds).
- Tap Download app / WhatsApp / Call: replace the guessed links in index.html (search for PLAY, WAN, YT) with your real ones.
