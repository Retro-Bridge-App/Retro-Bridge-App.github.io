# Codex task: LIGHT premium redesign of the Retro Bridge App landing page + a curated RESOURCES rail (authority articles)

Rebuild this static one-page site IN PLACE (your -C workdir): overwrite `index.html` + `style.css`, keep
every other file. No frameworks, no build, no external JS/libraries; tiny inline JS only. Premium and
polished -- NOT dry, NOT minimal, NOT oversized.

IMAGES ARE FROZEN (local): never create, overwrite, download, replace, rename, or delete any LOCAL image
(`favicon.png`, `eth.png`, `usdc.png`, `og-cover.png`, any local `*.png`/`*.svg`/`*.ico`). Use ONLY the
local images already in the folder, byte-unchanged. Keep `<link rel="icon">` and the topbar brand `<img>`
on the existing `favicon.png` (no inline `<svg>` mark, no data-URI).
ONE EXCEPTION: the bottom RESOURCES rail may use EXTERNAL `<img>` source-logos from a favicon service. No new LOCAL files.

PRESERVE from the current `index.html` (read it first): the exact keyword `Retro Bridge App` (as `<h1>` and
in `<title>`), the existing value sentence (deck `<p>` = `<meta description>`, word-for-word, light polish
only), the `<link rel=canonical>`, the money CTA target href, AND the existing topbar authority links
(Etherscan, Ethereum bridges, L2BEAT) -- keep them, never drop them.

## THEME: LIGHT premium, in the style of RetroBridge (retrobridge.io)
- This is RetroBridge, a fast multi-chain cross-chain bridge. Render LIGHT and premium in its spirit: a
  clean light base, ONE confident accent derived from `favicon.png` + your knowledge of RetroBridge (it
  uses a purple/violet-leaning palette -- verify via the favicon), soft WHITE cards with GENEROUS rounded
  corners (~16-22px), gentle soft shadows, hairline neutral borders, airy whitespace. ONE accent, no rainbow.
- `<meta name="theme-color">` = the light base background.
- Quiet premium motion only (soft pulse on the Preview dot, gentle hover lift). Respect `prefers-reduced-motion`.

## Layout (desktop ONE screen, mobile CLEAN short scroll)
Inside `<main>`: a split hero, then the RESOURCES rail (below), then the footer.
- **Topbar:** brand mark (`favicon.png`) + `Retro Bridge App` wordmark LEFT; flexible spacer; the AUTHORITY
  NAV right (Etherscan / Ethereum bridges / L2BEAT, plain text, `target="_blank" rel="nofollow noopener noreferrer"`)
  -- MUST stay present and in source HTML. No topbar button.
- **Left column (basic):** `<h1>Retro Bridge App</h1>` (see H1 SIZE) -> the deck `<p>` value sentence
  (keyword in `<strong>`) -> EXACTLY THREE qualitative trust chips (e.g. `Multi-chain bridging`,
  `One-minute transfers`, `Non-custodial`) -> ONE prominent primary CTA `Enter App`. NO `<h2>`.
- **H1 SIZE (IMPORTANT):** the hero `<h1>` must RENDER at ~80px on a 1280px desktop -- e.g.
  `font-size: clamp(2.7rem, 5.2vw, 4.7rem)` (it is 3 words, so a touch smaller cap is fine, but ~74-82px,
  NEVER under ~64px, NEVER 120px+). Scale down on mobile.
- **Right column (the star -- a RICH bridge preview, light soft card):** light chrome + a small selector pill
  + a pulsing `Preview` pill; a From (ETH, `eth.png`) -> To (USDC, `usdc.png`) bridge route in two rounded
  panels with a SMALL GAP so the circular switch sits in a clean notch; the switch swaps the two; an abstract
  `Best route` micro-row (faint hop dots, NEVER fabricated numbers); a faint number-free hint; and the
  `Start Bridge` CTA. Non-interactive preview, only the switch toggles icons. No wallet connect, no fake amounts.

## BOTTOM RESOURCES RAIL (link top authority ARTICLES on RetroBridge topics -- NOT just project logos)
Build a refined "Further reading" / "Resources" rail that links to REAL authoritative ARTICLES about what
RetroBridge is, what it is used for, how cross-chain bridges work, and its data/reviews. Use EXACTLY these
(short anchor label | source favicon domain | full link) -- do NOT invent or alter the URLs:
- Official site            | retrobridge.io   | https://retrobridge.io/
- What RetroBridge is       | medium.com       | https://retro-bridge.medium.com/retro-bridge-revolutionizing-cross-chain-bridging-in-blockchain-networks-d835ea840fad
- Bridge to Rari Chain (guide) | medium.com    | https://retro-bridge.medium.com/how-to-bridge-assets-to-rari-chain-with-retrobridge-95aa2102d562
- What are cross-chain bridges | moonpay.com   | https://www.moonpay.com/learn/blockchain/what-are-cross-chain-bridges
- How bridges work          | chainalysis.com  | https://www.chainalysis.com/blog/introduction-to-cross-chain-bridges/
- RetroBridge volume & data | defillama.com    | https://defillama.com/bridge/retrobridge
- RetroBridge review        | cryptototem.com  | https://cryptototem.com/retro-bridge/

Each item is an `<a target="_blank" rel="nofollow noopener noreferrer">` whose VISIBLE anchor text is the
short descriptive label above (this is good -- descriptive, topical anchors). Prefix each with the SOURCE
LOGO from the Google favicon service ONLY:
`https://www.google.com/s2/favicons?sz=64&domain=<FAVICON_DOMAIN>` (the only external image source; create
NO local files). Each logo `<img>`: `width`+`height` (e.g. 20x20), `loading="lazy"`, `alt=""`, `onerror="this.remove()"`.
DESIGN (neat + premium): a small quiet label like `Resources` or `Further reading on cross-chain bridging`,
then a thin tidy rail (ONE row, or two tidy rows on narrow) of compact link chips -- each = the source
favicon + the short label; muted/soft by default, gently colorizing + underlining/lifting on hover; even
spacing, calm. Keep it THIN so desktop stays ONE screen; NO horizontal overflow.

## BUTTON STYLE (2026-modern, refined -- NOT chunky)
Both CTAs: moderate size (hero ~50px, card ~48px), refined radius ~12-13px, font-weight ~600-650, slight
negative letter-spacing. Clean accent fill + SUBTLE top inner highlight (`inset 0 1px 0 rgba(255,255,255,.3)`)
+ faint 1px ring; a TIGHT low accent-tinted shadow (`0 10px 22px -12px <accent>`), NOT a big glow. A small
arrow (`&rsaquo;`) that nudges ~3px right on hover with a gentle 1px lift.

## SEO spine (LOCKED)
- `<title>` = `Retro Bridge App &mdash; <short hook>` (em-dash, keyword first, <=60 chars, no weak suffix).
- Exactly one `<h1>` = `Retro Bridge App`. NO `<h2>` anywhere.
- Deck `<p>` wraps `<strong>Retro Bridge App</strong>` and equals `<meta description>` word-for-word.
- Schema `@graph` = WebSite + WebApplication + Organization, truthful, no FAQ/HowTo. SEO text in source HTML.

## Claims (light, crypto-friendly)
- Confident premium copy welcome. Two floors: (1) invent NO specific numbers (stats, TVL, fees, dates,
  audits, partnerships) -- qualitative only; (2) no "guaranteed / risk-free / 100%", no fake wallet-connect.
- One small footer line: `Information on this page is for educational purposes only and is not financial advice.`

## CTAs + footer
- Exactly TWO, distinct, both -> the preserved target href, `rel="noopener noreferrer"`: hero `Enter App` +
  card `Start Bridge`. No third CTA, no topbar button.
- Footer: a `Retro Bridge App &mdash; 2026` brand line + the one educational line.

## Technical / mobile
- SEO content in SOURCE HTML; tiny INLINE `<script>` for the switch only; every LOCAL `<img>` has width+height.
- Desktop ONE screen: `body{min-height:100vh;min-height:100dvh}` + desktop media
  `{height:100vh;height:100dvh;overflow:hidden}` (vh BEFORE dvh); add a `max-height` desktop query to compress.
- MOBILE CLEAN: single column; bridge card full-width; route stacks neatly (switch rotates vertical); the
  resources rail wraps cleanly; comfortable spacing + tap targets; topbar collapses tidily (nav may hide but
  stays in source); short vertical scroll; ABSOLUTELY no horizontal overflow (`overflow-x:hidden` on html/body).
- Keep `lang="en"`; keep favicon/og/manifest/robots/sitemap referenced. Glyphs via HTML entities.

## Self-QC
- [ ] LIGHT premium, RetroBridge spirit; ONE accent; soft rounded cards; NOT dry.
- [ ] Topbar authority links (Etherscan / Ethereum bridges / L2BEAT) present + in source HTML.
- [ ] One `<h1>` = `Retro Bridge App`; NO `<h2>`; deck `<p>` == meta description; H1 RENDERS ~78px (not under 64).
- [ ] Modern refined buttons (~50/48px, weight ~640, radius ~12px, tight shadow, arrow nudge).
- [ ] Split hero; desktop one screen no-scroll; MOBILE clean, no horizontal overflow.
- [ ] Rich number-free ETH->USDC bridge preview; real eth.png/usdc.png; switch in a clean notch.
- [ ] RESOURCES rail: all 7 ARTICLE links with the EXACT URLs above, descriptive anchors, source favicons via Google service, nofollow, tidy, no overflow, graceful onerror.
- [ ] Exactly TWO CTAs (`Enter App` + `Start Bridge`) -> target; no topbar button.
- [ ] LOCAL images byte-untouched; favicon still the icon + brand mark; footer brand line + one educational line.

Make it genuinely premium, RetroBridge-light, with a tasteful authority-articles resources rail. Then stop.
