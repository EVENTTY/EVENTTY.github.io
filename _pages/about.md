---
title: "About Eventty"
permalink: /about/
classes: about-page
---

<style>
  /* ════════════════════════════════════════════════════════════
     ABOUT PAGE — full facelift
     Mirrors the home page's motion language: spinning background,
     animated equalizer, count-up stats, hover micro-interactions,
     scroll-reveal, sticky mini-nav. All styles are scoped to .ap-*
     and live only on this page.
     ════════════════════════════════════════════════════════════ */

  /* ── Layout fix: kill theme's "About Eventty" h1 + side padding ── */
  body.about-page .page__title { display: none !important; }
  body.about-page h1#page-title { display: none !important; }
  body.about-page .page__hero { display: none !important; }
  body.about-page .page__hero--overlay { display: none !important; }
  body.about-page .initial-content { padding-top: 0 !important; margin-top: 0 !important; }
  body.about-page .page { width: 100% !important; padding-right: 0 !important; }
  body.about-page .page__inner-wrap { width: 100% !important; max-width: 100% !important; }
  body.about-page .page__content { width: 100% !important; max-width: 100% !important; padding: 0 !important; }
  body.about-page .archive { width: 100% !important; max-width: 100% !important; padding: 0 !important; margin: 0 !important; }
  body.about-page #main { max-width: 100% !important; padding: 0 !important; }

  /* ── Sticky mini-nav that appears after the hero ── */
  .ap-mini-nav {
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
  .ap-mini-nav.is-visible { transform: translateY(0); }
  .ap-mini-nav a {
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s var(--ease-out-expo);
    position: relative;
  }
  .ap-mini-nav a::after {
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
  .ap-mini-nav a:hover { color: #04a9ff; }
  .ap-mini-nav a:hover::after { transform: scaleX(1); }

  /* ── HERO ── */
  .ap-hero {
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
  .ap-hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/images/about.jpg");
    background-size: cover;
    background-position: center 40%;
    opacity: 0.30;
    filter: grayscale(35%) saturate(0.85) contrast(1.05);
    pointer-events: none;
    z-index: 0;
    animation: apHeroSpin 180s linear infinite;
  }
  .ap-hero::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 70% 60% at 50% 50%, transparent 0%, rgba(10, 10, 15, 0.45) 60%, var(--bg-primary) 95%),
      linear-gradient(180deg, var(--bg-primary) 0%, transparent 12%, transparent 88%, var(--bg-primary) 100%);
    pointer-events: none;
    z-index: 1;
  }
  @keyframes apHeroSpin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
  }

  .ap-hero__inner {
    position: relative;
    z-index: 2;
    text-align: center;
    max-width: 880px;
    margin: 0 auto;
  }

  .ap-eyebrow {
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
  .ap-eyebrow__dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #04a9ff;
    box-shadow: 0 0 8px rgba(4, 169, 255, 0.6);
  }

  .ap-hero h1 {
    font-size: clamp(2.4rem, 6vw, 4.8rem);
    font-weight: 600;
    letter-spacing: -0.04em;
    line-height: 1.04;
    margin: 0 0 1.5rem;
    color: var(--text-primary);
  }
  .ap-hero h1 .gold {
    background: linear-gradient(135deg, #33bbff 0%, #04a9ff 50%, #0090dd 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-style: italic;
    font-weight: 500;
  }

  .ap-hero__sub {
    font-size: clamp(1.05rem, 1.4vw, 1.2rem);
    color: rgba(242, 242, 245, 0.65);
    line-height: 1.65;
    max-width: 600px;
    margin: 0 auto 2.5rem;
  }

  .ap-hero__ctas {
    display: flex;
    gap: 0.75rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 3.5rem;
  }

  .ap-btn {
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
  .ap-btn--primary {
    background: #04a9ff;
    color: #0a0a0f !important;
  }
  .ap-btn--primary:hover {
    background: #33bbff;
    transform: translateY(-1px);
    box-shadow: 0 8px 24px rgba(4, 169, 255, 0.25);
  }
  .ap-btn--ghost {
    background: rgba(255, 255, 255, 0.04);
    color: var(--text-primary) !important;
    border-color: rgba(255, 255, 255, 0.12);
  }
  .ap-btn--ghost:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(255, 255, 255, 0.22);
    transform: translateY(-1px);
  }
  .ap-btn__arrow { transition: transform 0.2s var(--ease-out-expo); }
  .ap-btn:hover .ap-btn__arrow { transform: translateX(3px); }

  /* Scroll cue + equalizer (mirrors home) */
  .ap-scroll-cue {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: var(--text-muted);
    font-size: 0.7rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
  }
  .ap-scroll-cue__line {
    width: 1px;
    height: 36px;
    background: linear-gradient(180deg, rgba(4, 169, 255, 0.6), transparent);
    position: relative;
    overflow: hidden;
  }
  .ap-scroll-cue__line::after {
    content: "";
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 8px;
    background: #04a9ff;
    animation: apScrollDot 2s ease-in-out infinite;
  }
  @keyframes apScrollDot {
    0% { transform: translateY(-100%); opacity: 0; }
    30% { opacity: 1; }
    100% { transform: translateY(360%); opacity: 0; }
  }
  .ap-eq {
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
  .ap-eq span {
    display: block;
    width: 3px;
    background: linear-gradient(180deg, transparent, #04a9ff 30%, #04a9ff 70%, transparent);
    border-radius: 2px;
    animation: apEqBar 1.4s ease-in-out infinite;
  }
  .ap-eq span:nth-child(1)  { height: 12px; animation-delay: 0.0s; }
  .ap-eq span:nth-child(2)  { height: 20px; animation-delay: 0.15s; }
  .ap-eq span:nth-child(3)  { height: 8px;  animation-delay: 0.3s; }
  .ap-eq span:nth-child(4)  { height: 24px; animation-delay: 0.1s; }
  .ap-eq span:nth-child(5)  { height: 14px; animation-delay: 0.45s; }
  .ap-eq span:nth-child(6)  { height: 18px; animation-delay: 0.25s; }
  .ap-eq span:nth-child(7)  { height: 26px; animation-delay: 0.05s; }
  .ap-eq span:nth-child(8)  { height: 10px; animation-delay: 0.4s; }
  .ap-eq span:nth-child(9)  { height: 22px; animation-delay: 0.2s; }
  .ap-eq span:nth-child(10) { height: 16px; animation-delay: 0.35s; }
  .ap-eq span:nth-child(11) { height: 8px;  animation-delay: 0.5s; }
  .ap-eq span:nth-child(12) { height: 20px; animation-delay: 0.1s; }
  .ap-eq span:nth-child(13) { height: 14px; animation-delay: 0.3s; }
  .ap-eq span:nth-child(14) { height: 24px; animation-delay: 0.2s; }
  .ap-eq span:nth-child(15) { height: 12px; animation-delay: 0.4s; }
  @keyframes apEqBar {
    0%, 100% { transform: scaleY(0.4); }
    50%      { transform: scaleY(1.6); }
  }

  /* ════════════════════════════════════════════════════════════
     FREQUENCY SCULPTURE — pure visual widget
     A 96-bar animated waveform that breathes and reacts to
     mouse position. No stats, no copy to read — just art.
     Replaces the carousel; gives the page a "wow" pause moment.
     ════════════════════════════════════════════════════════════ */


  /* ── SECTION SHELL ── */
  .ap-section {
    padding: 7rem 1.5rem;
    max-width: var(--content-width);
    margin: 0 auto;
  }
  .ap-head {
    text-align: center;
    max-width: 680px;
    margin: 0 auto 3.5rem;
  }
  .ap-head__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .ap-head__title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .ap-head__sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  /* Divider line between sections */
  .ap-divider {
    max-width: var(--content-width);
    margin: 0 auto;
    padding: 0 1.5rem;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border-subtle), transparent);
  }

  /* ── CAPABILITY STRIP with shimmer + count badge ── */
  .ap-cap-row {
    max-width: 880px;
    margin: 0 auto 5rem;
    padding: 0 1.5rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 0.6rem;
  }
  .ap-cap {
    position: relative;
    display: inline-flex;
    align-items: center;
    gap: 0.55rem;
    padding: 0.7rem 1.1rem 0.7rem 0.95rem;
    background: var(--bg-glass);
    border: 1px solid rgba(4, 169, 255, 0.12);
    border-radius: 100px;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--text-secondary);
    letter-spacing: -0.01em;
    overflow: hidden;
    transition: all 0.25s var(--ease-out-expo);
    cursor: default;
  }
  /* Shimmer sweep on hover */
  .ap-cap::before {
    content: "";
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(4, 169, 255, 0.12), transparent);
    transition: left 0.5s var(--ease-out-expo);
  }
  .ap-cap::after {
    content: "";
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
    transition: width 0.3s var(--ease-out-expo);
  }
  .ap-cap i { color: #04a9ff; font-size: 0.95rem; flex-shrink: 0; }
  .ap-cap:hover {
    background: var(--bg-glass-hover);
    border-color: rgba(4, 169, 255, 0.3);
    color: var(--text-primary);
    transform: translateY(-2px);
    box-shadow: 0 4px 16px rgba(4, 169, 255, 0.1);
  }
  .ap-cap:hover::before { left: 100%; }
  .ap-cap:hover::after { width: 70%; }

  /* ── LOGO WALL with hover-revealed venue name ── */
  .ap-logos {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1rem;
    max-width: 960px;
    margin: 0 auto 5rem;
    padding: 0 1.5rem;
  }
  .ap-logo {
    position: relative;
    aspect-ratio: 1 / 1;
    background:
      radial-gradient(ellipse 70% 50% at 50% 50%, rgba(4, 169, 255, 0.05), transparent 70%),
      rgba(255, 255, 255, 0.025);
    border: 1px solid rgba(4, 169, 255, 0.10);
    border-radius: var(--radius-md);
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.25rem;
    transition: all 0.3s var(--ease-out-expo);
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.04) inset, 0 4px 12px rgba(0, 0, 0, 0.2);
    cursor: default;
  }
  .ap-logo::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent 15%, rgba(4, 169, 255, 0.4) 50%, transparent 85%);
  }
  .ap-logo__img-wrap {
    position: relative;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.4s var(--ease-out-expo), filter 0.4s var(--ease-out-expo), opacity 0.4s var(--ease-out-expo);
  }
  .ap-logo__img-wrap img {
    max-width: 78%;
    max-height: 78%;
    object-fit: contain;
    filter: grayscale(100%) brightness(1.0);
    opacity: 0.85;
  }
  .ap-logo__cap {
    position: absolute;
    inset: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    background: rgba(10, 10, 15, 0.85);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    opacity: 0;
    transform: scale(0.95);
    transition: all 0.3s var(--ease-out-expo);
    padding: 1rem;
  }
  .ap-logo__cap-name {
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin-bottom: 0.25rem;
  }
  .ap-logo__cap-meta {
    font-size: 0.68rem;
    font-weight: 500;
    color: rgba(4, 169, 255, 0.8);
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }
  .ap-logo:hover {
    transform: translateY(-3px);
    border-color: rgba(4, 169, 255, 0.4);
    background:
      radial-gradient(ellipse 70% 50% at 50% 50%, rgba(4, 169, 255, 0.12), transparent 70%),
      rgba(255, 255, 255, 0.05);
    box-shadow:
      0 0 0 1px rgba(4, 169, 255, 0.25),
      0 12px 30px rgba(0, 0, 0, 0.4),
      0 0 40px rgba(4, 169, 255, 0.1);
  }
  .ap-logo:hover .ap-logo__img-wrap {
    transform: scale(0.92);
    filter: blur(2px) grayscale(100%) brightness(0.6);
    opacity: 0.4;
  }
  .ap-logo:hover .ap-logo__cap {
    opacity: 1;
    transform: scale(1);
  }

  /* Stagger reveal for logo tiles */
  .ap-logo:nth-child(1)  { transition-delay: 0.0s; }
  .ap-logo:nth-child(2)  { transition-delay: 0.04s; }
  .ap-logo:nth-child(3)  { transition-delay: 0.08s; }
  .ap-logo:nth-child(4)  { transition-delay: 0.12s; }
  .ap-logo:nth-child(5)  { transition-delay: 0.16s; }
  .ap-logo:nth-child(6)  { transition-delay: 0.20s; }
  .ap-logo:nth-child(7)  { transition-delay: 0.24s; }
  .ap-logo:nth-child(8)  { transition-delay: 0.28s; }
  .ap-logo:nth-child(9)  { transition-delay: 0.32s; }
  .ap-logo:nth-child(10) { transition-delay: 0.36s; }
  .ap-logo:nth-child(11) { transition-delay: 0.40s; }
  .ap-logo:nth-child(12) { transition-delay: 0.44s; }

  /* ── ARTIST TILES with parallax hover + play button ── */
  .ap-artists {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    max-width: 720px;
    margin: 0 auto 5rem;
    padding: 0 1.5rem;
  }
  .ap-artist {
    position: relative;
    background:
      radial-gradient(ellipse 70% 50% at 50% 0%, rgba(4, 169, 255, 0.05), transparent 70%),
      rgba(255, 255, 255, 0.025);
    border: 1px solid rgba(4, 169, 255, 0.10);
    border-radius: var(--radius-md);
    overflow: hidden;
    transition: all 0.3s var(--ease-out-expo);
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.04) inset, 0 4px 12px rgba(0, 0, 0, 0.2);
    display: flex;
    flex-direction: column;
    cursor: default;
  }
  .ap-artist::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent 15%, rgba(4, 169, 255, 0.4) 50%, transparent 85%);
    z-index: 3;
  }
  .ap-artist__img-wrap {
    position: relative;
    aspect-ratio: 4 / 3;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1.25rem;
  }
  .ap-artist__img-wrap::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 50% 50%, transparent 60%, rgba(0, 0, 0, 0.4) 100%),
      linear-gradient(180deg, transparent 60%, rgba(0, 0, 0, 0.3) 100%);
    pointer-events: none;
  }
  .ap-artist img {
    width: 82%;
    height: 82%;
    object-fit: cover;
    object-position: center;
    border-radius: 4px;
    filter: grayscale(100%) brightness(1.0) contrast(0.95);
    opacity: 0.85;
    transition: all 0.5s var(--ease-out-expo);
    position: relative;
    z-index: 1;
  }
  .ap-artist__cap {
    position: relative;
    z-index: 1;
    padding: 0.85rem 1rem 1rem;
    border-top: 1px solid rgba(4, 169, 255, 0.10);
    background: rgba(10, 10, 15, 0.4);
    text-align: left;
  }
  .ap-artist__name {
    display: block;
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin-bottom: 0.15rem;
  }
  .ap-artist__meta {
    display: block;
    font-size: 0.7rem;
    font-weight: 500;
    color: rgba(4, 169, 255, 0.7);
    letter-spacing: 0.04em;
  }
  .ap-artist:hover {
    transform: translateY(-4px);
    border-color: rgba(4, 169, 255, 0.4);
    background:
      radial-gradient(ellipse 70% 50% at 50% 0%, rgba(4, 169, 255, 0.10), transparent 70%),
      rgba(255, 255, 255, 0.05);
    box-shadow:
      0 0 0 1px rgba(4, 169, 255, 0.25),
      0 16px 40px rgba(0, 0, 0, 0.4),
      0 0 40px rgba(4, 169, 255, 0.1);
  }
  .ap-artist:hover img {
    filter: grayscale(0%) brightness(1) contrast(1);
    opacity: 1;
    transform: scale(1.08);
  }

  /* ── "WHY EVENTTY" feature cards (hover lift + glow) ── */
  .ap-features {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
    max-width: 960px;
    margin: 0 auto 5rem;
    padding: 0 1.5rem;
  }
  .ap-feature {
    position: relative;
    background:
      radial-gradient(ellipse 70% 50% at 50% 0%, rgba(4, 169, 255, 0.06), transparent 70%),
      var(--bg-glass);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-lg);
    padding: 2.25rem 1.75rem;
    transition: all 0.3s var(--ease-out-expo);
    overflow: hidden;
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.03) inset, 0 4px 12px rgba(0, 0, 0, 0.2);
  }
  .ap-feature::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.10), transparent);
  }
  .ap-feature::after {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 0; height: 2px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
    transition: width 0.35s var(--ease-out-expo);
  }
  .ap-feature:hover {
    transform: translateY(-5px);
    border-color: rgba(4, 169, 255, 0.25);
    background:
      radial-gradient(ellipse 70% 50% at 50% 0%, rgba(4, 169, 255, 0.12), transparent 70%),
      var(--bg-glass-hover);
    box-shadow:
      0 1px 0 rgba(255, 255, 255, 0.05) inset,
      0 20px 50px rgba(0, 0, 0, 0.4),
      0 4px 20px rgba(4, 169, 255, 0.08);
  }
  .ap-feature:hover::after { width: 60%; }
  .ap-feature__icon {
    width: 52px;
    height: 52px;
    border-radius: 14px;
    background: rgba(4, 169, 255, 0.1);
    border: 1px solid rgba(4, 169, 255, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #04a9ff;
    font-size: 1.3rem;
    margin-bottom: 1.5rem;
    transition: all 0.3s var(--ease-out-expo);
  }
  .ap-feature:hover .ap-feature__icon {
    background: rgba(4, 169, 255, 0.2);
    transform: scale(1.08) rotate(-5deg);
  }
  .ap-feature h4 {
    font-size: 1.1rem;
    font-weight: 600;
    letter-spacing: -0.02em;
    color: var(--text-primary);
    margin: 0 0 0.6rem;
  }
  .ap-feature p {
    font-size: 0.9rem;
    line-height: 1.6;
    color: var(--text-secondary);
    margin: 0 0 1rem;
  }
  .ap-feature__more {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    font-size: 0.75rem;
    font-weight: 600;
    color: rgba(4, 169, 255, 0.7);
    letter-spacing: 0.06em;
    text-transform: uppercase;
    transition: all 0.2s var(--ease-out-expo);
  }
  .ap-feature__more i { font-size: 0.7rem; transition: transform 0.2s var(--ease-out-expo); }
  .ap-feature:hover .ap-feature__more { color: #04a9ff; }
  .ap-feature:hover .ap-feature__more i { transform: translateX(3px); }

  /* ── FINAL CTA (mirrors home) ── */
  .ap-cta {
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
  .ap-cta::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 200px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .ap-cta__eq {
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
  .ap-cta__eq span {
    display: block;
    width: 2px;
    background: #04a9ff;
    border-radius: 1px;
    animation: apEqBar 1.6s ease-in-out infinite;
  }
  .ap-cta__eq span:nth-child(1)  { height: 8px;  animation-delay: 0.0s; }
  .ap-cta__eq span:nth-child(2)  { height: 14px; animation-delay: 0.2s; }
  .ap-cta__eq span:nth-child(3)  { height: 6px;  animation-delay: 0.4s; }
  .ap-cta__eq span:nth-child(4)  { height: 16px; animation-delay: 0.1s; }
  .ap-cta__eq span:nth-child(5)  { height: 10px; animation-delay: 0.3s; }
  .ap-cta__eq span:nth-child(6)  { height: 18px; animation-delay: 0.15s; }
  .ap-cta__eq span:nth-child(7)  { height: 8px;  animation-delay: 0.35s; }
  .ap-cta__eq span:nth-child(8)  { height: 12px; animation-delay: 0.05s; }
  .ap-cta__eq span:nth-child(9)  { height: 6px;  animation-delay: 0.25s; }
  .ap-cta__eq span:nth-child(10) { height: 14px; animation-delay: 0.45s; }
  .ap-cta h2 {
    position: relative;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .ap-cta p {
    position: relative;
    font-size: 1.05rem;
    color: var(--text-secondary);
    line-height: 1.65;
    max-width: 520px;
    margin: 0 auto 2rem;
  }
  .ap-cta .ap-btn { position: relative; }
  .ap-cta__note {
    position: relative;
    display: block;
    margin-top: 1.25rem;
    font-size: 0.8rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }

  /* ── Scroll reveal ── */
  .ap-reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease-out, transform 0.7s ease-out;
  }
  .ap-reveal.is-visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .ap-logos { grid-template-columns: repeat(3, 1fr); }
    .ap-artists, .ap-features { grid-template-columns: 1fr; }
    .ap-mini-nav { gap: 1rem; font-size: 0.7rem; }
  }
  @media (max-width: 600px) {
    .ap-hero { padding: 7rem 1rem 5rem; min-height: auto; }
    .ap-logos { grid-template-columns: repeat(2, 1fr); }
    .ap-cap-row { gap: 0.5rem; }
    .ap-cap { font-size: 0.8rem; padding: 0.6rem 0.95rem; }
  }
  @media (max-width: 380px) {
    .ap-logos { grid-template-columns: 1fr; }
  }
</style>

<!-- ═══ STICKY MINI-NAV (appears after hero scrolls past) ═══ -->
<nav class="ap-mini-nav" aria-label="Page sections">
  <a href="#ap-capabilities">Capabilities</a>
  <a href="#ap-trusted">Trusted by</a>
  <a href="#ap-artists">Artists</a>
  <a href="#ap-why">Why Eventty</a>
  <a href="#ap-cta">Get in touch</a>
</nav>

<!-- ═══ HERO ═══ -->
<section class="ap-hero">
  <div class="ap-hero__inner">
    <div class="ap-eyebrow ap-reveal">
      <span class="ap-eyebrow__dot"></span>
      About
    </div>
    <h1 class="ap-reveal">
      A decade behind<br><span class="gold">the music.</span>
    </h1>
    <div class="ap-hero__ctas ap-reveal">
      <a href="/" class="ap-btn ap-btn--primary">
        Home
        <span class="ap-btn__arrow">→</span>
      </a>
      <a href="/services/" class="ap-btn ap-btn--ghost">
        Services
      </a>
    </div>
    <div class="ap-scroll-cue ap-reveal" aria-hidden="true">
      <span>Scroll</span>
      <span class="ap-scroll-cue__line"></span>
    </div>
  </div>
  <div class="ap-eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
</section>



<!-- ═══ CAPABILITIES ═══ -->
<div class="ap-head ap-reveal" id="ap-capabilities" style="margin-top: 6rem;">
  <div class="ap-head__eyebrow">What you get</div>
  <h2 class="ap-head__title">Everything you need.</h2>
  <p class="ap-head__sub">Sound, lighting, wireless mic, full insurance and backup gear.</p>
</div>

<div class="ap-cap-row">
  <span class="ap-cap ap-reveal"><i class="fas fa-sliders-h"></i> Curated setlists</span>
  <span class="ap-cap ap-reveal"><i class="fas fa-microphone"></i> Pro-grade PA</span>
  <span class="ap-cap ap-reveal"><i class="fas fa-lightbulb"></i> Lighting rig</span>
  <span class="ap-cap ap-reveal"><i class="fas fa-headphones"></i> Wireless mic</span>
  <span class="ap-cap ap-reveal"><i class="fas fa-shield-alt"></i> Full insurance</span>
  <span class="ap-cap ap-reveal"><i class="fas fa-plug"></i> Backup gear</span>
</div>

<div class="ap-divider" style="margin-top: 5rem;"></div>

<!-- ═══ WHY EVENTTY — three feature cards ═══ -->
<div class="ap-head ap-reveal" id="ap-why" style="margin-top: 5rem;">
  <div class="ap-head__eyebrow">Why Eventty</div>
  <h2 class="ap-head__title">Built around the room.</h2>
</div>

<div class="ap-features">
  <div class="ap-feature ap-reveal">
    <div class="ap-feature__icon"><i class="fas fa-headphones"></i></div>
    <h4>Read the room.</h4>
    <p>Pre-event brief. Music adapted in real time.</p>
    
  </div>
  <div class="ap-feature ap-reveal">
    <div class="ap-feature__icon"><i class="fas fa-volume-up"></i></div>
    <h4>Professional gear.</h4>
    <p>Pro-grade sound and lighting.</p>
    
  </div>
  <div class="ap-feature ap-reveal">
    <div class="ap-feature__icon"><i class="fas fa-handshake"></i></div>
    <h4>Show up and deliver.</h4>
    <p>On time, insured, no surprises.</p>
    
  </div>
</div>

<div class="ap-divider" style="margin-top: 5rem;"></div>

<!-- ═══ TRUSTED BY — 4-column grid, 12 tiles with hover-reveal caps ═══ -->
<div class="ap-head ap-reveal" id="ap-trusted" style="margin-top: 5rem;">
  <div class="ap-head__eyebrow">Trusted by</div>
  <h2 class="ap-head__title">Brands and Venues</h2>
</div>

<div class="ap-logos">
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="/images/terrigal-beach-house.png" alt="Terrigal Beach House"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Terrigal Beach House</div>
      <div class="ap-logo__cap-meta">Beachfront venue</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://images.squarespace-cdn.com/content/v1/68f0356b07218143351eb035/ec64e6f7-8b66-4edc-afd9-091a3d20f340/Main+Logo+Transparent.png?format=2500w" alt="Woodport Hotel"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Woodport Hotel</div>
      <div class="ap-logo__cap-meta">Pub &amp; dining</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="/images/terrigal-hotel.png" alt="Terrigal Hotel"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Terrigal Hotel</div>
      <div class="ap-logo__cap-meta">Live entertainment</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://www.bateaubayhotel.com.au/images/BBH-Logo-Green.avif" alt="Bateau Bay Hotel"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Bateau Bay Hotel</div>
      <div class="ap-logo__cap-meta">Dining &amp; events</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://cdn.prod.website-files.com/60efb8fbbca80e2406e63ea5/60f52101e304a23e7c54c097_SIRENS-LOGO-HORIZONTAL-SML-GOLD.svg" alt="Sirens The Nightclub"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Sirens The Nightclub</div>
      <div class="ap-logo__cap-meta">RNB &amp; EDM nights</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://mumbojumbos.com.au/wp-content/uploads/2019/12/Mumbo-Jumbos-logo.svg" alt="Mumbo Jumbos"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Mumbo Jumbos</div>
      <div class="ap-logo__cap-meta">Caribbean rooftop bar</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://mcprod2.yd.com.au/media/og_image/websites/19/opengraph-logo.jpeg" alt="yd. Australia"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">yd. Australia</div>
      <div class="ap-logo__cap-meta">Retail fashion</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="/images/2.jpg" alt="Anytime Fitness"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Anytime Fitness</div>
      <div class="ap-logo__cap-meta">24/7 gym partner</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="/images/clipnclimb.png" alt="Clip 'N Climb Central Coast"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Clip 'N Climb Central Coast</div>
      <div class="ap-logo__cap-meta">Indoor climbing venue</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://sydneymumsonthecentralcoast.com.au/wp-content/uploads/2019/06/Narara-Valley-High-School-300x300.png" alt="Narara Valley High School"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Narara Valley High School</div>
      <div class="ap-logo__cap-meta">School events &amp; formals</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="/images/5.jpg" alt="St Joseph's &amp; St Edward's"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">St Joseph's &amp; St Edward's</div>
      <div class="ap-logo__cap-meta">Catholic colleges</div>
    </div>
  </div>
  <div class="ap-logo">
    <div class="ap-logo__img-wrap"><img src="https://tmcricket.com/wp-content/uploads/tmcc-80-years-logo-2.png" alt="Terrigal Matcham Cricket Club"></div>
    <div class="ap-logo__cap">
      <div class="ap-logo__cap-name">Terrigal Matcham Cricket Club</div>
      <div class="ap-logo__cap-meta">The Bellbirds</div>
    </div>
  </div>
</div>

<div class="ap-divider" style="margin-top: 5rem;"></div>

<!-- ═══ ALSO SUPPORTING — 3 artist tiles ═══ -->
<div class="ap-head ap-reveal" id="ap-artists" style="margin-top: 5rem;">
  <div class="ap-head__eyebrow">Supporting</div>
  <h2 class="ap-head__title reveal">International artists:</h2>
</div>

<div class="ap-artists">
  <div class="ap-artist ap-reveal">
    <div class="ap-artist__img-wrap">
      <img src="/images/7.jpg" alt="International touring DJ act">
    </div>
    <div class="ap-artist__cap">
      <span class="ap-artist__name">Jason Derulo</span>
      <span class="ap-artist__meta">Pop · Hip Hop · R&amp;B</span>
    </div>
  </div>
  <div class="ap-artist ap-reveal">
    <div class="ap-artist__img-wrap">
      <img src="/images/8.png" alt="Australian electronic music performer">
    </div>
    <div class="ap-artist__cap">
      <span class="ap-artist__name">IYAZ</span>
      <span class="ap-artist__meta">Pop · R&amp;B · Reggae</span>
    </div>
  </div>
  <div class="ap-artist ap-reveal">
    <div class="ap-artist__img-wrap">
      <img src="/images/9.jpg" alt="Headline music act at Central Coast events">
    </div>
    <div class="ap-artist__cap">
      <span class="ap-artist__name">Gorillaz</span>
      <span class="ap-artist__meta">DJ Set · Ivy Sydney</span>
    </div>
  </div>
</div>

<div class="ap-divider" style="margin-top: 5rem;"></div>

<!-- ═══ FINAL CTA ═══ -->
<section class="ap-cta ap-reveal" id="ap-cta">
  <div class="ap-cta__eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
  <h2>Music that fits.</h2>
  <a href="/contact/" class="ap-btn ap-btn--primary">
    Discuss
    <span class="ap-btn__arrow">→</span>
  </a>
  <span class="ap-cta__note">Free consultation · Replies within 24 hours</span>
</section>

<script>
  (function() {
    // ── Reveal on scroll ──
    function setupReveal() {
      const els = document.querySelectorAll('.ap-reveal');
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

    // ── Sticky mini-nav (appears after hero) ──
    function setupMiniNav() {
      const nav = document.querySelector('.ap-mini-nav');
      if (!nav) return;
      const hero = document.querySelector('.ap-hero');
      if (!hero) return;
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          // When hero is NOT intersecting (i.e., we've scrolled past it), show the nav
          if (!e.isIntersecting) {
            nav.classList.add('is-visible');
          } else {
            nav.classList.remove('is-visible');
          }
        });
      }, { threshold: 0.05, rootMargin: '-80px 0px 0px 0px' });
      observer.observe(hero);
    }

    // ── Smooth scroll for in-page anchors ──
    function setupSmoothScroll() {
      document.querySelectorAll('a[href^="#ap-"]').forEach(a => {
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

    // ── Init ──
    function init() {
      setupReveal();
      setupMiniNav();
      setupSmoothScroll();
      // Safety net: if anything is still hidden after 1.5s (slow scroll, screenshot tools,
      // reduced-motion, edge cases), force-reveal it. Prevents "invisible content" bugs.
      setTimeout(function() {
        document.querySelectorAll('.ap-reveal:not(.is-visible)').forEach(function(el) {
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
