# Tender-Flow-Ads

Standalone Remotion repo for Tender Flow marketing spots. The product app lives in
[Martin82K/Tender-Flow](https://github.com/Martin82K/Tender-Flow) and must **not**
gain Remotion, `ads/instagram-reel`, or `ads:reel:*` scripts.

First composition: **`TenderFlowReel15`** — 15 s vertical Instagram Reel
(1080×1920, 30 fps, H.264). Czech copy, dark TF basic (`html.dark` / `#0f172a`),
real TF logo from `brand/`, synthetic demo data.

CTA on the last beat is **Domluvit ukázku** with `tenderflow.cz`. Landing URL for
captions / end card is `https://www.tenderflow.cz` (not `app.` and not
`tenderflow.de`). Tagline: **Jedna cesta v jednom nástroji.** The spot does not
promise výkaz výměrů, soupisy, položkovou kalkulaci, or a Helios / First RSV
replacement.

Product docs pointer: [Tender-Flow PR #471](https://github.com/Martin82K/Tender-Flow/pull/471).

## Storyboard

| Time | Screen | On-canvas copy |
| --- | --- | --- |
| 0.0–2.5 s | Kategorie | *Kategorie* / **Příprava a VŘ** / Tendry. Nabídky. Smlouva. |
| 2.5–5.0 s | Oslovení | *Uchazeči* / **Oslovení uchazečů** / Koho oslovit. Přehledně. |
| 5.0–8.5 s | Kola | *Nabídky* / **Kola nabídek** / Další kolo bez ztráty kontextu. |
| 8.5–11.5 s | Výběr | *Rozhodnutí* / **Výběr nabídky** / Rozhodnutí zůstane u zakázky. |
| 11.5–15.0 s | Smlouva + CTA | *Uzavření* / **Smlouva** / Jedna cesta v jednom nástroji. / **Domluvit ukázku** / tenderflow.cz |

Copy lives in `src/copy.ts`. Layout chrome and the TF app icon / logo are in
`src/chrome.tsx`, served from `brand/` (`logo.svg`, `TF_ico.png`,
`logo_full_text.png`).

## Studio and render

```bash
npm ci
npm test
npm run typecheck
npx remotion studio src/index.ts
npx remotion render src/index.ts TenderFlowReel15 out/TenderFlowReel15.mp4
```

Same commands via npm scripts:

```bash
npm run studio
npm run render
npm run stills
```

Output: `out/TenderFlowReel15.mp4`. Poster frames: `out/stills/`.

Studio and render use system Chrome when `CHROME_BIN` or
`REMOTION_BROWSER_EXECUTABLE` is set. Composition is 15 s, 30 fps, H.264,
1080x1920 (9:16). A verified render is in
`artifacts/TenderFlowReel15.mp4`.

## Visual

Classic dark product surfaces (`html.dark`: `#0f172a`, `#111827`, `#020617`)
matching public app screenshots, indigo primary (`#6580fb`) and the orange TF
logo accent for header / CTA. Header and end card use the real app icon
(`brand/TF_ico.png`). Scenes echo product UI: VŘ grid, kanban
Oslovení / Odesláno / Cenová nabídka / Užší výběr / Jednání o SOD, demand
overview.

Remotion has its own license; confirm whether the free license covers a
production ad, or whether a company license is required.
