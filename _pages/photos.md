---
title: "Photos"
permalink: /photos/
classes: photos-page
---

<style>
  /* ════════════════════════════════════════════════════════════
     PHOTOS PAGE — full facelift
     Serves a different purpose from home, about, services.
     This page SHOWS THE WORK through interactive visual
     storytelling — filter, explore, lightbox, film strip.
     ════════════════════════════════════════════════════════════ */

  /* ── Layout fix: kill theme's page title + side padding ── */
  body.photos-page .page__title { display: none !important; }
  body.photos-page h1#page-title { display: none !important; }
  body.photos-page .page__hero { display: none !important; }
  body.photos-page .page__hero--overlay { display: none !important; }
  body.photos-page .initial-content { padding-top: 0 !important; margin-top: 0 !important; }
  body.photos-page .page { width: 100% !important; padding-right: 0 !important; }
  body.photos-page .page__inner-wrap { width: 100% !important; max-width: 100% !important; }
  body.photos-page .page__content { width: 100% !important; max-width: 100% !important; padding: 0 !important; }
  body.photos-page .archive { width: 100% !important; max-width: 100% !important; padding: 0 !important; margin: 0 !important; }
  body.photos-page #main { max-width: 100% !important; padding: 0 !important; }

  /* ── Sticky mini-nav ── */
  .ph-mini-nav {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 90;
    background: rgba(10, 10, 15, 0.85);
    backdrop-filter: blur(14px) saturate(180%);
    -webkit-backdrop-filter: blur(14px) saturate(180%);
    border-bottom: 1px solid var(--border-subtle);
    padding: 0.85rem 1.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1.75rem;
    transform: translateY(-100%);
    transition: transform 0.4s var(--ease-out-expo);
    font-size: 0.78rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
  }
  .ph-mini-nav.is-visible { transform: translateY(0); }
  .ph-mini-nav a {
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s var(--ease-out-expo);
    position: relative;
  }
  .ph-mini-nav a::after {
    content: "";
    position: absolute;
    bottom: -6px;
    left: 0;
    right: 0;
    height: 1px;
    background: #04a9ff;
    transform: scaleX(0);
    transition: transform 0.2s var(--ease-out-expo);
  }
  .ph-mini-nav a:hover { color: #04a9ff; }
  .ph-mini-nav a:hover::after { transform: scaleX(1); }

  /* ── HERO ── */
  .ph-hero {
    position: relative;
    min-height: calc(100vh - 80px);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 9rem 1.5rem 7rem;
    overflow: hidden;
    background:
      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(4, 169, 255, 0.14), transparent 70%),
      var(--bg-primary);
  }
  .ph-hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/images/about.jpg");
    background-size: cover;
    background-position: center;
    opacity: 0.30;
    filter: grayscale(30%) saturate(0.85) contrast(1.05);
    pointer-events: none;
    z-index: 0;
  }
  .ph-hero::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 70% 60% at 50% 50%, transparent 0%, rgba(10, 10, 15, 0.45) 60%, var(--bg-primary) 95%),
      linear-gradient(180deg, var(--bg-primary) 0%, transparent 12%, transparent 88%, var(--bg-primary) 100%);
    pointer-events: none;
    z-index: 1;
  }
  .ph-hero__inner {
    position: relative;
    z-index: 2;
    text-align: center;
    max-width: 880px;
    margin: 0 auto;
  }
  .ph-eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.4rem 0.95rem;
    background: rgba(4, 169, 255, 0.08);
    border: 1px solid rgba(4, 169, 255, 0.18);
    border-radius: 100px;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 2rem;
  }
  .ph-eyebrow__dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #04a9ff;
    box-shadow: 0 0 8px rgba(4, 169, 255, 0.6);
  }
  .ph-hero h1 {
    font-size: clamp(2.4rem, 6vw, 4.8rem);
    font-weight: 600;
    letter-spacing: -0.04em;
    line-height: 1.04;
    margin: 0 0 1.5rem;
    color: var(--text-primary);
  }
  .ph-hero h1 .gold {
    background: linear-gradient(135deg, #33bbff 0%, #04a9ff 50%, #0090dd 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-style: italic;
    font-weight: 500;
  }
  .ph-hero__sub {
    font-size: clamp(1.05rem, 1.4vw, 1.2rem);
    color: rgba(242, 242, 245, 0.65);
    line-height: 1.65;
    max-width: 600px;
    margin: 0 auto 2.5rem;
  }
  .ph-hero__ctas {
    display: flex;
    gap: 0.75rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 3rem;
  }
  .ph-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    padding: 0.95rem 1.6rem;
    border-radius: var(--radius-sm);
    font-family: var(--font-sans);
    font-size: 0.95rem;
    font-weight: 600;
    letter-spacing: -0.01em;
    text-decoration: none !important;
    border: 1px solid transparent;
    cursor: pointer;
    transition: all 0.2s var(--ease-out-expo);
    min-height: 48px;
    white-space: nowrap;
  }
  .ph-btn--primary {
    background: #04a9ff;
    color: #0a0a0f !important;
  }
  .ph-btn--primary:hover {
    background: #33bbff;
    transform: translateY(-1px);
    box-shadow: 0 8px 24px rgba(4, 169, 255, 0.25);
  }
  .ph-btn--ghost {
    background: rgba(255, 255, 255, 0.04);
    color: var(--text-primary) !important;
    border-color: rgba(255, 255, 255, 0.12);
  }
  .ph-btn--ghost:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(255, 255, 255, 0.22);
    transform: translateY(-1px);
  }
  .ph-btn__arrow { transition: transform 0.2s var(--ease-out-expo); }
  .ph-btn:hover .ph-btn__arrow { transform: translateX(3px); }

  .ph-scroll-cue {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: var(--text-muted);
    font-size: 0.7rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
  }
  .ph-scroll-cue__line {
    width: 1px;
    height: 36px;
    background: linear-gradient(180deg, rgba(4, 169, 255, 0.6), transparent);
    position: relative;
    overflow: hidden;
  }
  .ph-scroll-cue__line::after {
    content: "";
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 8px;
    background: #04a9ff;
    animation: phScrollDot 2s ease-in-out infinite;
  }
  @keyframes phScrollDot {
    0% { transform: translateY(-100%); opacity: 0; }
    30% { opacity: 1; }
    100% { transform: translateY(360%); opacity: 0; }
  }
  .ph-eq {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    align-items: flex-end;
    gap: 4px;
    height: 28px;
    opacity: 0.18;
    z-index: 0;
    pointer-events: none;
  }
  .ph-eq span {
    display: block;
    width: 3px;
    background: linear-gradient(180deg, transparent, #04a9ff 30%, #04a9ff 70%, transparent);
    border-radius: 2px;
    animation: phEqBar 1.4s ease-in-out infinite;
  }
  .ph-eq span:nth-child(1)  { height: 12px; animation-delay: 0.0s; }
  .ph-eq span:nth-child(2)  { height: 20px; animation-delay: 0.15s; }
  .ph-eq span:nth-child(3)  { height: 8px;  animation-delay: 0.3s; }
  .ph-eq span:nth-child(4)  { height: 24px; animation-delay: 0.1s; }
  .ph-eq span:nth-child(5)  { height: 14px; animation-delay: 0.45s; }
  .ph-eq span:nth-child(6)  { height: 18px; animation-delay: 0.25s; }
  .ph-eq span:nth-child(7)  { height: 26px; animation-delay: 0.05s; }
  .ph-eq span:nth-child(8)  { height: 10px; animation-delay: 0.4s; }
  .ph-eq span:nth-child(9)  { height: 22px; animation-delay: 0.2s; }
  .ph-eq span:nth-child(10) { height: 16px; animation-delay: 0.35s; }
  .ph-eq span:nth-child(11) { height: 8px;  animation-delay: 0.5s; }
  .ph-eq span:nth-child(12) { height: 20px; animation-delay: 0.1s; }
  .ph-eq span:nth-child(13) { height: 14px; animation-delay: 0.3s; }
  .ph-eq span:nth-child(14) { height: 24px; animation-delay: 0.2s; }
  .ph-eq span:nth-child(15) { height: 12px; animation-delay: 0.4s; }
  @keyframes phEqBar {
    0%, 100% { transform: scaleY(0.4); }
    50%      { transform: scaleY(1.6); }
  }

  /* ════════════════════════════════════════════════════════════
     THE FILTER CONSOLE — unique widget, not on any other page
     Styled like a hardware selector. Active filter has a glowing
     power-LED + active-light bar. Filter chips live in a rack
     panel that hovers in to reveal real-time counts.
     ════════════════════════════════════════════════════════════ */
  .ph-console {
    padding: 4rem 1.5rem 1rem;
    background: var(--bg-primary);
    position: relative;
  }
  .ph-console::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }

  .ph-console__panel {
    max-width: 1100px;
    margin: 0 auto;
    padding: 1.25rem 1.5rem;
    background: linear-gradient(180deg, #14141a 0%, #0e0e14 100%);
    border: 1px solid rgba(4, 169, 255, 0.18);
    border-radius: var(--radius-lg);
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.04),
      0 8px 30px rgba(0, 0, 0, 0.3);
    display: flex;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
    position: relative;
  }
  .ph-console__brand {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.22em;
    color: rgba(4, 169, 255, 0.8);
    padding: 0.3rem 0.6rem;
    background: linear-gradient(135deg, rgba(4, 169, 255, 0.18) 0%, rgba(4, 169, 255, 0.08) 100%);
    border: 1px solid rgba(4, 169, 255, 0.4);
    border-radius: 3px;
    flex-shrink: 0;
  }
  .ph-console__led {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    margin-left: auto;
    flex-shrink: 0;
  }
  .ph-console__led .led {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #4ade80;
    box-shadow: 0 0 6px rgba(74, 222, 128, 0.8), inset 0 0 2px rgba(255, 255, 255, 0.3);
    animation: phLedPulse 2.4s ease-in-out infinite;
  }
  .ph-console__led .led-lbl {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.55rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    color: var(--text-muted);
    text-transform: uppercase;
    margin-left: 0.35rem;
  }
  @keyframes phLedPulse {
    0%, 100% { opacity: 1; }
    50%      { opacity: 0.45; }
  }

  .ph-filter-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    flex: 1;
    justify-content: center;
  }
  .ph-filter {
    position: relative;
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.55rem 1rem;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 100px;
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--text-secondary);
    letter-spacing: -0.01em;
    cursor: pointer;
    transition: all 0.25s var(--ease-out-expo);
    white-space: nowrap;
  }
  .ph-filter .ph-filter__count {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-width: 20px;
    height: 18px;
    padding: 0 0.4rem;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 100px;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.62rem;
    font-weight: 700;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }
  .ph-filter i {
    color: #04a9ff;
    font-size: 0.8rem;
  }
  .ph-filter:hover {
    background: rgba(255, 255, 255, 0.05);
    border-color: rgba(4, 169, 255, 0.3);
    color: var(--text-primary);
    transform: translateY(-1px);
  }
  .ph-filter.is-on {
    background: linear-gradient(135deg, rgba(4, 169, 255, 0.18) 0%, rgba(4, 169, 255, 0.06) 100%);
    border-color: rgba(4, 169, 255, 0.5);
    color: #04a9ff;
    box-shadow: 0 0 12px rgba(4, 169, 255, 0.15);
  }
  .ph-filter.is-on .ph-filter__count {
    background: rgba(4, 169, 255, 0.2);
    color: #04a9ff;
  }

  /* Result count line under the console */
  .ph-console__result {
    max-width: 1100px;
    margin: 0.85rem auto 0;
    text-align: center;
    font-size: 0.72rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }
  .ph-console__result b {
    color: #04a9ff;
    font-weight: 600;
  }

  /* ════════════════════════════════════════════════════════════
     THE GALLERY — asymmetric bento mosaic
     One featured large tile (the "hero shot") + smaller tiles
     in a varied layout. Each tile has hover effects, EXIF info,
     and opens a lightbox on click.
     ════════════════════════════════════════════════════════════ */
  .ph-gallery {
    padding: 3rem 1.5rem 5rem;
    max-width: 1200px;
    margin: 0 auto;
  }
  .ph-mosaic {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: 180px;
    gap: 0.85rem;
  }
  /* Featured tile (first one) — spans 2 cols × 2 rows */
  .ph-tile--feat {
    grid-column: span 2;
    grid-row: span 2;
  }
  /* Tall tile (one of them) — spans 1 col × 2 rows */
  .ph-tile--tall {
    grid-row: span 2;
  }
  /* Wide tile (one of them) — spans 2 cols × 1 row */
  .ph-tile--wide {
    grid-column: span 2;
  }

  .ph-tile {
    position: relative;
    overflow: hidden;
    border-radius: var(--radius-md);
    border: 1px solid rgba(255, 255, 255, 0.04);
    cursor: pointer;
    background: var(--bg-secondary);
    transition: all 0.4s var(--ease-out-expo);
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.3);
  }
  .ph-tile img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    transition: transform 0.6s var(--ease-out-expo), filter 0.4s var(--ease-out-expo);
    filter: brightness(0.85) saturate(0.95);
  }

  /* EXIF-style badge — top-left, always visible */
  .ph-tile__exif {
    position: absolute;
    top: 0.7rem; left: 0.7rem;
    z-index: 2;
    display: flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.3rem 0.6rem;
    background: rgba(10, 10, 15, 0.7);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 3px;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.55rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    color: var(--text-muted);
    text-transform: uppercase;
    opacity: 0;
    transform: translateY(-4px);
    transition: all 0.3s var(--ease-out-expo);
  }
  .ph-tile__exif i { color: #04a9ff; }

  /* Event tag — top-right, always visible */
  .ph-tile__tag {
    position: absolute;
    top: 0.7rem; right: 0.7rem;
    z-index: 2;
    padding: 0.3rem 0.6rem;
    background: rgba(4, 169, 255, 0.18);
    border: 1px solid rgba(4, 169, 255, 0.4);
    border-radius: 3px;
    font-size: 0.55rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    color: #04a9ff;
    text-transform: uppercase;
    opacity: 0;
    transform: translateY(-4px);
    transition: all 0.3s var(--ease-out-expo);
  }

  /* Bottom caption strip — slides up on hover */
  .ph-tile__cap {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    z-index: 2;
    padding: 1.5rem 1rem 0.85rem;
    background: linear-gradient(180deg, transparent 0%, rgba(10, 10, 15, 0.85) 50%, rgba(10, 10, 15, 0.95) 100%);
    transform: translateY(100%);
    transition: transform 0.35s var(--ease-out-expo);
  }
  .ph-tile__cap-venue {
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin: 0 0 0.15rem;
  }
  .ph-tile__cap-meta {
    font-size: 0.7rem;
    color: rgba(4, 169, 255, 0.85);
    letter-spacing: 0.04em;
    text-transform: uppercase;
    font-weight: 500;
  }

  /* Center "view" button — only shows on hover */
  .ph-tile__view {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%) scale(0.7);
    z-index: 2;
    width: 52px; height: 52px;
    border-radius: 50%;
    background: rgba(4, 169, 255, 0.95);
    color: #0a0a0f;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: all 0.3s var(--ease-out-expo);
    box-shadow: 0 4px 18px rgba(4, 169, 255, 0.4);
  }
  .ph-tile__view i { font-size: 0.95rem; margin-left: 2px; }

  .ph-tile:hover {
    border-color: rgba(4, 169, 255, 0.4);
    transform: translateY(-3px);
    box-shadow:
      0 0 0 1px rgba(4, 169, 255, 0.25),
      0 16px 40px rgba(0, 0, 0, 0.5),
      0 0 30px rgba(4, 169, 255, 0.1);
  }
  .ph-tile:hover img {
    transform: scale(1.06);
    filter: brightness(0.6) saturate(0.85);
  }
  .ph-tile:hover .ph-tile__exif,
  .ph-tile:hover .ph-tile__tag {
    opacity: 1;
    transform: translateY(0);
  }
  .ph-tile:hover .ph-tile__cap {
    transform: translateY(0);
  }
  .ph-tile:hover .ph-tile__view {
    opacity: 1;
    transform: translate(-50%, -50%) scale(1);
  }

  /* Hidden by default during filtering */
  .ph-tile.is-hidden {
    display: none;
  }

  /* Stagger reveal */
  .ph-tile {
    opacity: 0;
    transform: scale(0.96);
    transition: opacity 0.5s var(--ease-out-expo), transform 0.5s var(--ease-out-expo);
  }
  .ph-tile.is-visible {
    opacity: 1;
    transform: scale(1);
  }
  .ph-tile.is-visible:hover {
    transform: translateY(-3px) scale(1);
  }

  /* ════════════════════════════════════════════════════════════
     LIGHTBOX — full-bleed photo viewer
     ════════════════════════════════════════════════════════════ */
  .ph-lightbox {
    position: fixed;
    inset: 0;
    z-index: 200;
    background: rgba(0, 0, 0, 0.96);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s var(--ease-out-expo);
  }
  .ph-lightbox.is-on {
    opacity: 1;
    pointer-events: all;
  }

  .ph-lightbox__stage {
    position: relative;
    width: 100%;
    max-width: min(90vw, 1400px);
    max-height: 80vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .ph-lightbox__img {
    max-width: 100%;
    max-height: 80vh;
    object-fit: contain;
    border-radius: var(--radius-sm);
    box-shadow: 0 30px 80px rgba(0, 0, 0, 0.6);
    transition: opacity 0.25s var(--ease-out-expo), transform 0.3s var(--ease-out-expo);
  }
  .ph-lightbox__img.is-fading {
    opacity: 0;
    transform: scale(0.98);
  }

  /* Top bar — close button + meta */
  .ph-lightbox__top {
    position: absolute;
    top: 1.5rem; left: 1.5rem; right: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 2;
  }
  .ph-lightbox__meta {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  .ph-lightbox__counter {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.78rem;
    color: var(--text-muted);
    letter-spacing: 0.18em;
  }
  .ph-lightbox__counter b { color: #04a9ff; font-weight: 600; }
  .ph-lightbox__exif {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.4rem 0.7rem;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 3px;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.62rem;
    color: var(--text-muted);
    letter-spacing: 0.1em;
  }
  .ph-lightbox__exif i { color: #04a9ff; }
  .ph-lightbox__close {
    width: 44px; height: 44px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--text-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.2s var(--ease-out-expo);
  }
  .ph-lightbox__close:hover {
    background: rgba(255, 255, 255, 0.1);
    color: #04a9ff;
    transform: rotate(90deg);
  }

  /* Side arrows */
  .ph-lightbox__nav {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 56px; height: 56px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--text-primary);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    z-index: 2;
    transition: all 0.2s var(--ease-out-expo);
  }
  .ph-lightbox__nav:hover {
    background: rgba(4, 169, 255, 0.18);
    border-color: rgba(4, 169, 255, 0.5);
    color: #04a9ff;
  }
  .ph-lightbox__nav--prev { left: 1.5rem; }
  .ph-lightbox__nav--next { right: 1.5rem; }

  /* Caption below the image */
  .ph-lightbox__cap {
    position: absolute;
    bottom: 5rem; left: 50%;
    transform: translateX(-50%);
    text-align: center;
    z-index: 2;
  }
  .ph-lightbox__cap-venue {
    font-size: 1rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin: 0 0 0.3rem;
  }
  .ph-lightbox__cap-meta {
    font-size: 0.78rem;
    color: #04a9ff;
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  /* Film strip at the bottom */
  .ph-lightbox__strip {
    position: absolute;
    bottom: 1.25rem; left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 0.4rem;
    padding: 0.4rem;
    background: rgba(10, 10, 15, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    max-width: min(90vw, 800px);
    overflow-x: auto;
    scrollbar-width: thin;
    scrollbar-color: rgba(4, 169, 255, 0.3) transparent;
  }
  .ph-lightbox__strip::-webkit-scrollbar { height: 4px; }
  .ph-lightbox__strip::-webkit-scrollbar-thumb { background: rgba(4, 169, 255, 0.3); border-radius: 2px; }
  .ph-lightbox__strip-item {
    flex-shrink: 0;
    width: 60px; height: 40px;
    border-radius: 4px;
    overflow: hidden;
    cursor: pointer;
    border: 2px solid transparent;
    opacity: 0.6;
    transition: all 0.2s var(--ease-out-expo);
  }
  .ph-lightbox__strip-item img {
    width: 100%; height: 100%;
    object-fit: cover;
  }
  .ph-lightbox__strip-item:hover { opacity: 1; }
  .ph-lightbox__strip-item.is-on {
    border-color: #04a9ff;
    opacity: 1;
    box-shadow: 0 0 8px rgba(4, 169, 255, 0.4);
  }

  /* ════════════════════════════════════════════════════════════
     PHOTO STRIP — horizontal scrollable index above the CTA
     ════════════════════════════════════════════════════════════ */
  .ph-strip-wrap {
    padding: 2rem 1.5rem 4rem;
    background:
      linear-gradient(180deg, var(--bg-primary) 0%, var(--bg-secondary) 100%);
    position: relative;
  }
  .ph-strip-wrap::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .ph-strip-head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 2rem;
  }
  .ph-strip-eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1rem;
  }
  .ph-strip-title {
    font-size: clamp(1.5rem, 2.8vw, 2rem);
    font-weight: 600;
    letter-spacing: -0.03em;
    line-height: 1.15;
    margin: 0 0 0.6rem;
    color: var(--text-primary);
  }
  .ph-strip-sub {
    font-size: 0.95rem;
    color: var(--text-secondary);
    line-height: 1.55;
    margin: 0;
  }
  .ph-strip {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    gap: 0.75rem;
    overflow-x: auto;
    padding: 0.5rem 0.25rem 1rem;
    scroll-snap-type: x mandatory;
    scrollbar-width: thin;
    scrollbar-color: rgba(4, 169, 255, 0.3) transparent;
  }
  .ph-strip::-webkit-scrollbar { height: 6px; }
  .ph-strip::-webkit-scrollbar-thumb { background: rgba(4, 169, 255, 0.3); border-radius: 3px; }
  .ph-strip-item {
    flex-shrink: 0;
    width: 220px;
    aspect-ratio: 4 / 3;
    border-radius: var(--radius-sm);
    overflow: hidden;
    position: relative;
    cursor: pointer;
    scroll-snap-align: start;
    transition: all 0.3s var(--ease-out-expo);
    border: 1px solid rgba(255, 255, 255, 0.05);
  }
  .ph-strip-item img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.5s var(--ease-out-expo);
  }
  .ph-strip-item__num {
    position: absolute;
    top: 0.5rem; left: 0.5rem;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.65rem;
    font-weight: 700;
    color: #04a9ff;
    background: rgba(10, 10, 15, 0.7);
    backdrop-filter: blur(6px);
    -webkit-backdrop-filter: blur(6px);
    padding: 0.2rem 0.45rem;
    border-radius: 3px;
    border: 1px solid rgba(4, 169, 255, 0.3);
    z-index: 1;
  }
  .ph-strip-item__name {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    padding: 1.5rem 0.75rem 0.6rem;
    background: linear-gradient(180deg, transparent 0%, rgba(10, 10, 15, 0.9) 70%);
    font-size: 0.78rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    z-index: 1;
  }
  .ph-strip-item:hover {
    transform: translateY(-3px);
    border-color: rgba(4, 169, 255, 0.4);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.4), 0 0 20px rgba(4, 169, 255, 0.1);
  }
  .ph-strip-item:hover img {
    transform: scale(1.05);
  }

  /* ════════════════════════════════════════════════════════════
     FINAL CTA
     ════════════════════════════════════════════════════════════ */
  .ph-cta {
    position: relative;
    max-width: var(--content-width);
    margin: 0 auto 5rem;
    padding: 5.5rem 2.5rem;
    text-align: center;
    background:
      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(4, 169, 255, 0.10), transparent 70%),
      linear-gradient(135deg, rgba(4, 169, 255, 0.08) 0%, rgba(4, 169, 255, 0.02) 100%);
    border: 1px solid rgba(4, 169, 255, 0.22);
    border-radius: var(--radius-xl);
    overflow: hidden;
    box-shadow:
      0 1px 0 rgba(4, 169, 255, 0.2) inset,
      0 30px 80px rgba(0, 0, 0, 0.4);
  }
  .ph-cta::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 200px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .ph-cta__eq {
    position: absolute;
    top: 1.25rem; left: 50%;
    transform: translateX(-50%);
    display: flex;
    align-items: flex-end;
    gap: 3px;
    height: 18px;
    opacity: 0.25;
    z-index: 0;
    pointer-events: none;
  }
  .ph-cta__eq span {
    display: block;
    width: 2px;
    background: #04a9ff;
    border-radius: 1px;
    animation: phEqBar 1.6s ease-in-out infinite;
  }
  .ph-cta__eq span:nth-child(1)  { height: 8px;  animation-delay: 0.0s; }
  .ph-cta__eq span:nth-child(2)  { height: 14px; animation-delay: 0.2s; }
  .ph-cta__eq span:nth-child(3)  { height: 6px;  animation-delay: 0.4s; }
  .ph-cta__eq span:nth-child(4)  { height: 16px; animation-delay: 0.1s; }
  .ph-cta__eq span:nth-child(5)  { height: 10px; animation-delay: 0.3s; }
  .ph-cta__eq span:nth-child(6)  { height: 18px; animation-delay: 0.15s; }
  .ph-cta__eq span:nth-child(7)  { height: 8px;  animation-delay: 0.35s; }
  .ph-cta__eq span:nth-child(8)  { height: 12px; animation-delay: 0.05s; }
  .ph-cta__eq span:nth-child(9)  { height: 6px;  animation-delay: 0.25s; }
  .ph-cta__eq span:nth-child(10) { height: 14px; animation-delay: 0.45s; }
  .ph-cta h2 {
    position: relative;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .ph-cta p {
    position: relative;
    font-size: 1.05rem;
    color: var(--text-secondary);
    line-height: 1.65;
    max-width: 520px;
    margin: 0 auto 2rem;
  }
  .ph-cta .ph-btn { position: relative; }
  .ph-cta__note {
    position: relative;
    display: block;
    margin-top: 1.25rem;
    font-size: 0.8rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }

  /* Scroll reveal */
  .ph-reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease-out, transform 0.7s ease-out;
  }
  .ph-reveal.is-visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    .ph-mosaic { grid-template-columns: repeat(3, 1fr); }
    .ph-tile--feat { grid-column: span 2; grid-row: span 2; }
    .ph-tile--tall { grid-row: span 1; }
    .ph-tile--wide { grid-column: span 1; }
    .ph-mini-nav { gap: 1rem; font-size: 0.7rem; }
    .ph-console__brand { display: none; }
    .ph-console__led { display: none; }
    .ph-console__panel { justify-content: center; }
  }
  @media (max-width: 600px) {
    .ph-hero { padding: 7rem 1rem 5rem; min-height: auto; }
    .ph-mosaic { grid-template-columns: repeat(2, 1fr); }
    .ph-tile--feat { grid-column: span 2; grid-row: span 2; }
    .ph-tile--tall, .ph-tile--wide { grid-row: auto; grid-column: auto; }
    .ph-console { padding: 3rem 1rem 1rem; }
    .ph-gallery { padding: 2rem 1rem 3rem; }
    .ph-strip-wrap { padding: 2rem 1rem 3rem; }
    .ph-strip-item { width: 160px; }
    .ph-cta { padding: 3.5rem 1.5rem; }
    .ph-lightbox__nav--prev { left: 0.5rem; }
    .ph-lightbox__nav--next { right: 0.5rem; }
    .ph-lightbox__nav { width: 40px; height: 40px; }
  }
</style>

<!-- ═══ STICKY MINI-NAV ═══ -->
<nav class="ph-mini-nav" aria-label="Page sections">
  <a href="#ph-console">Gallery</a>
  <a href="#ph-strip">Photos</a>
  <a href="#ph-cta">Book a visit</a>
</nav>

<!-- ═══ HERO ═══ -->
<section class="ph-hero">
  <div class="ph-hero__inner">
    <div class="ph-eyebrow ph-reveal">
      <span class="ph-eyebrow__dot"></span>
      PHOTOS
    </div>
    <h1 class="ph-reveal">
      Create <span class="gold">moments.</span>
    </h1>
    <div class="ph-hero__ctas ph-reveal">
      <a href="#ph-all" class="ph-btn ph-btn--primary">
        Gallery
        <span class="ph-btn__arrow">→</span>
      </a>
      <a href="/contact/" class="ph-btn ph-btn--ghost">
        Discuss
      </a>
    </div>
    <div class="ph-scroll-cue ph-reveal" aria-hidden="true">
      <span>Scroll</span>
      <span class="ph-scroll-cue__line"></span>
    </div>
  </div>
  <div class="ph-eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
</section>

<!-- ═══ THE FILTER CONSOLE ═══ -->
<!-- ═══ CONSOLE BAR ═══ -->
<section class="ph-console" id="ph-console">
  <div class="ph-console__bar">
    <span class="ph-console__led">
      <span class="led led--green"></span>
      <span class="led-lbl">Live</span>
    </span>
  </div>
  <div class="ph-console__result" id="ph-result">
    Showing <b>2</b> frames
  </div>
</section>

<!-- ═══ THE GALLERY ═══ -->
<section class="ph-gallery">
  <div class="ph-mosaic" id="ph-mosaic">
    <a class="ph-tile ph-tile--feat ph-reveal" href="#" data-src="/images/gallery-2.jpg" data-exif="f/2.8 · 1/60s · ISO 800">
      <img src="/images/gallery-2.jpg" alt="Gallery frame 1">
      <span class="ph-tile__exif"><i class="fas fa-camera"></i> f/2.8 · 1/60s · ISO 800</span>
      <div class="ph-tile__view"><i class="fas fa-expand"></i></div>
    </a>

    <a class="ph-tile ph-reveal" href="#" data-src="/images/gallery-1.jpg" data-exif="f/1.8 · 1/125s · ISO 400">
      <img src="/images/gallery-1.jpg" alt="Gallery frame 2">
      <span class="ph-tile__exif"><i class="fas fa-camera"></i> f/1.8 · 1/125s · ISO 400</span>
      <div class="ph-tile__view"><i class="fas fa-expand"></i></div>
    </a>
  </div>
</section>

<!-- ═══ PHOTO STRIP ═══ -->
<section class="ph-strip-wrap" id="ph-strip">
  <div class="ph-strip-head ph-reveal">
    <div class="ph-strip-eyebrow">Photos</div>
    <h2 class="ph-strip-title">Browse frames.</h2>
    <p class="ph-strip-sub">Click any frame to jump back to the gallery.</p>
  </div>
  <div class="ph-strip" id="ph-strip-track">
    <a class="ph-strip-item" href="#" data-target="0">
      <span class="ph-strip-item__num">01</span>
      <img src="/images/gallery-1.jpg" alt="Frame 1">
    </a>
    <a class="ph-strip-item" href="#" data-target="1">
      <span class="ph-strip-item__num">02</span>
      <img src="/images/gallery-2.jpg" alt="Frame 2">
    </a>
  </div>
</section>

<!-- ═══ FINAL CTA ═══ -->
<section class="ph-cta ph-reveal" id="ph-cta">
  <div class="ph-cta__eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
  <h2>See it in action.</h2>
  <p>See the setup in person.</p>
  <a href="/contact/" class="ph-btn ph-btn--primary">
    Book a visit
    <span class="ph-btn__arrow">→</span>
  </a>
  <span class="ph-cta__note">Free · 15 minutes · In-person or video</span>
</section>

<!-- ═══ LIGHTBOX ═══ -->
<div class="ph-lightbox" id="ph-lightbox" role="dialog" aria-modal="true" aria-label="Photo viewer">
  <div class="ph-lightbox__top">
    <div class="ph-lightbox__meta">
      <span class="ph-lightbox__counter" id="ph-lb-counter"><b>01</b> / 07</span>
      <span class="ph-lightbox__exif" id="ph-lb-exif"><i class="fas fa-camera"></i> f/2.8 · 1/60s · ISO 800</span>
    </div>
    <button class="ph-lightbox__close" id="ph-lb-close" aria-label="Close"><i class="fas fa-times"></i></button>
  </div>
  <div class="ph-lightbox__nav ph-lightbox__nav--prev" id="ph-lb-prev" aria-label="Previous photo"><i class="fas fa-chevron-left"></i></div>
  <div class="ph-lightbox__nav ph-lightbox__nav--next" id="ph-lb-next" aria-label="Next photo"><i class="fas fa-chevron-right"></i></div>
  <div class="ph-lightbox__stage">
    <img class="ph-lightbox__img" id="ph-lb-img" src="" alt="">
    <div class="ph-lightbox__cap">
      <div class="ph-lightbox__cap-venue" id="ph-lb-venue">Bateau Bay Hotel</div>
      <div class="ph-lightbox__cap-meta" id="ph-lb-type">Venue · 220 guests</div>
    </div>
  </div>
  <div class="ph-lightbox__strip" id="ph-lb-strip"></div>
</div>

<script>
  (function() {
    // Photo data — single source of truth, derived from the DOM tiles
    function buildPhotoIndex() {
      const tiles = Array.from(document.querySelectorAll('.ph-tile'));
      return tiles.map((tile, idx) => ({
        idx: idx,
        src: tile.getAttribute('data-src'),
        venue: tile.getAttribute('data-venue'),
        type: tile.getAttribute('data-type'),
        exif: tile.getAttribute('data-exif'),
        tags: (tile.getAttribute('data-tags') || '').split(/\s+/).filter(Boolean),
        el: tile
      }));
    }

    // ── Reveal on scroll ──
    function setupReveal() {
      const els = document.querySelectorAll('.ph-reveal, .ph-tile');
      if (!('IntersectionObserver' in window)) {
        els.forEach(el => el.classList.add('is-visible'));
        return;
      }
      const obs = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if (e.isIntersecting) {
            e.target.classList.add('is-visible');
            obs.unobserve(e.target);
          }
        });
      }, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
      els.forEach((el, i) => {
        // Stagger tiles for a nicer cascade
        if (el.classList.contains('ph-tile')) {
          el.style.transitionDelay = (i * 60) + 'ms';
        }
        const rect = el.getBoundingClientRect();
        if (rect.top < window.innerHeight && rect.bottom > 0) {
          el.classList.add('is-visible');
        } else {
          obs.observe(el);
        }
      });
    }

    // ── Sticky mini-nav ──
    function setupMiniNav() {
      const nav = document.querySelector('.ph-mini-nav');
      if (!nav) return;
      const hero = document.querySelector('.ph-hero');
      if (!hero) return;
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if (!e.isIntersecting) nav.classList.add('is-visible');
          else nav.classList.remove('is-visible');
        });
      }, { threshold: 0.05, rootMargin: '-80px 0px 0px 0px' });
      observer.observe(hero);
    }

    // ── Smooth scroll for in-page anchors ──
    function setupSmoothScroll() {
      document.querySelectorAll('a[href^="#ph-"]').forEach(a => {
        a.addEventListener('click', (e) => {
          const id = a.getAttribute('href').slice(1);
          const target = document.getElementById(id);
          if (target) {
            e.preventDefault();
            const top = target.getBoundingClientRect().top + window.scrollY - 80;
            window.scrollTo({ top, behavior: 'smooth' });
          }
        });
      });
    }

    // ── Filter Console ──
    function setupFilters() {
      const filters = Array.from(document.querySelectorAll('.ph-filter'));
      const resultEl = document.getElementById('ph-result');
      const photos = buildPhotoIndex();
      if (!filters.length) return;

      filters.forEach(btn => {
        btn.addEventListener('click', () => {
          filters.forEach(f => f.classList.remove('is-on'));
          btn.classList.add('is-on');
          applyFilter(btn.getAttribute('data-filter'), photos, resultEl);
        });
      });
    }
    function applyFilter(filter, photos, resultEl) {
      let visibleCount = 0;
      photos.forEach(photo => {
        const show = filter === 'all' || photo.tags.indexOf(filter) !== -1;
        if (show) {
          photo.el.classList.remove('is-hidden');
          visibleCount++;
        } else {
          photo.el.classList.add('is-hidden');
        }
      });
      if (resultEl) {
        const filterName = (filter === 'all') ? 'All' :
          (filter.charAt(0).toUpperCase() + filter.slice(1));
        const bVisible = document.createElement('b');
        bVisible.textContent = String(visibleCount);
        const bFilter = document.createElement('b');
        bFilter.textContent = filterName;
        resultEl.textContent = '';
        resultEl.appendChild(document.createTextNode('Showing '));
        resultEl.appendChild(bVisible);
        resultEl.appendChild(document.createTextNode(' ' + (visibleCount === 1 ? 'frame' : 'frames') + ' · filter: '));
        resultEl.appendChild(bFilter);
      }
    }

    // ── Lightbox ──
    function setupLightbox() {
      const photos = buildPhotoIndex();
      const lb = document.getElementById('ph-lightbox');
      const lbImg = document.getElementById('ph-lb-img');
      const lbCounter = document.getElementById('ph-lb-counter');
      const lbExif = document.getElementById('ph-lb-exif');
      const lbVenue = document.getElementById('ph-lb-venue');
      const lbType = document.getElementById('ph-lb-type');
      const lbStrip = document.getElementById('ph-lb-strip');
      const lbClose = document.getElementById('ph-lb-close');
      const lbPrev = document.getElementById('ph-lb-prev');
      const lbNext = document.getElementById('ph-lb-next');
      if (!lb || !lbImg) return;

      // Build the lightbox film strip
      // Safe: src comes from our own data attributes in the static HTML, not user input.
      photos.forEach((p, i) => {
        const item = document.createElement('button');
        item.className = 'ph-lightbox__strip-item';
        item.setAttribute('aria-label', 'Jump to photo ' + (i + 1));
        const img = document.createElement('img');
        img.src = p.src;
        img.alt = '';
        item.appendChild(img);
        item.addEventListener('click', () => show(i));
        lbStrip.appendChild(item);
      });
      const stripItems = Array.from(lbStrip.children);

      let current = 0;
      function show(idx) {
        if (idx < 0 || idx >= photos.length) return;
        const p = photos[idx];
        // Fade transition
        lbImg.classList.add('is-fading');
        setTimeout(() => {
          lbImg.src = p.src;
          lbImg.alt = p.venue;
          const bCounter = document.createElement('b');
          bCounter.textContent = String(idx + 1).padStart(2, '0');
          // Replace children: <b>NN</b> / <NN>
          lbCounter.textContent = '';
          lbCounter.appendChild(bCounter);
          lbCounter.appendChild(document.createTextNode(' / ' + String(photos.length).padStart(2, '0')));

          // exif — safe, from hardcoded data-exif attributes
          const exifIcon = document.createElement('i');
          exifIcon.className = 'fas fa-camera';
          lbExif.textContent = '';
          lbExif.appendChild(exifIcon);
          lbExif.appendChild(document.createTextNode(' ' + p.exif));
          lbVenue.textContent = p.venue;
          lbType.textContent = p.type;
          stripItems.forEach((s, i) => s.classList.toggle('is-on', i === idx));
          // Auto-scroll the strip to keep current visible
          if (stripItems[idx]) {
            stripItems[idx].scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'center' });
          }
          lbImg.classList.remove('is-fading');
        }, 200);
        current = idx;
      }
      function open(idx) {
        show(idx);
        lb.classList.add('is-on');
        document.body.style.overflow = 'hidden';
      }
      function close() {
        lb.classList.remove('is-on');
        document.body.style.overflow = '';
      }
      function next() { show((current + 1) % photos.length); }
      function prev() { show((current - 1 + photos.length) % photos.length); }

      // Tile click → open lightbox
      photos.forEach((p, i) => {
        p.el.addEventListener('click', (e) => {
          e.preventDefault();
          open(i);
        });
      });
      lbClose.addEventListener('click', close);
      lbNext.addEventListener('click', next);
      lbPrev.addEventListener('click', prev);
      // Click backdrop to close (but not the stage itself)
      lb.addEventListener('click', (e) => {
        if (e.target === lb) close();
      });
      // Keyboard nav
      document.addEventListener('keydown', (e) => {
        if (!lb.classList.contains('is-on')) return;
        if (e.key === 'Escape') close();
        if (e.key === 'ArrowRight') { e.preventDefault(); next(); }
        if (e.key === 'ArrowLeft')  { e.preventDefault(); prev(); }
      });
    }

    // ── Photo strip — clicking a thumbnail opens the lightbox ──
    function setupStrip() {
      const photos = buildPhotoIndex();
      const items = Array.from(document.querySelectorAll('.ph-strip-item'));
      items.forEach(item => {
        const target = parseInt(item.getAttribute('data-target'), 10);
        if (isNaN(target) || !photos[target]) return;
        item.addEventListener('click', (e) => {
          e.preventDefault();
          // Scroll to gallery, then open lightbox
          const gallery = document.getElementById('ph-mosaic');
          if (gallery) {
            const top = gallery.getBoundingClientRect().top + window.scrollY - 80;
            window.scrollTo({ top, behavior: 'smooth' });
          }
          setTimeout(() => {
            // Trigger a click on the corresponding tile
            photos[target].el.click();
          }, 400);
        });
      });
    }

    // ── Init ──
    function init() {
      setupReveal();
      setupMiniNav();
      setupFilters();
      setupLightbox();
      setupStrip();
      setupSmoothScroll();
      // Safety net
      setTimeout(function() {
        document.querySelectorAll('.ph-reveal:not(.is-visible), .ph-tile:not(.is-visible)').forEach(function(el) {
          el.classList.add('is-visible');
        });
      }, 1500);
    }
    if (document.readyState === 'loading') {
      document.addEventListener('DOMContentLoaded', init);
    } else {
      init();
    }
  })();
</script>
