---
title: "Services"
permalink: /services/
classes: services-page
---

<style>
  /* ════════════════════════════════════════════════════════════
     SERVICES PAGE — full facelift
     Serves a different purpose from home + about. Home proves
     busy/trusted. About proves personality. Services proves
     deliverables: gear, packages, genres, inclusions, pricing.
     Same motion language, completely new visual widgets.
     ════════════════════════════════════════════════════════════ */

  /* ── Layout fix: kill theme's page title + side padding ── */
  body.services-page .page__title { display: none !important; }
  body.services-page h1#page-title { display: none !important; }
  body.services-page .page__hero { display: none !important; }
  body.services-page .page__hero--overlay { display: none !important; }
  body.services-page .initial-content { padding-top: 0 !important; margin-top: 0 !important; }
  body.services-page .page { width: 100% !important; padding-right: 0 !important; }
  body.services-page .page__inner-wrap { width: 100% !important; max-width: 100% !important; }
  body.services-page .page__content { width: 100% !important; max-width: 100% !important; padding: 0 !important; }
  body.services-page .archive { width: 100% !important; max-width: 100% !important; padding: 0 !important; margin: 0 !important; }
  body.services-page #main { max-width: 100% !important; padding: 0 !important; }

  /* ── Sticky mini-nav (appears after hero scrolls past) ── */
  .sv-mini-nav {
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
    gap: 2rem;
    transform: translateY(-100%);
    transition: transform 0.4s var(--ease-out-expo);
    font-size: 0.78rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
  }
  .sv-mini-nav.is-visible { transform: translateY(0); }
  .sv-mini-nav a {
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s var(--ease-out-expo);
    position: relative;
  }
  .sv-mini-nav a::after {
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
  .sv-mini-nav a:hover { color: #04a9ff; }
  .sv-mini-nav a:hover::after { transform: scaleX(1); }

  /* ── HERO ── */
  .sv-hero {
    position: relative;
    min-height: calc(100vh - 80px);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 9rem 1.5rem 7rem;
    overflow: hidden;
    background:
      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(4, 169, 255, 0.14), transparent 70%),
      radial-gradient(ellipse 60% 50% at 80% 100%, rgba(4, 169, 255, 0.06), transparent 70%),
      var(--bg-primary);
  }
  .sv-hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/images/services.png");
    background-size: cover;
    background-position: center;
    opacity: 0.28;
    filter: grayscale(30%) saturate(0.85) contrast(1.05);
    pointer-events: none;
    z-index: 0;
    animation: svHeroSpin 220s linear infinite;
  }
  .sv-hero::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 70% 60% at 50% 50%, transparent 0%, rgba(10, 10, 15, 0.45) 60%, var(--bg-primary) 95%),
      linear-gradient(180deg, var(--bg-primary) 0%, transparent 12%, transparent 88%, var(--bg-primary) 100%);
    pointer-events: none;
    z-index: 1;
  }
  @keyframes svHeroSpin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
  }

  .sv-hero__inner {
    position: relative;
    z-index: 2;
    text-align: center;
    max-width: 880px;
    margin: 0 auto;
  }

  .sv-eyebrow {
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
  .sv-eyebrow__dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #04a9ff;
    box-shadow: 0 0 8px rgba(4, 169, 255, 0.6);
  }

  .sv-hero h1 {
    font-size: clamp(2.4rem, 6vw, 4.8rem);
    font-weight: 600;
    letter-spacing: -0.04em;
    line-height: 1.04;
    margin: 0 0 1.5rem;
    color: var(--text-primary);
  }
  .sv-hero h1 .gold {
    background: linear-gradient(135deg, #33bbff 0%, #04a9ff 50%, #0090dd 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-style: italic;
    font-weight: 500;
  }

  .sv-hero__sub {
    font-size: clamp(1.05rem, 1.4vw, 1.2rem);
    color: rgba(242, 242, 245, 0.65);
    line-height: 1.65;
    max-width: 600px;
    margin: 0 auto 2.5rem;
  }

  .sv-hero__ctas {
    display: flex;
    gap: 0.75rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 3.5rem;
  }

  .sv-btn {
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
  .sv-btn--primary {
    background: #04a9ff;
    color: #0a0a0f !important;
  }
  .sv-btn--primary:hover {
    background: #33bbff;
    transform: translateY(-1px);
    box-shadow: 0 8px 24px rgba(4, 169, 255, 0.25);
  }
  .sv-btn--ghost {
    background: rgba(255, 255, 255, 0.04);
    color: var(--text-primary) !important;
    border-color: rgba(255, 255, 255, 0.12);
  }
  .sv-btn--ghost:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(255, 255, 255, 0.22);
    transform: translateY(-1px);
  }
  .sv-btn__arrow { transition: transform 0.2s var(--ease-out-expo); }
  .sv-btn:hover .sv-btn__arrow { transform: translateX(3px); }

  /* Scroll cue + equalizer (mirrors home) */
  .sv-scroll-cue {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: var(--text-muted);
    font-size: 0.7rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
  }
  .sv-scroll-cue__line {
    width: 1px;
    height: 36px;
    background: linear-gradient(180deg, rgba(4, 169, 255, 0.6), transparent);
    position: relative;
    overflow: hidden;
  }
  .sv-scroll-cue__line::after {
    content: "";
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 8px;
    background: #04a9ff;
    animation: svScrollDot 2s ease-in-out infinite;
  }
  @keyframes svScrollDot {
    0% { transform: translateY(-100%); opacity: 0; }
    30% { opacity: 1; }
    100% { transform: translateY(360%); opacity: 0; }
  }
  .sv-eq {
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
  .sv-eq span {
    display: block;
    width: 3px;
    background: linear-gradient(180deg, transparent, #04a9ff 30%, #04a9ff 70%, transparent);
    border-radius: 2px;
    animation: svEqBar 1.4s ease-in-out infinite;
  }
  .sv-eq span:nth-child(1)  { height: 12px; animation-delay: 0.0s; }
  .sv-eq span:nth-child(2)  { height: 20px; animation-delay: 0.15s; }
  .sv-eq span:nth-child(3)  { height: 8px;  animation-delay: 0.3s; }
  .sv-eq span:nth-child(4)  { height: 24px; animation-delay: 0.1s; }
  .sv-eq span:nth-child(5)  { height: 14px; animation-delay: 0.45s; }
  .sv-eq span:nth-child(6)  { height: 18px; animation-delay: 0.25s; }
  .sv-eq span:nth-child(7)  { height: 26px; animation-delay: 0.05s; }
  .sv-eq span:nth-child(8)  { height: 10px; animation-delay: 0.4s; }
  .sv-eq span:nth-child(9)  { height: 22px; animation-delay: 0.2s; }
  .sv-eq span:nth-child(10) { height: 16px; animation-delay: 0.35s; }
  .sv-eq span:nth-child(11) { height: 8px;  animation-delay: 0.5s; }
  .sv-eq span:nth-child(12) { height: 20px; animation-delay: 0.1s; }
  .sv-eq span:nth-child(13) { height: 14px; animation-delay: 0.3s; }
  .sv-eq span:nth-child(14) { height: 24px; animation-delay: 0.2s; }
  .sv-eq span:nth-child(15) { height: 12px; animation-delay: 0.4s; }
  @keyframes svEqBar {
    0%, 100% { transform: scaleY(0.4); }
    50%      { transform: scaleY(1.6); }
  }

  /* ════════════════════════════════════════════════════════════
     GEAR RACK — the headline widget of the services page
     Styled like physical rack-mounted studio gear. Each unit has
     a power LED, model name, status indicator, and a glowing edge
     on hover. Visually completely unlike the home/about cards.
     ════════════════════════════════════════════════════════════ */
  .sv-rack {
    padding: 6rem 1.5rem 5rem;
    background:
      linear-gradient(180deg, var(--bg-secondary) 0%, var(--bg-primary) 100%);
    position: relative;
  }
  .sv-rack::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .sv-rack__head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3rem;
  }
  .sv-rack__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .sv-rack__title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .sv-rack__sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  .sv-rack__rail {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.25rem;
  }

  .sv-unit {
    position: relative;
    background: linear-gradient(180deg, #1a1a22 0%, #14141a 100%);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-md);
    padding: 1.5rem 1.5rem 1.25rem;
    overflow: hidden;
    transition: all 0.3s var(--ease-out-expo);
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.04),
      inset 0 -1px 0 rgba(0, 0, 0, 0.4),
      0 4px 14px rgba(0, 0, 0, 0.3);
  }
  /* Brushed-metal top strip */
  .sv-unit::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 24px;
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.03) 0%, transparent 100%);
    border-bottom: 1px solid rgba(0, 0, 0, 0.3);
    pointer-events: none;
  }
  /* Rack-screw corners */
  .sv-unit::after {
    content: "";
    position: absolute;
    top: 6px; right: 6px;
    width: 6px; height: 6px;
    border-radius: 50%;
    background: rgba(0, 0, 0, 0.4);
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.08),
      0 0 0 1px rgba(255, 255, 255, 0.03);
  }

  .sv-unit__top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 1.25rem;
    position: relative;
    z-index: 1;
  }
  .sv-unit__brand {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.66rem;
    font-weight: 700;
    letter-spacing: 0.22em;
    color: #04a9ff;
    padding: 0.3rem 0.65rem;
    background: linear-gradient(135deg, rgba(4, 169, 255, 0.18) 0%, rgba(4, 169, 255, 0.08) 100%);
    border: 1px solid rgba(4, 169, 255, 0.4);
    border-radius: 3px;
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.04);
  }
  .sv-unit__led {
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }
  .sv-unit__led .led {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: #04a9ff;
    box-shadow: 0 0 6px rgba(4, 169, 255, 0.7), inset 0 0 2px rgba(255, 255, 255, 0.3);
    animation: svLedPulse 2.4s ease-in-out infinite;
  }
  .sv-unit__led .led--green { background: #4ade80; box-shadow: 0 0 6px rgba(74, 222, 128, 0.7), inset 0 0 2px rgba(255, 255, 255, 0.3); }
  .sv-unit__led .led--blue  { background: #60a5fa; box-shadow: 0 0 6px rgba(96, 165, 250, 0.7), inset 0 0 2px rgba(255, 255, 255, 0.3); }
  /* Tiny label under the LEDs */
  .sv-unit__led-label {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.55rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    color: var(--text-muted);
    text-transform: uppercase;
  }
  @keyframes svLedPulse {
    0%, 100% { opacity: 1; }
    50%      { opacity: 0.45; }
  }
  .sv-unit__model {
    font-size: 0.95rem;
    font-weight: 600;
    letter-spacing: -0.01em;
    color: var(--text-primary);
    margin: 0 0 0.25rem;
    position: relative;
    z-index: 1;
  }
  .sv-unit__type {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.65rem;
    letter-spacing: 0.14em;
    color: var(--text-muted);
    text-transform: uppercase;
    margin: 0 0 1rem;
    position: relative;
    z-index: 1;
  }
  .sv-unit__desc {
    font-size: 0.85rem;
    line-height: 1.6;
    color: var(--text-secondary);
    margin: 0 0 1.25rem;
    position: relative;
    z-index: 1;
  }

  /* Bottom-row specs — knob/dial aesthetic */
  .sv-unit__specs {
    display: flex;
    gap: 0.6rem;
    padding-top: 0.85rem;
    border-top: 1px solid rgba(255, 255, 255, 0.04);
    position: relative;
    z-index: 1;
  }
  .sv-unit__knob {
    flex: 1;
    text-align: center;
    padding: 0.45rem 0.4rem 0.4rem;
    background: rgba(0, 0, 0, 0.25);
    border-radius: 4px;
    border: 1px solid rgba(255, 255, 255, 0.04);
  }
  .sv-unit__knob-val {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.7rem;
    font-weight: 700;
    color: #04a9ff;
    letter-spacing: 0.04em;
    line-height: 1;
  }
  .sv-unit__knob-lbl {
    font-size: 0.58rem;
    font-weight: 600;
    letter-spacing: 0.12em;
    color: var(--text-muted);
    text-transform: uppercase;
    margin-top: 0.3rem;
  }

  .sv-unit:hover {
    transform: translateY(-4px);
    border-color: rgba(4, 169, 255, 0.3);
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.06),
      inset 0 -1px 0 rgba(0, 0, 0, 0.4),
      0 12px 30px rgba(0, 0, 0, 0.5),
      0 0 30px rgba(4, 169, 255, 0.08);
  }

  /* ════════════════════════════════════════════════════════════
     GENRE SPECTRUM — interactive visualizer
     A horizontal "spectrum bar" with 16 genre dots positioned
     along it by energy/tempo. Hover or click a dot to highlight
     that genre. Visually a 3D-feel slider control.
     Completely unique widget — not on home or about.
     ════════════════════════════════════════════════════════════ */
  .sv-spectrum {
    padding: 7rem 1.5rem 6rem;
    background:
      radial-gradient(ellipse 80% 50% at 50% 30%, rgba(4, 169, 255, 0.06), transparent 70%),
      var(--bg-primary);
    position: relative;
  }
  .sv-spectrum::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .sv-spectrum__head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3.5rem;
  }
  .sv-spectrum__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .sv-spectrum__title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .sv-spectrum__sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  .sv-spectrum__panel {
    max-width: 1100px;
    margin: 0 auto;
    padding: 2.5rem 2rem 1.5rem;
    background:
      radial-gradient(ellipse 60% 50% at 50% 0%, rgba(4, 169, 255, 0.06), transparent 70%),
      linear-gradient(180deg, #14141a 0%, #0e0e14 100%);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-lg);
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.04),
      0 16px 50px rgba(0, 0, 0, 0.4);
  }

  /* The horizontal axis — "lounge" to "peak" */
  .sv-spectrum__axis {
    position: relative;
    height: 220px;
    display: flex;
    align-items: center;
    margin: 0 0.5rem 1.5rem;
  }
  .sv-spectrum__track {
    position: absolute;
    left: 0; right: 0;
    top: 50%;
    height: 1px;
    background: linear-gradient(90deg,
      rgba(4, 169, 255, 0.1) 0%,
      rgba(4, 169, 255, 0.4) 50%,
      rgba(4, 169, 255, 0.1) 100%);
    transform: translateY(-50%);
  }
  /* Tick marks every 10% */
  .sv-spectrum__track::before {
    content: "";
    position: absolute;
    inset: -8px 0;
    background-image: repeating-linear-gradient(90deg,
      transparent 0,
      transparent 9.6%,
      rgba(4, 169, 255, 0.15) 9.6%,
      rgba(4, 169, 255, 0.15) 10%);
  }
  .sv-spectrum__axis-lbl {
    position: absolute;
    bottom: -1.5rem;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.62rem;
    letter-spacing: 0.18em;
    color: var(--text-muted);
    text-transform: uppercase;
  }
  .sv-spectrum__axis-lbl--l { left: 0; }
  .sv-spectrum__axis-lbl--r { right: 0; }

  /* Genre dots */
  .sv-genre-dot {
    position: absolute;
    top: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    cursor: pointer;
    transition: all 0.3s var(--ease-out-expo);
    z-index: 1;
  }
  .sv-genre-dot__pip {
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background: var(--bg-primary);
    border: 2px solid rgba(4, 169, 255, 0.5);
    transition: all 0.3s var(--ease-out-expo);
    position: relative;
  }
  .sv-genre-dot__pip::after {
    content: "";
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    border: 1px solid transparent;
    transition: all 0.3s var(--ease-out-expo);
  }
  .sv-genre-dot__name {
    position: absolute;
    top: 22px;
    font-size: 0.7rem;
    font-weight: 600;
    color: var(--text-muted);
    letter-spacing: 0.04em;
    white-space: nowrap;
    transition: color 0.2s var(--ease-out-expo);
    pointer-events: none;
  }
  .sv-genre-dot:hover .sv-genre-dot__pip,
  .sv-genre-dot.is-on .sv-genre-dot__pip {
    background: #04a9ff;
    border-color: #04a9ff;
    box-shadow: 0 0 16px rgba(4, 169, 255, 0.6);
    transform: scale(1.4);
  }
  .sv-genre-dot:hover .sv-genre-dot__pip::after,
  .sv-genre-dot.is-on .sv-genre-dot__pip::after {
    border-color: rgba(4, 169, 255, 0.4);
    transform: scale(1.3);
  }
  .sv-genre-dot:hover .sv-genre-dot__name,
  .sv-genre-dot.is-on .sv-genre-dot__name {
    color: #04a9ff;
  }
  /* Vertical labels — alternate above/below the line */
  .sv-genre-dot--alt .sv-genre-dot__name {
    top: auto;
    bottom: 22px;
  }

  /* Genre detail readout below the spectrum */
  .sv-spectrum__readout {
    text-align: center;
    min-height: 72px;
    margin-top: 1.5rem;
    padding: 1rem 1.5rem;
    border-top: 1px solid rgba(255, 255, 255, 0.05);
  }
  .sv-spectrum__readout-name {
    font-size: 1.05rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin: 0 0 0.4rem;
    transition: color 0.2s var(--ease-out-expo);
  }
  .sv-spectrum__readout-desc {
    font-size: 0.88rem;
    color: var(--text-secondary);
    line-height: 1.55;
    margin: 0;
    max-width: 720px;
    margin-left: auto;
    margin-right: auto;
  }
  .sv-spectrum__readout.is-on .sv-spectrum__readout-name { color: #04a9ff; }
  .sv-spectrum__readout.is-dim .sv-spectrum__readout-name { color: var(--text-muted); opacity: 0.5; }

  /* Pulse markers along the track — "energy" indicators */
  .sv-spectrum__pulse {
    position: absolute;
    top: 50%;
    width: 2px;
    height: 32px;
    background: linear-gradient(180deg, transparent, #04a9ff, transparent);
    transform: translate(-50%, -50%);
    opacity: 0.4;
    pointer-events: none;
    animation: svSpectrumPulse 2s ease-in-out infinite;
  }
  @keyframes svSpectrumPulse {
    0%, 100% { opacity: 0.2; }
    50%      { opacity: 0.6; }
  }

  /* ════════════════════════════════════════════════════════════
     PACKAGES — three tiers, with featured middle
     ════════════════════════════════════════════════════════════ */
  .sv-packages {
    padding: 6rem 1.5rem 5rem;
    background:
      linear-gradient(180deg, var(--bg-primary) 0%, var(--bg-secondary) 100%);
    position: relative;
  }
  .sv-packages::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .sv-packages__head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3.5rem;
  }
  .sv-packages__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .sv-packages__title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .sv-packages__sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  .sv-packages__grid {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.25rem;
    align-items: stretch;
  }

  .sv-pkg {
    position: relative;
    background: var(--bg-glass);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-lg);
    padding: 2.5rem 1.75rem 2rem;
    display: flex;
    flex-direction: column;
    transition: all 0.3s var(--ease-out-expo);
    overflow: hidden;
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.03) inset, 0 4px 16px rgba(0, 0, 0, 0.2);
  }
  .sv-pkg::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent 20%, rgba(255, 255, 255, 0.10) 50%, transparent 80%);
  }
  .sv-pkg__tier {
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin: 0 0 0.5rem;
  }
  .sv-pkg__name {
    font-size: 1.4rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.02em;
    margin: 0 0 0.5rem;
  }
  .sv-pkg__from {
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
    margin: 0 0 0.25rem;
  }
  .sv-pkg__price {
    font-size: 2.2rem;
    font-weight: 600;
    color: #04a9ff;
    letter-spacing: -0.03em;
    line-height: 1;
    margin: 0 0 0.25rem;
    font-variant-numeric: tabular-nums;
  }
  .sv-pkg__unit {
    font-size: 0.7rem;
    color: var(--text-muted);
    letter-spacing: 0.06em;
    text-transform: uppercase;
    margin: 0 0 1.5rem;
  }

  .sv-pkg__list {
    list-style: none;
    padding: 0;
    margin: 0 0 1.75rem;
    flex: 1;
  }
  .sv-pkg__list li {
    display: flex;
    align-items: flex-start;
    gap: 0.6rem;
    padding: 0.55rem 0;
    font-size: 0.85rem;
    color: var(--text-secondary);
    line-height: 1.5;
    border-bottom: 1px solid rgba(255, 255, 255, 0.04);
  }
  .sv-pkg__list li:last-child { border-bottom: none; }
  .sv-pkg__list li::before {
    content: "✓";
    color: #04a9ff;
    font-weight: 700;
    flex-shrink: 0;
    margin-top: 1px;
  }
  .sv-pkg__list li.is-muted { color: var(--text-muted); opacity: 0.6; }
  .sv-pkg__list li.is-muted::before { content: "—"; color: var(--text-muted); opacity: 0.5; }

  .sv-pkg__cta {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    padding: 0.85rem 1.25rem;
    border-radius: var(--radius-sm);
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.10);
    color: var(--text-primary) !important;
    font-weight: 600;
    font-size: 0.88rem;
    text-decoration: none !important;
    letter-spacing: -0.01em;
    transition: all 0.2s var(--ease-out-expo);
  }
  .sv-pkg__cta:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(4, 169, 255, 0.4);
    color: #04a9ff !important;
  }

  /* Featured package — the popular choice */
  .sv-pkg--featured {
    background:
      radial-gradient(ellipse 80% 50% at 50% 0%, rgba(4, 169, 255, 0.12), transparent 70%),
      var(--bg-glass-hover);
    border-color: rgba(4, 169, 255, 0.4);
    transform: scale(1.03);
    box-shadow:
      0 1px 0 rgba(255, 255, 255, 0.05) inset,
      0 20px 50px rgba(0, 0, 0, 0.4),
      0 0 40px rgba(4, 169, 255, 0.1);
  }
  .sv-pkg--featured::before {
    background: linear-gradient(90deg, transparent 10%, rgba(4, 169, 255, 0.6) 50%, transparent 90%);
  }
  .sv-pkg__ribbon {
    position: absolute;
    top: 1.25rem; right: -1px;
    background: #04a9ff;
    color: #0a0a0f;
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    padding: 0.35rem 0.7rem;
    border-radius: 4px 0 0 4px;
  }
  .sv-pkg--featured .sv-pkg__cta {
    background: #04a9ff;
    border-color: #04a9ff;
    color: #0a0a0f !important;
  }
  .sv-pkg--featured .sv-pkg__cta:hover {
    background: #33bbff;
    border-color: #33bbff;
    color: #0a0a0f !important;
  }

  .sv-pkg:hover {
    transform: translateY(-3px);
    border-color: rgba(4, 169, 255, 0.25);
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.05) inset, 0 12px 30px rgba(0, 0, 0, 0.4);
  }
  .sv-pkg--featured:hover { transform: scale(1.03) translateY(-3px); }

  /* ════════════════════════════════════════════════════════════
     INCLUSIONS — two-column "always" + "on request"
     ════════════════════════════════════════════════════════════ */
  .sv-incl {
    padding: 6rem 1.5rem 5rem;
    background: var(--bg-primary);
    position: relative;
  }
  .sv-incl::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .sv-incl__head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3rem;
  }
  .sv-incl__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .sv-incl__title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .sv-incl__sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  .sv-incl__grid {
    max-width: 1000px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.25rem;
  }
  .sv-incl-col {
    background: var(--bg-glass);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-lg);
    padding: 2rem 1.75rem 1.5rem;
  }
  .sv-incl-col__head {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    margin-bottom: 1.25rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  }
  .sv-incl-col__icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    background: rgba(4, 169, 255, 0.1);
    border: 1px solid rgba(4, 169, 255, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #04a9ff;
    font-size: 0.85rem;
  }
  .sv-incl-col__title {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin: 0;
  }
  .sv-incl-col__sub {
    font-size: 0.7rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
    margin-left: auto;
  }
  .sv-incl-col__list {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  .sv-incl-col__list li {
    display: flex;
    align-items: flex-start;
    gap: 0.7rem;
    padding: 0.6rem 0;
    font-size: 0.9rem;
    color: var(--text-secondary);
    line-height: 1.5;
    border-bottom: 1px solid rgba(255, 255, 255, 0.04);
    opacity: 0;
    transform: translateX(-12px);
    transition: opacity 0.4s ease-out, transform 0.4s ease-out;
  }
  .sv-incl-col__list li:last-child { border-bottom: none; }
  .sv-incl-col__list.is-on li { opacity: 1; transform: translateX(0); }
  .sv-incl-col__list li::before {
    content: "✓";
    color: #04a9ff;
    font-weight: 700;
    flex-shrink: 0;
    margin-top: 1px;
  }
  .sv-incl-col--on-req .sv-incl-col__list li::before { content: "+"; color: rgba(4, 169, 255, 0.7); }

  /* ════════════════════════════════════════════════════════════
     FINAL CTA
     ════════════════════════════════════════════════════════════ */
  .sv-cta {
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
  .sv-cta::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 200px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .sv-cta__eq {
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
  .sv-cta__eq span {
    display: block;
    width: 2px;
    background: #04a9ff;
    border-radius: 1px;
    animation: svEqBar 1.6s ease-in-out infinite;
  }
  .sv-cta__eq span:nth-child(1)  { height: 8px;  animation-delay: 0.0s; }
  .sv-cta__eq span:nth-child(2)  { height: 14px; animation-delay: 0.2s; }
  .sv-cta__eq span:nth-child(3)  { height: 6px;  animation-delay: 0.4s; }
  .sv-cta__eq span:nth-child(4)  { height: 16px; animation-delay: 0.1s; }
  .sv-cta__eq span:nth-child(5)  { height: 10px; animation-delay: 0.3s; }
  .sv-cta__eq span:nth-child(6)  { height: 18px; animation-delay: 0.15s; }
  .sv-cta__eq span:nth-child(7)  { height: 8px;  animation-delay: 0.35s; }
  .sv-cta__eq span:nth-child(8)  { height: 12px; animation-delay: 0.05s; }
  .sv-cta__eq span:nth-child(9)  { height: 6px;  animation-delay: 0.25s; }
  .sv-cta__eq span:nth-child(10) { height: 14px; animation-delay: 0.45s; }
  .sv-cta h2 {
    position: relative;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .sv-cta p {
    position: relative;
    font-size: 1.05rem;
    color: var(--text-secondary);
    line-height: 1.65;
    max-width: 520px;
    margin: 0 auto 2rem;
  }
  .sv-cta .sv-btn { position: relative; }
  .sv-cta__note {
    position: relative;
    display: block;
    margin-top: 1.25rem;
    font-size: 0.8rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }

  /* Section head helper (reused) */
  .sv-head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3rem;
  }
  .sv-head__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .sv-head__title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .sv-head__sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  /* ── Scroll reveal ── */
  .sv-reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease-out, transform 0.7s ease-out;
  }
  .sv-reveal.is-visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .sv-rack__rail { grid-template-columns: 1fr 1fr; }
    .sv-rack__rail > .sv-unit:nth-child(3) { grid-column: span 2; }
    .sv-packages__grid { grid-template-columns: 1fr; max-width: 480px; }
    .sv-pkg--featured { transform: scale(1); }
    .sv-pkg--featured:hover { transform: translateY(-3px); }
    .sv-incl__grid { grid-template-columns: 1fr; }
    .sv-mini-nav { gap: 1rem; font-size: 0.7rem; }
    .sv-spectrum__panel { padding: 2rem 1rem; }
  }
  @media (max-width: 600px) {
    .sv-hero { padding: 7rem 1rem 5rem; min-height: auto; }
    .sv-rack { padding: 4rem 1rem; }
    .sv-rack__rail { grid-template-columns: 1fr; }
    .sv-rack__rail > .sv-unit:nth-child(3) { grid-column: auto; }
    .sv-spectrum { padding: 4rem 1rem; }
    .sv-spectrum__axis { height: 160px; }
    .sv-packages { padding: 4rem 1rem; }
    .sv-incl { padding: 4rem 1rem; }
    .sv-cta { padding: 3.5rem 1.5rem; }
  }
</style>

<!-- ═══ STICKY MINI-NAV ═══ -->
<nav class="sv-mini-nav" aria-label="Page sections">
  <a href="#sv-gear">Gear</a>
  <a href="#sv-spectrum">Genres</a>
  <a href="#sv-packages">Packages</a>
  <a href="#sv-incl">Inclusions</a>
  <a href="#sv-cta">Book</a>
</nav>

<!-- ═══ HERO ═══ -->
<section class="sv-hero">
  <div class="sv-hero__inner">
    <div class="sv-eyebrow sv-reveal">
      <span class="sv-eyebrow__dot"></span>
      Services
    </div>
    <h1 class="sv-reveal">
      Pick what fits, or <span class="gold">build something custom.</span>
    </h1>
    <div class="sv-hero__ctas sv-reveal">
      <a href="/about/" class="sv-btn sv-btn--primary">
        About
        <span class="sv-btn__arrow">→</span>
      </a>
      <a href="/photos/" class="sv-btn sv-btn--ghost">
        Photos
      </a>
    </div>
    <div class="sv-scroll-cue sv-reveal" aria-hidden="true">
      <span>Scroll</span>
      <span class="sv-scroll-cue__line"></span>
    </div>
  </div>
  <div class="sv-eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
</section>

<!-- ═══ THE GEAR RACK ═══ -->
<section class="sv-rack" id="sv-gear">
  <div class="sv-rack__head">
    <div class="sv-rack__eyebrow sv-reveal">Included</div>
    <h2 class="sv-rack__title sv-reveal">Equipment</h2>
    <p class="sv-rack__sub sv-reveal">Pro-grade, calibrated to your space with backup on-site.</p>
  </div>

  <div class="sv-rack__rail">
    <div class="sv-unit sv-reveal">
      <div class="sv-unit__top">
        <span class="sv-unit__brand">EVT-01</span>
        <span class="sv-unit__led">
          <span class="led led--green"></span>
          <span class="led led--green"></span>
          <span class="sv-unit__led-label">PWR · SIG</span>
        </span>
      </div>
      <h4 class="sv-unit__model">Pro PA System</h4>
      <div class="sv-unit__type">Main / fills / subs</div>
      <p class="sv-unit__desc">Calibrated to your room size and ceiling height. Fills a 300-cover venue; quiet enough for dinner conversation.</p>
      <div class="sv-unit__specs">
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">2× TOP</div>
          <div class="sv-unit__knob-lbl">Mains</div>
        </div>
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">2× SUB</div>
          <div class="sv-unit__knob-lbl">Low end</div>
        </div>
      </div>
    </div>

    <div class="sv-unit sv-reveal">
      <div class="sv-unit__top">
        <span class="sv-unit__brand">EVT-02</span>
        <span class="sv-unit__led">
          <span class="led led--green"></span>
          <span class="led"></span>
          <span class="sv-unit__led-label">DMX · LIVE</span>
        </span>
      </div>
      <h4 class="sv-unit__model">Lighting Rig</h4>
      <div class="sv-unit__type">Ambient + dancefloor</div>
      <p class="sv-unit__desc">Warm uplighting for dinner, full LED rig for peak hour. Pre-programmed scenes.</p>
      <div class="sv-unit__specs">
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">8× PAR</div>
          <div class="sv-unit__knob-lbl">Uplights</div>
        </div>
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">4× MOV</div>
          <div class="sv-unit__knob-lbl">Heads</div>
        </div>
      </div>
    </div>

    <div class="sv-unit sv-reveal">
      <div class="sv-unit__top">
        <span class="sv-unit__brand">EVT-03</span>
        <span class="sv-unit__led">
          <span class="led led--blue"></span>
          <span class="led led--green"></span>
          <span class="sv-unit__led-label">LINK · PWR</span>
        </span>
      </div>
      <h4 class="sv-unit__model">DJ Controller &amp; Mics</h4>
      <div class="sv-unit__type">Pioneer DDJ-1000 / Shure</div>
      <p class="sv-unit__desc">Industry-standard controller, two wireless mics, backup laptop on standby.</p>
      <div class="sv-unit__specs">
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">DDJ</div>
          <div class="sv-unit__knob-lbl">Controller</div>
        </div>
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">2× WL</div>
          <div class="sv-unit__knob-lbl">Mics</div>
        </div>
      </div>
    </div>

    <div class="sv-unit sv-reveal">
      <div class="sv-unit__top">
        <span class="sv-unit__brand">EVT-04</span>
        <span class="sv-unit__led">
          <span class="led led--green"></span>
          <span class="led"></span>
          <span class="led led--green"></span>
          <span class="sv-unit__led-label">DB · OK</span>
        </span>
      </div>
      <h4 class="sv-unit__model">15k+ Track Library</h4>
      <div class="sv-unit__type">Curated &amp; family-clean</div>
      <p class="sv-unit__desc">A growing catalogue spanning six decades. All tracks edited, no skips.</p>
      <div class="sv-unit__specs">
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">15K+</div>
          <div class="sv-unit__knob-lbl">Tracks</div>
        </div>
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">~6 DEC</div>
          <div class="sv-unit__knob-lbl">Eras</div>
        </div>
      </div>
    </div>

    <div class="sv-unit sv-reveal">
      <div class="sv-unit__top">
        <span class="sv-unit__brand">EVT-05</span>
        <span class="sv-unit__led">
          <span class="led led--green"></span>
          <span class="led led--green"></span>
          <span class="sv-unit__led-label">RDY · STBY</span>
        </span>
      </div>
      <h4 class="sv-unit__model">Backup Stack</h4>
      <div class="sv-unit__type">Every booking</div>
      <p class="sv-unit__desc">Complete backup of every critical piece. If anything fails, the show continues.</p>
      <div class="sv-unit__specs">
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">2nd LP</div>
          <div class="sv-unit__knob-lbl">Laptop</div>
        </div>
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">2nd RC</div>
          <div class="sv-unit__knob-lbl">Controller</div>
        </div>
      </div>
    </div>

    <div class="sv-unit sv-reveal">
      <div class="sv-unit__top">
        <span class="sv-unit__brand">EVT-06</span>
        <span class="sv-unit__led">
          <span class="led led--green"></span>
          <span class="led led--green"></span>
          <span class="sv-unit__led-label">CERT · OK</span>
        </span>
      </div>
      <h4 class="sv-unit__model">Insurance &amp; Compliance</h4>
      <div class="sv-unit__type">Public liability &amp; PI</div>
      <p class="sv-unit__desc">Full public liability and professional indemnity. Certificates available on request.</p>
      <div class="sv-unit__specs">
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">$20M</div>
          <div class="sv-unit__knob-lbl">Liability</div>
        </div>
        <div class="sv-unit__knob">
          <div class="sv-unit__knob-val">PI</div>
          <div class="sv-unit__knob-lbl">Indemnity</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ GENRE SPECTRUM — interactive widget ═══ -->
<section class="sv-spectrum" id="sv-spectrum">
  <div class="sv-spectrum__head">
    <div class="sv-spectrum__eyebrow sv-reveal">Genres</div>
    <h2 class="sv-spectrum__title sv-reveal">From lounge-warm to peak-hour dancefloor.</h2>
    <p class="sv-spectrum__sub sv-reveal">Hover or tap a dot to read the brief.</p>
  </div>

  <div class="sv-spectrum__panel sv-reveal">
    <div class="sv-spectrum__axis" id="sv-spectrum-axis">
      <div class="sv-spectrum__track"></div>
      <div class="sv-spectrum__pulse" style="left: 12%; animation-delay: 0s;"></div>
      <div class="sv-spectrum__pulse" style="left: 28%; animation-delay: 0.3s;"></div>
      <div class="sv-spectrum__pulse" style="left: 45%; animation-delay: 0.6s;"></div>
      <div class="sv-spectrum__pulse" style="left: 63%; animation-delay: 0.2s;"></div>
      <div class="sv-spectrum__pulse" style="left: 78%; animation-delay: 0.5s;"></div>
      <div class="sv-spectrum__pulse" style="left: 91%; animation-delay: 0.7s;"></div>

      <!-- Genre dots — left = lounge, right = peak. Positioned by tempo/energy. -->
      <button class="sv-genre-dot" data-genre="lounge" style="left: 8%;" aria-label="Lounge &amp; dinner"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Lounge</span></button>
      <button class="sv-genre-dot sv-genre-dot--alt" data-genre="soul" style="left: 18%;" aria-label="Soul &amp; Motown"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Soul</span></button>
      <button class="sv-genre-dot" data-genre="disco" style="left: 30%;" aria-label="Disco &amp; Funk"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Disco</span></button>
      <button class="sv-genre-dot sv-genre-dot--alt" data-genre="indie" style="left: 41%;" aria-label="Indie &amp; Alt"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Indie</span></button>
      <button class="sv-genre-dot" data-genre="house" style="left: 53%;" aria-label="House"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">House</span></button>
      <button class="sv-genre-dot sv-genre-dot--alt" data-genre="pop" style="left: 64%;" aria-label="Pop &amp; Top 40"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Pop</span></button>
      <button class="sv-genre-dot" data-genre="rnb" style="left: 73%;" aria-label="R&amp;B"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">R&amp;B</span></button>
      <button class="sv-genre-dot sv-genre-dot--alt" data-genre="hiphop" style="left: 81%;" aria-label="Hip Hop"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Hip Hop</span></button>
      <button class="sv-genre-dot" data-genre="latin" style="left: 89%;" aria-label="Latin"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Latin</span></button>
      <button class="sv-genre-dot sv-genre-dot--alt" data-genre="peak" style="left: 96%;" aria-label="Peak &amp; dancefloor"><span class="sv-genre-dot__pip"></span><span class="sv-genre-dot__name">Peak</span></button>

      <span class="sv-spectrum__axis-lbl sv-spectrum__axis-lbl--l">Lounge / dinner</span>
      <span class="sv-spectrum__axis-lbl sv-spectrum__axis-lbl--r">Peak / dancefloor</span>
    </div>

    <div class="sv-spectrum__readout" id="sv-spectrum-readout">
      <h3 class="sv-spectrum__readout-name" id="sv-spectrum-name">Tap a dot.</h3>
      <p class="sv-spectrum__readout-desc" id="sv-spectrum-desc">Select a genre to see what it sounds like in your venue.</p>
    </div>
  </div>
</section>

<!-- Genre metadata — JS reads this on hover/click -->
<script type="application/json" id="sv-genre-data">
{
  "lounge":  { "name": "Lounge & dinner",          "desc": "Acoustic and soft-electronica. Volume matched to conversation." },
  "soul":    { "name": "Soul & Motown",           "desc": "Al Green, Stevie, early Motown. Civilised rooms, warm energy." },
  "disco":   { "name": "Disco & funk",            "desc": "Salsoul, early disco, French touch, modern funk." },
  "indie":   { "name": "Indie & alt",             "desc": "Modern indie and alternative. Known songs, good energy." },
  "house":   { "name": "House",                       "desc": "Deep house, disco house, tech-lite. Steady and danceable." },
  "pop":     { "name": "Pop & Top 40",            "desc": "Current hits and party classics. Songs your guests know." },
  "rnb":     { "name": "R&B",                      "desc": "Old-school R&B, neo-soul, slow-burn ballads." },
  "hiphop":  { "name": "Hip Hop",                     "desc": "Old-school essentials, golden-era classics, modern hits. Clean edits." },
  "latin":   { "name": "Latin & reggaeton",       "desc": "Salsa, reggaeton, Brazilian. For venues that already lean Latin." },
  "peak":    { "name": "Peak & dancefloor",       "desc": "High-energy pop, house, throwbacks. The closing-hour set." }
}
</script>

<!-- ═══ PACKAGES ═══ -->
<section class="sv-packages" id="sv-packages">
  <div class="sv-packages__head">
    <div class="sv-packages__eyebrow sv-reveal">Packages</div>
    <h2 class="sv-packages__title sv-reveal">Pick the event that fits.</h2>
    <p class="sv-packages__sub sv-reveal">Or discuss a custom build.</p>
  </div>

  <div class="sv-packages__grid">
    <div class="sv-pkg sv-reveal">
      <div class="sv-pkg__tier">Tier 01</div>
      <h3 class="sv-pkg__name">Standard</h3>
      <ul class="sv-pkg__list">
        <li>DJ + full PA system</li>
        <li>Up to 100 guests</li>
        <li>Pre-event brief call</li>
        <li>Curated setlists</li>
        <li>Setup &amp; pack-down included</li>
        <li class="is-muted">No lighting rig</li>
        <li class="is-muted">No MC services</li>
      </ul>
      <a href="/contact/" class="sv-pkg__cta">Discuss <span>→</span></a>
    </div>

    <div class="sv-pkg sv-pkg--featured sv-reveal">
      <div class="sv-pkg__ribbon">Most booked</div>
      <div class="sv-pkg__tier">Tier 02</div>
      <h3 class="sv-pkg__name">Production</h3>
      <ul class="sv-pkg__list">
        <li>DJ + lighting rig</li>
        <li>Up to 250 guests</li>
        <li>Three setlists</li>
        <li>Wireless MC mic included</li>
        <li>Backup gear on-site</li>
        <li>Insurance certificate provided</li>
      </ul>
      <a href="/contact/" class="sv-pkg__cta">Discuss <span>→</span></a>
    </div>

    <div class="sv-pkg sv-reveal">
      <div class="sv-pkg__tier">Tier 03</div>
      <h3 class="sv-pkg__name">Full</h3>
      <ul class="sv-pkg__list">
        <li>Everything in Production, plus:</li>
        <li>Up to 800+ guests</li>
        <li>Extended line array</li>
        <li>Two-DJ handover</li>
        <li>Dedicated MC</li>
        <li>Pre-event venue liaison</li>
        <li>White-glove load-in &amp; pack-down</li>
      </ul>
      <a href="/contact/" class="sv-pkg__cta">Discuss <span>→</span></a>
    </div>
  </div>
</section>

<!-- ═══ INCLUSIONS — two columns ═══ -->
<section class="sv-incl" id="sv-incl">
  <div class="sv-incl__head">
    <div class="sv-incl__eyebrow sv-reveal">Inclusions</div>
    <h2 class="sv-incl__title sv-reveal">No upcharges, no surprises.</h2>
    <p class="sv-incl__sub sv-reveal">Every booking gets what's needed.</p>
  </div>

  <div class="sv-incl__grid">
    <div class="sv-incl-col sv-incl-col--always sv-reveal">
      <div class="sv-incl-col__head">
        <div class="sv-incl-col__icon"><i class="fas fa-check"></i></div>
        <h3 class="sv-incl-col__title">Always included</h3>
        <div class="sv-incl-col__sub">Every booking</div>
      </div>
      <ul class="sv-incl-col__list" id="sv-incl-always">
        <li>Free pre-event consultation</li>
        <li>Tailored setlist planning</li>
        <li>Professional PA system (mains + subs)</li>
        <li>Industry-standard DJ controller</li>
        <li>Two wireless microphones</li>
        <li>Pre-event venue briefing</li>
        <li>Setup &amp; sound-check (2hr before doors)</li>
        <li>Pack-down &amp; load-out</li>
        <li>Public liability insurance ($20M)</li>
        <li>Professional indemnity insurance</li>
        <li>Backup equipment on-site</li>
        <li>Family-friendly track library (15k+)</li>
        <li>Energy read-and-adjust throughout</li>
        <li>Post-event summary</li>
      </ul>
    </div>

    <div class="sv-incl-col sv-incl-col--on-req sv-reveal">
      <div class="sv-incl-col__head">
        <div class="sv-incl-col__icon"><i class="fas fa-plus"></i></div>
        <h3 class="sv-incl-col__title">On request</h3>
        <div class="sv-incl-col__sub">Add as needed</div>
      </div>
      <ul class="sv-incl-col__list" id="sv-incl-req">
        <li>Full LED dance lighting rig</li>
        <li>Uplighting package (8–16 fixtures)</li>
        <li>Moving head lights</li>
        <li>Smoke &amp; haze machine</li>
        <li>Dedicated MC for the night</li>
        <li>Second DJ (peak-time handover)</li>
        <li>Sub-rig &amp; extended line array</li>
        <li>Custom monogram / gobo projection</li>
        <li>Live event recording</li>
        <li>Same-day highlight reel</li>
        <li>Photographer add-on</li>
        <li>Extended hours (after 6hr)</li>
        <li>Multi-room coverage</li>
        <li>Festival / outdoor power add-on</li>
      </ul>
    </div>
  </div>
</section>

<!-- ═══ FINAL CTA ═══ -->
<section class="sv-cta sv-reveal" id="sv-cta">
  <div class="sv-cta__eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
  <h2>Build your event.</h2>
  <p>Tell us about the event. Tailored package and quote within 24 hours.</p>
  <a href="/contact/" class="sv-btn sv-btn--primary">
    Discuss
    <span class="sv-btn__arrow">→</span>
  </a>
  <span class="sv-cta__note">Free consultation · Custom quotes · No obligation</span>
</section>

<script>
  (function() {
    // ── Reveal on scroll ──
    function setupReveal() {
      const els = document.querySelectorAll('.sv-reveal');
      if (!('IntersectionObserver' in window) || !els.length) {
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
      }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });
      els.forEach(el => {
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
      const nav = document.querySelector('.sv-mini-nav');
      if (!nav) return;
      const hero = document.querySelector('.sv-hero');
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
      document.querySelectorAll('a[href^="#sv-"]').forEach(a => {
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

    // ── Genre Spectrum — interactive widget ──
    function setupGenreSpectrum() {
      const dots = Array.from(document.querySelectorAll('.sv-genre-dot'));
      const nameEl = document.getElementById('sv-spectrum-name');
      const descEl = document.getElementById('sv-spectrum-desc');
      const readout = document.getElementById('sv-spectrum-readout');
      if (!dots.length || !nameEl || !descEl) return;
      const dataNode = document.getElementById('sv-genre-data');
      if (!dataNode) return;
      let data = {};
      try { data = JSON.parse(dataNode.textContent); } catch (e) { return; }

      function clearAll() {
        dots.forEach(d => d.classList.remove('is-on'));
        readout.classList.remove('is-on', 'is-dim');
      }
      function setDefault() {
        clearAll();
        nameEl.textContent = 'Tap a dot.';
        descEl.textContent = 'Select a genre to see what it sounds like in your venue.';
      }
      dots.forEach(dot => {
        const key = dot.getAttribute('data-genre');
        const item = data[key];
        if (!item) return;
        function activate() {
          clearAll();
          dot.classList.add('is-on');
          readout.classList.add('is-on');
          nameEl.textContent = item.name;
          descEl.textContent = item.desc;
        }
        dot.addEventListener('mouseenter', activate);
        dot.addEventListener('focus', activate);
        dot.addEventListener('click', activate);
        dot.addEventListener('mouseleave', () => {
          // Only reset if no dot is active (i.e., user is just hovering, not pinned)
          if (!dots.some(d => d.classList.contains('is-on'))) setDefault();
        });
        dot.addEventListener('blur', setDefault);
      });
      // When user moves mouse away from the entire axis, reset
      const axis = document.getElementById('sv-spectrum-axis');
      if (axis) {
        axis.addEventListener('mouseleave', () => {
          if (!dots.some(d => d.classList.contains('is-on'))) setDefault();
        });
      }
    }

    // ── Inclusions — stagger reveal on scroll into view ──
    function setupInclusionsReveal() {
      const lists = document.querySelectorAll('.sv-incl-col__list');
      lists.forEach(list => {
        const items = Array.from(list.children);
        if (!items.length) return;
        // Set the initial transition delay per item
        items.forEach((li, i) => {
          li.style.transitionDelay = (i * 50) + 'ms';
        });
        // If list is already in viewport, reveal immediately
        const col = list.closest('.sv-incl-col');
        if (!col) return;
        const reveal = () => list.classList.add('is-on');
        const rect = col.getBoundingClientRect();
        if (rect.top < window.innerHeight && rect.bottom > 0) {
          reveal();
        } else if ('IntersectionObserver' in window) {
          const obs = new IntersectionObserver((entries) => {
            entries.forEach(e => {
              if (e.isIntersecting) {
                reveal();
                obs.unobserve(e.target);
              }
            });
          }, { threshold: 0.15 });
          obs.observe(col);
        } else {
          reveal();
        }
      });
    }

    // ── Init ──
    function init() {
      setupReveal();
      setupMiniNav();
      setupGenreSpectrum();
      setupInclusionsReveal();
      setupSmoothScroll();
      // Safety net: reveal anything still hidden after 1.5s (screenshot tools,
      // slow scroll, reduced-motion, edge cases)
      setTimeout(function() {
        document.querySelectorAll('.sv-reveal:not(.is-visible), .sv-incl-col__list:not(.is-on)').forEach(function(el) {
          el.classList.add('is-visible');
          el.classList.add('is-on');
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
