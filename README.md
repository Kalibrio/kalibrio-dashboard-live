# dashboard.kalibrio.com

Static GitHub Pages site for Kalibrio product boards. Every board is an AES-256-GCM unlock page decrypted in the browser.

- `/trumble` — Trumble launch board (Live · Users · Retention · Legs)

## Source

Authored in the private repo `Kalibrio/dashboard-src` (local clone `../dashboard-src`), `trumble/index.html` + `trumble/launch.json`.

## Rebuild (daily, or after editing launch.json)

```bash
node ../dashboard-src/trumble/build.mjs
git add -A && git commit -m "build: trumble board $(date -u +%F)" && git push
```

`build.mjs` pulls the analytics rollup, inlines it, encrypts the page with the password in `~/.trumble-board-password`, and writes `trumble/index.html` here. No plaintext data is ever committed.
