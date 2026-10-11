# PurposePay (installable prototype)

This folder is a Progressive Web App (PWA). People can open it in a browser and install it
on their phone's home screen. It is a **prototype**: no real money moves, nothing is saved
between visits, and there is no server. Keep `const DEMO=true;` in `index.html` until a real
backend exists, so the "Prototype" banner and the demo-only warnings stay visible.

## 1. Put it online (free, about 5 minutes)

It is a static site, so any static host works. The host must use HTTPS (all of these do).

- Netlify: go to app.netlify.com/drop and drag this whole folder onto the page.
- GitHub Pages: create a repository, upload these files, then Settings > Pages > deploy from the main branch.
- Cloudflare Pages or Vercel: connect the repository, no build step, output folder is the root.

## 2. How people "download" it

- Android (Chrome): open the link, tap the menu, then "Install app" (or "Add to Home screen").
- iPhone (Safari): open the link, tap Share, then "Add to Home Screen".
- Computer (Chrome or Edge): click the install icon in the address bar.

## 3. Put it in the Play Store (optional)

1. Host the app first, so it has a public HTTPS address.
2. Go to pwabuilder.com, paste the address, and choose Android. It produces a package for Google Play.
3. Create a Google Play developer account (one-time fee) and upload the package.

The Apple App Store needs a Mac, an Apple developer account (yearly fee), and a wrapper such as
Capacitor. It is a bigger step, so launch on Android and the web first.

## 4. Shipping a new version

Edit `index.html`, then change `CACHE = 'purposepay-v1'` in `sw.js` to `purposepay-v2`
(and so on). Without that, phones keep showing the old version.

## 5. Removing demo features

- Set `const DEMO=false;` in `index.html` to hide the Demo tab, demo buttons and demo hints.
- To delete the demo code completely, remove the block between `DEMO-START` and `DEMO-END`
  and every line that mentions `DEMO`.
- The starting balances, budgets, card, target and voucher are demo data at the top of the script.

## 6. Before real people use it

Do not let real people enter real BVN, NIN, PIN or password details here. This version does not
verify anything and keeps no server records. A real launch needs a licensed partner, a backend that
keeps the ledger and verifies identity, security testing, and compliance with Central Bank of
Nigeria and data protection rules.
