---
title: "Contact"
permalink: /contact/
classes: contact-page
---

<style>
  /* ════════════════════════════════════════════════════════════
     CONTACT PAGE — full facelift
     Serves a different purpose from every other page.
     Other pages sell, show, prove. This one STARTS A CONVERSATION
     through a multi-step brief that feels like a chat, not a form.
     ════════════════════════════════════════════════════════════ */

  /* ── Layout fix ── */
  body.contact-page .page__title { display: none !important; }
  body.contact-page h1#page-title { display: none !important; }
  body.contact-page .page__hero { display: none !important; }
  body.contact-page .page__hero--overlay { display: none !important; }
  body.contact-page .initial-content { padding-top: 0 !important; margin-top: 0 !important; }
  body.contact-page .page { width: 100% !important; padding-right: 0 !important; }
  body.contact-page .page__inner-wrap { width: 100% !important; max-width: 100% !important; }
  body.contact-page .page__content { width: 100% !important; max-width: 100% !important; padding: 0 !important; }
  body.contact-page .archive { width: 100% !important; max-width: 100% !important; padding: 0 !important; margin: 0 !important; }
  body.contact-page #main { max-width: 100% !important; padding: 0 !important; }

  /* ── Sticky mini-nav ── */
  .ct-mini-nav {
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
  .ct-mini-nav.is-visible { transform: translateY(0); }
  .ct-mini-nav a {
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s var(--ease-out-expo);
    position: relative;
  }
  .ct-mini-nav a::after {
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
  .ct-mini-nav a:hover { color: #04a9ff; }
  .ct-mini-nav a:hover::after { transform: scaleX(1); }

  /* ── HERO ── */
  .ct-hero {
    position: relative;
    min-height: 70vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 9rem 1.5rem 6rem;
    overflow: hidden;
    background:
      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(4, 169, 255, 0.14), transparent 70%),
      var(--bg-primary);
  }
  .ct-hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/images/2contact.jpg");
    background-size: cover;
    background-position: center;
    opacity: 0.28;
    filter: grayscale(30%) saturate(0.85) contrast(1.05);
    pointer-events: none;
    z-index: 0;
  }
  .ct-hero::after {
    content: "";
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 70% 60% at 50% 50%, transparent 0%, rgba(10, 10, 15, 0.45) 60%, var(--bg-primary) 95%),
      linear-gradient(180deg, var(--bg-primary) 0%, transparent 12%, transparent 88%, var(--bg-primary) 100%);
    pointer-events: none;
    z-index: 1;
  }
  .ct-hero__inner {
    position: relative;
    z-index: 2;
    text-align: center;
    max-width: 880px;
    margin: 0 auto;
  }
  .ct-eyebrow {
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
  .ct-eyebrow__dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #04a9ff;
    box-shadow: 0 0 8px rgba(4, 169, 255, 0.6);
  }
  .ct-hero h1 {
    font-size: clamp(2.4rem, 6vw, 4.8rem);
    font-weight: 600;
    letter-spacing: -0.04em;
    line-height: 1.04;
    margin: 0 0 1.5rem;
    color: var(--text-primary);
  }
  .ct-hero h1 .gold {
    background: linear-gradient(135deg, #33bbff 0%, #04a9ff 50%, #0090dd 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-style: italic;
    font-weight: 500;
  }
  .ct-hero__sub {
    font-size: clamp(1.05rem, 1.4vw, 1.2rem);
    color: rgba(242, 242, 245, 0.65);
    line-height: 1.65;
    max-width: 600px;
    margin: 0 auto 2.5rem;
  }
  .ct-hero__ctas {
    display: flex;
    gap: 0.75rem;
    justify-content: center;
    flex-wrap: wrap;
  }
  .ct-btn {
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
  .ct-btn--primary {
    background: #04a9ff;
    color: #0a0a0f !important;
  }
  .ct-btn--primary:hover {
    background: #33bbff;
    transform: translateY(-1px);
    box-shadow: 0 8px 24px rgba(4, 169, 255, 0.25);
  }
  .ct-btn--ghost {
    background: rgba(255, 255, 255, 0.04);
    color: var(--text-primary) !important;
    border-color: rgba(255, 255, 255, 0.12);
  }
  .ct-btn--ghost:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(255, 255, 255, 0.22);
    transform: translateY(-1px);
  }
  .ct-btn__arrow { transition: transform 0.2s var(--ease-out-expo); }
  .ct-btn:hover .ct-btn__arrow { transform: translateX(3px); }

  /* ════════════════════════════════════════════════════════════
     THE EVENT BRIEF — multi-step form
     Styled like a hardware control surface. 4 steps with
     progress bar, gold step circles, slide transitions.
     ════════════════════════════════════════════════════════════ */
  .ct-brief {
    padding: 5rem 1.5rem 6rem;
    background:
      linear-gradient(180deg, var(--bg-primary) 0%, var(--bg-secondary) 100%);
    position: relative;
  }
  .ct-brief::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }

  .ct-brief__panel {
    max-width: 760px;
    margin: 0 auto;
    background: linear-gradient(180deg, #14141a 0%, #0e0e14 100%);
    border: 1px solid rgba(4, 169, 255, 0.18);
    border-radius: var(--radius-lg);
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.04),
      0 16px 50px rgba(0, 0, 0, 0.4);
    overflow: hidden;
  }

  /* Panel header — device ID + step indicator */
  .ct-brief__head {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    padding: 1rem 1.5rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    background: rgba(0, 0, 0, 0.2);
  }
  .ct-brief__brand {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 0.22em;
    color: #04a9ff;
    padding: 0.3rem 0.6rem;
    background: linear-gradient(135deg, rgba(4, 169, 255, 0.18) 0%, rgba(4, 169, 255, 0.08) 100%);
    border: 1px solid rgba(4, 169, 255, 0.4);
    border-radius: 3px;
    flex-shrink: 0;
  }
  .ct-brief__title {
    font-size: 0.78rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: 0.06em;
    text-transform: uppercase;
    flex: 1;
  }
  .ct-brief__led {
    display: flex;
    align-items: center;
    gap: 0.4rem;
  }
  .ct-brief__led .led {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #4ade80;
    box-shadow: 0 0 6px rgba(74, 222, 128, 0.8), inset 0 0 2px rgba(255, 255, 255, 0.3);
    animation: ctLedPulse 2.4s ease-in-out infinite;
  }
  .ct-brief__led-lbl {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.55rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    color: var(--text-muted);
    text-transform: uppercase;
  }
  @keyframes ctLedPulse {
    0%, 100% { opacity: 1; }
    50%      { opacity: 0.45; }
  }

  /* Step indicator row */
  .ct-brief__steps {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2rem 2rem 1.5rem;
    gap: 0.5rem;
  }
  .ct-step {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    flex: 1;
  }
  .ct-step__num {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: var(--text-muted);
    font-size: 0.85rem;
    font-weight: 700;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    transition: all 0.3s var(--ease-out-expo);
  }
  .ct-step.is-on .ct-step__num {
    background: linear-gradient(135deg, #04a9ff, #0090dd);
    border-color: #04a9ff;
    color: #0a0a0f;
    box-shadow: 0 0 12px rgba(4, 169, 255, 0.4);
  }
  .ct-step.is-done .ct-step__num {
    background: rgba(4, 169, 255, 0.15);
    border-color: rgba(4, 169, 255, 0.5);
    color: #04a9ff;
  }
  .ct-step__label {
    font-size: 0.72rem;
    font-weight: 600;
    color: var(--text-muted);
    letter-spacing: 0.04em;
    text-transform: uppercase;
    transition: color 0.2s var(--ease-out-expo);
  }
  .ct-step.is-on .ct-step__label { color: var(--text-primary); }
  .ct-step__line {
    flex: 1;
    height: 1px;
    background: rgba(255, 255, 255, 0.08);
    margin: 0 0.4rem;
    position: relative;
    overflow: hidden;
  }
  .ct-step__line.is-done {
    background: linear-gradient(90deg, #04a9ff, #04a9ff);
  }

  /* Step content area */
  .ct-brief__body {
    padding: 1rem 2.5rem 0.5rem;
    min-height: 360px;
    position: relative;
    overflow: hidden;
  }
  .ct-step-panel {
    display: none;
  }
  .ct-step-panel.is-on {
    display: block;
    animation: ctStepIn 0.4s var(--ease-out-expo);
  }
  @keyframes ctStepIn {
    from { opacity: 0; transform: translateX(20px); }
    to   { opacity: 1; transform: translateX(0); }
  }
  .ct-step-panel h3 {
    font-size: 1.15rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin: 0 0 0.5rem;
  }
  .ct-step-panel p {
    font-size: 0.88rem;
    color: var(--text-secondary);
    line-height: 1.55;
    margin: 0 0 1.5rem;
  }

  /* Form fields */
  .ct-field {
    margin-bottom: 1.25rem;
  }
  .ct-field__label {
    display: block;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.14em;
    color: var(--text-muted);
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }
  .ct-field__input,
  .ct-field__textarea,
  .ct-field__select {
    display: block;
    width: 100%;
    padding: 0.85rem 1rem;
    background: rgba(10, 10, 15, 0.5);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: var(--radius-sm);
    color: var(--text-primary);
    font-family: var(--font-sans);
    font-size: 0.95rem;
    transition: all 0.2s var(--ease-out-expo);
    box-sizing: border-box;
  }
  .ct-field__input:focus,
  .ct-field__textarea:focus,
  .ct-field__select:focus {
    outline: none;
    border-color: #04a9ff;
    background: rgba(10, 10, 15, 0.7);
    box-shadow: 0 0 0 3px rgba(4, 169, 255, 0.1);
  }
  .ct-field__input::placeholder,
  .ct-field__textarea::placeholder {
    color: var(--text-muted);
    opacity: 0.7;
  }
  .ct-field__textarea {
    min-height: 100px;
    resize: vertical;
    line-height: 1.5;
  }
  .ct-field__select {
    appearance: none;
    background-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='10' height='6' viewBox='0 0 10 6'><path fill='%2304a9ff' d='M0 0l5 6 5-6z'/></svg>");
    background-repeat: no-repeat;
    background-position: right 1rem center;
    padding-right: 2.5rem;
    cursor: pointer;
  }
  .ct-field__row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  /* Chip-style multi-select for "vibe" step */
  .ct-chips {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }
  .ct-chip {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.55rem 1rem;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 100px;
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--text-secondary);
    cursor: pointer;
    transition: all 0.2s var(--ease-out-expo);
    user-select: none;
  }
  .ct-chip i {
    color: var(--text-muted);
    font-size: 0.8rem;
    transition: color 0.2s var(--ease-out-expo);
  }
  .ct-chip:hover {
    background: rgba(255, 255, 255, 0.05);
    border-color: rgba(4, 169, 255, 0.3);
    color: var(--text-primary);
  }
  .ct-chip:hover i { color: #04a9ff; }
  .ct-chip.is-on {
    background: linear-gradient(135deg, rgba(4, 169, 255, 0.18) 0%, rgba(4, 169, 255, 0.06) 100%);
    border-color: rgba(4, 169, 255, 0.5);
    color: #04a9ff;
    box-shadow: 0 0 12px rgba(4, 169, 255, 0.15);
  }
  .ct-chip.is-on i { color: #04a9ff; }

  /* Step navigation footer */
  .ct-brief__foot {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.5rem 2.5rem 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.05);
    background: rgba(0, 0, 0, 0.2);
  }
  .ct-brief__back {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.7rem 1.25rem;
    background: transparent;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: var(--radius-sm);
    color: var(--text-muted);
    font-family: var(--font-sans);
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s var(--ease-out-expo);
  }
  .ct-brief__back:hover {
    color: var(--text-primary);
    border-color: rgba(255, 255, 255, 0.15);
  }
  .ct-brief__back[disabled] { opacity: 0.3; cursor: not-allowed; }
  .ct-brief__next {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    padding: 0.85rem 1.6rem;
    background: #04a9ff;
    color: #0a0a0f !important;
    border: 1px solid #04a9ff;
    border-radius: var(--radius-sm);
    font-family: var(--font-sans);
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s var(--ease-out-expo);
    min-height: 44px;
  }
  .ct-brief__next:hover {
    background: #33bbff;
    transform: translateY(-1px);
    box-shadow: 0 6px 20px rgba(4, 169, 255, 0.3);
  }
  .ct-brief__next i { transition: transform 0.2s var(--ease-out-expo); }
  .ct-brief__next:hover i { transform: translateX(3px); }
  .ct-brief__step-of {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.72rem;
    color: var(--text-muted);
    letter-spacing: 0.12em;
  }
  .ct-brief__step-of b { color: #04a9ff; }

  /* Success state */
  .ct-brief__success {
    display: none;
    padding: 3rem 2.5rem;
    text-align: center;
  }
  .ct-brief__success.is-on {
    display: block;
    animation: ctStepIn 0.5s var(--ease-out-expo);
  }
  .ct-brief__success-check {
    width: 64px; height: 64px;
    border-radius: 50%;
    background: linear-gradient(135deg, #04a9ff, #0090dd);
    color: #0a0a0f;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.6rem;
    margin: 0 auto 1.25rem;
    box-shadow: 0 0 24px rgba(4, 169, 255, 0.4);
    animation: ctCheckPop 0.5s var(--ease-out-expo) 0.2s both;
  }
  @keyframes ctCheckPop {
    from { transform: scale(0.4); opacity: 0; }
    to   { transform: scale(1); opacity: 1; }
  }
  .ct-brief__success h3 {
    font-size: 1.4rem;
    font-weight: 600;
    color: var(--text-primary);
    margin: 0 0 0.6rem;
    letter-spacing: -0.02em;
  }
  .ct-brief__success p {
    font-size: 0.95rem;
    color: var(--text-secondary);
    line-height: 1.6;
    max-width: 460px;
    margin: 0 auto 1.5rem;
  }
  .ct-brief__success-recap {
    display: inline-flex;
    flex-direction: column;
    gap: 0.4rem;
    padding: 1rem 1.5rem;
    background: rgba(10, 10, 15, 0.4);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-sm);
    text-align: left;
    font-size: 0.82rem;
    color: var(--text-muted);
    max-width: 380px;
    margin: 0 auto;
  }
  .ct-brief__success-recap b {
    color: var(--text-primary);
    font-weight: 600;
  }
  .ct-brief__success-recap span {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.7rem;
    color: var(--text-muted);
    letter-spacing: 0.06em;
  }

  /* ════════════════════════════════════════════════════════════
     THE RESPONSE TIMELINE — visual diagram
     ════════════════════════════════════════════════════════════ */
  .ct-timeline {
    padding: 6rem 1.5rem 5rem;
    background: var(--bg-primary);
    position: relative;
  }
  .ct-timeline::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .ct-tl-head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3.5rem;
  }
  .ct-tl-eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .ct-tl-title {
    font-size: clamp(1.7rem, 3.2vw, 2.4rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .ct-tl-sub {
    font-size: 1.02rem;
    color: var(--text-secondary);
    line-height: 1.65;
    margin: 0;
  }

  .ct-tl-track {
    max-width: 1000px;
    margin: 0 auto;
    position: relative;
    display: grid;
    grid-template-columns: 1fr auto 1fr auto 1fr;
    align-items: center;
    gap: 0;
  }
  /* The horizontal line behind the dots */
  .ct-tl-track::before {
    content: "";
    position: absolute;
    top: 50%;
    left: calc(100% / 6);
    right: calc(100% / 6);
    height: 1px;
    background: linear-gradient(90deg,
      transparent 0%,
      rgba(4, 169, 255, 0.4) 30%,
      rgba(4, 169, 255, 0.6) 50%,
      rgba(4, 169, 255, 0.4) 70%,
      transparent 100%);
    z-index: 0;
  }
  .ct-tl-step {
    position: relative;
    z-index: 1;
    text-align: center;
    padding: 0 1rem;
  }
  .ct-tl-dot {
    width: 56px; height: 56px;
    border-radius: 50%;
    background: linear-gradient(135deg, #18181f 0%, #14141a 100%);
    border: 2px solid #04a9ff;
    color: #04a9ff;
    font-size: 1.1rem;
    font-weight: 700;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 1rem;
    position: relative;
    box-shadow:
      inset 0 1px 0 rgba(255, 255, 255, 0.05),
      0 0 16px rgba(4, 169, 255, 0.15);
  }
  .ct-tl-dot::after {
    content: "";
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    border: 1px solid rgba(4, 169, 255, 0.3);
    animation: ctTlPulse 2.6s ease-in-out infinite;
  }
  @keyframes ctTlPulse {
    0%, 100% { opacity: 0.4; transform: scale(1); }
    50%      { opacity: 1;   transform: scale(1.15); }
  }
  .ct-tl-step-time {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.72rem;
    color: #04a9ff;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    margin-bottom: 0.4rem;
  }
  .ct-tl-step-label {
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--text-primary);
    margin: 0 0 0.4rem;
    letter-spacing: -0.01em;
  }
  .ct-tl-step-desc {
    font-size: 0.82rem;
    color: var(--text-muted);
    line-height: 1.5;
    margin: 0;
    max-width: 220px;
    margin-left: auto;
    margin-right: auto;
  }
  /* Animated gold dot travelling along the track */
  .ct-tl-traveller {
    position: absolute;
    top: calc(50% - 4px);
    left: calc(100% / 6);
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #04a9ff;
    box-shadow: 0 0 12px rgba(4, 169, 255, 0.9);
    animation: ctTlTraveller 6s linear infinite;
    z-index: 2;
  }
  @keyframes ctTlTraveller {
    0%   { left: calc(100% / 6);   opacity: 0; }
    10%  { opacity: 1; }
    90%  { opacity: 1; }
    100% { left: calc(100% - 100% / 6); opacity: 0; }
  }
  /* Arrow connectors between steps */
  .ct-tl-arrow {
    color: rgba(4, 169, 255, 0.4);
    font-size: 0.9rem;
    z-index: 1;
  }

  /* ════════════════════════════════════════════════════════════
     DIRECT CONTACT — live status panels
     ════════════════════════════════════════════════════════════ */
  .ct-direct {
    padding: 5rem 1.5rem 5rem;
    background: var(--bg-secondary);
    position: relative;
  }
  .ct-direct::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .ct-direct__head {
    text-align: center;
    max-width: 720px;
    margin: 0 auto 3rem;
  }
  .ct-direct__eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: #04a9ff;
    margin-bottom: 1.25rem;
  }
  .ct-direct__title {
    font-size: clamp(1.5rem, 2.8vw, 2rem);
    font-weight: 600;
    letter-spacing: -0.03em;
    line-height: 1.15;
    margin: 0 0 0.6rem;
    color: var(--text-primary);
  }
  .ct-direct__sub {
    font-size: 0.95rem;
    color: var(--text-secondary);
    line-height: 1.55;
    margin: 0;
  }

  .ct-direct__grid {
    max-width: 1000px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
  }
  .ct-direct-card {
    position: relative;
    background: var(--bg-glass);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: var(--radius-lg);
    padding: 2rem 1.75rem;
    text-align: left;
    transition: all 0.3s var(--ease-out-expo);
    overflow: hidden;
  }
  .ct-direct-card::before {
    content: "";
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.10), transparent);
  }
  .ct-direct-card__top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 1.25rem;
  }
  .ct-direct-card__icon {
    width: 44px; height: 44px;
    border-radius: 12px;
    background: rgba(4, 169, 255, 0.1);
    border: 1px solid rgba(4, 169, 255, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #04a9ff;
    font-size: 1.1rem;
  }
  .ct-direct-card__status {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.6rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    color: var(--text-muted);
    text-transform: uppercase;
  }
  .ct-direct-card__status .led {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: #4ade80;
    box-shadow: 0 0 6px rgba(74, 222, 128, 0.7);
    animation: ctLedPulse 2.4s ease-in-out infinite;
  }
  .ct-direct-card__label {
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    color: var(--text-muted);
    text-transform: uppercase;
    margin: 0 0 0.5rem;
  }
  .ct-direct-card__value {
    font-size: 1.1rem;
    font-weight: 600;
    color: var(--text-primary);
    letter-spacing: -0.01em;
    margin: 0 0 0.5rem;
    word-break: break-word;
  }
  .ct-direct-card__meta {
    font-family: var(--font-mono, "SF Mono", "Monaco", monospace);
    font-size: 0.65rem;
    color: var(--text-muted);
    letter-spacing: 0.06em;
    margin: 0 0 0.75rem;
  }
  .ct-direct-card__note {
    font-size: 0.78rem;
    color: var(--text-secondary);
    line-height: 1.5;
    margin: 0;
  }
  .ct-direct-card__link {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    margin-top: 1rem;
    font-size: 0.78rem;
    font-weight: 600;
    color: #04a9ff;
    letter-spacing: 0.04em;
    text-decoration: none !important;
  }
  .ct-direct-card__link i { transition: transform 0.2s var(--ease-out-expo); }
  .ct-direct-card__link:hover i { transform: translateX(3px); }
  .ct-direct-card:hover {
    transform: translateY(-3px);
    border-color: rgba(4, 169, 255, 0.25);
    background: var(--bg-glass-hover);
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.3);
  }

  /* ════════════════════════════════════════════════════════════
     FINAL CTA
     ════════════════════════════════════════════════════════════ */
  .ct-cta {
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
  .ct-cta::before {
    content: "";
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 200px; height: 1px;
    background: linear-gradient(90deg, transparent, #04a9ff, transparent);
  }
  .ct-cta__eq {
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
  .ct-cta__eq span {
    display: block;
    width: 2px;
    background: #04a9ff;
    border-radius: 1px;
    animation: ctEqBar 1.6s ease-in-out infinite;
  }
  .ct-cta__eq span:nth-child(1)  { height: 8px;  animation-delay: 0.0s; }
  .ct-cta__eq span:nth-child(2)  { height: 14px; animation-delay: 0.2s; }
  .ct-cta__eq span:nth-child(3)  { height: 6px;  animation-delay: 0.4s; }
  .ct-cta__eq span:nth-child(4)  { height: 16px; animation-delay: 0.1s; }
  .ct-cta__eq span:nth-child(5)  { height: 10px; animation-delay: 0.3s; }
  .ct-cta__eq span:nth-child(6)  { height: 18px; animation-delay: 0.15s; }
  .ct-cta__eq span:nth-child(7)  { height: 8px;  animation-delay: 0.35s; }
  .ct-cta__eq span:nth-child(8)  { height: 12px; animation-delay: 0.05s; }
  .ct-cta__eq span:nth-child(9)  { height: 6px;  animation-delay: 0.25s; }
  .ct-cta__eq span:nth-child(10) { height: 14px; animation-delay: 0.45s; }
  @keyframes ctEqBar {
    0%, 100% { transform: scaleY(0.4); }
    50%      { transform: scaleY(1.6); }
  }
  .ct-cta h2 {
    position: relative;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 600;
    letter-spacing: -0.035em;
    line-height: 1.1;
    margin: 0 0 1rem;
    color: var(--text-primary);
  }
  .ct-cta p {
    position: relative;
    font-size: 1.05rem;
    color: var(--text-secondary);
    line-height: 1.65;
    max-width: 520px;
    margin: 0 auto 2rem;
  }
  .ct-cta .ct-btn { position: relative; }
  .ct-cta__note {
    position: relative;
    display: block;
    margin-top: 1.25rem;
    font-size: 0.8rem;
    color: var(--text-muted);
    letter-spacing: 0.04em;
  }

  /* Scroll reveal */
  .ct-reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease-out, transform 0.7s ease-out;
  }
  .ct-reveal.is-visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    .ct-brief__steps { padding: 1.5rem 1.25rem 1rem; }
    .ct-brief__step-label { display: none; }
    .ct-brief__body { padding: 1rem 1.5rem 0.5rem; min-height: 320px; }
    .ct-brief__foot { padding: 1.25rem 1.5rem 1.5rem; }
    .ct-direct__grid { grid-template-columns: 1fr; max-width: 480px; }
    .ct-tl-track {
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }
    .ct-tl-track::before { display: none; }
    .ct-tl-arrow { display: none; }
    .ct-tl-traveller { display: none; }
    .ct-mini-nav { gap: 1rem; font-size: 0.7rem; }
  }
  @media (max-width: 600px) {
    .ct-hero { padding: 7rem 1rem 4rem; min-height: auto; }
    .ct-brief { padding: 4rem 1rem; }
    .ct-timeline { padding: 4rem 1rem 3rem; }
    .ct-direct { padding: 3rem 1rem; }
    .ct-cta { padding: 3.5rem 1.5rem; }
    .ct-field__row { grid-template-columns: 1fr; }
  }
</style>

<!-- ═══ STICKY MINI-NAV ═══ -->
<nav class="ct-mini-nav" aria-label="Page sections">
  <a href="#ct-timeline">Timeline</a>
  <a href="#ct-direct">Direct contact</a>
  <a href="#ct-cta">Get started</a>
</nav>

<!-- ═══ HERO ═══ -->
<section class="ct-hero">
  <div class="ct-hero__inner">
    <div class="ct-eyebrow ct-reveal">
      <span class="ct-eyebrow__dot"></span>
      CONTACT
    </div>
    <h1 class="ct-reveal">
      Tell us about <span class="gold">the night.</span>
    </h1>
    <div class="ct-hero__ctas ct-reveal">
      <a href="/photos/" class="ct-btn ct-btn--primary">
        Photos
        <span class="ct-btn__arrow">→</span>
      </a>
      <a href="/" class="ct-btn ct-btn--ghost">
        Home
      </a>
    </div>
  </div>
</section>

<!-- ═══ THE EVENT BRIEF ═══ -->
<!-- FORM REMOVED — spam prevention. To re-enable, restore from .backups/form-off/contact.bak -->
<section class="ct-brief" id="ct-brief">
  <div class="ct-brief__panel ct-reveal" style="text-align:center; padding: 4rem 2rem;">
    <div class="ct-brief__head">
      <span class="ct-brief__brand">EVT-CT-01</span>
      <span class="ct-brief__title">Contact</span>
      <span class="ct-brief__led">
        <span class="led" style="background:#ef4444; box-shadow:0 0 8px #ef4444;"></span>
        <span class="ct-brief__led-lbl">Offline</span>
      </span>
    </div>
    <div style="padding: 3rem 2rem;">
      <h3 style="font-size:clamp(1.3rem, 2vw, 1.6rem); margin: 0 0 1rem; color: var(--text-primary);">Form currently offline.</h3>
      <p style="color: rgba(242, 242, 245, 0.6); line-height: 1.7; max-width: 500px; margin: 0 auto 2rem;">
        We've temporarily disabled the enquiry form. Reply on the platform where you found this link.
      </p>
      <div style="display: flex; gap: 0.75rem; justify-content: center; flex-wrap: wrap;">
        <a href="/photos/" class="ct-btn ct-btn--primary">
          Photos <span class="ct-btn__arrow">→</span>
        </a>
        <a href="/" class="ct-btn ct-btn--ghost">
          Home
        </a>
      </div>
    </div>
  </div>
</section>

<!-- Original form removed. See below for the Response Timeline. -->

<!-- ═══ THE RESPONSE TIMELINE ═══ -->
<section class="ct-timeline" id="ct-timeline">
  <div class="ct-tl-head ct-reveal">
    <div class="ct-tl-eyebrow">What's next</div>
    <h2 class="ct-tl-title">A reply in your inbox within 24 hours</h2>
  </div>

  <div class="ct-tl-track ct-reveal">
    <div class="ct-tl-step">
      <div class="ct-tl-dot">1</div>
      <div class="ct-tl-step-time">Now</div>
      <div class="ct-tl-step-label">Reach out</div>
      <div class="ct-tl-step-desc">Reply on the platform where you found this link.</div>
    </div>
    <i class="fas fa-chevron-right ct-tl-arrow"></i>
    <div class="ct-tl-step">
      <div class="ct-tl-dot">2</div>
      <div class="ct-tl-step-time">Within 24h</div>
      <div class="ct-tl-step-label">Reply</div>
      <div class="ct-tl-step-desc">Tailored plan in your inbox.</div>
    </div>
    <i class="fas fa-chevron-right ct-tl-arrow"></i>
    <div class="ct-tl-step">
      <div class="ct-tl-dot">3</div>
      <div class="ct-tl-step-time">Same week</div>
      <div class="ct-tl-step-label">Contact</div>
      <div class="ct-tl-step-desc">Quick chat to lock in the plan, or confirm via email.</div>
    </div>
    <div class="ct-tl-traveller" aria-hidden="true"></div>
  </div>
</section>

<!-- ═══ DIRECT CONTACT ═══ -->
<section class="ct-direct" id="ct-direct">
  <div class="ct-direct__head ct-reveal">
    <div class="ct-direct__eyebrow">What to expect</div>
    <h2 class="ct-direct__title">Reply to us on the same platform you found this link.</h2>
  </div>

  <div class="ct-direct__grid">
    <div class="ct-direct-card ct-reveal">
      <div class="ct-direct-card__top">
        <div class="ct-direct-card__icon"><i class="fas fa-comment-dots"></i></div>
      </div>
      <div class="ct-direct-card__label">Reply</div>
      <div class="ct-direct-card__value">Where you found us</div>
      <div class="ct-direct-card__meta">Instagram · Facebook · Email · SMS</div>
      <p class="ct-direct-card__note">Reply on the platform where you got this link. No forms.</p>
    </div>

    <div class="ct-direct-card ct-reveal">
      <div class="ct-direct-card__top">
        <div class="ct-direct-card__icon"><i class="fas fa-clock"></i></div>
      </div>
      <div class="ct-direct-card__label">Response</div>
      <div class="ct-direct-card__value">Within 24 hours</div>
      <div class="ct-direct-card__meta">Mon–Sat · Often same-day</div>
      <p class="ct-direct-card__note">A real reply with a plan, price and next step.</p>
    </div>

    <div class="ct-direct-card ct-reveal">
      <div class="ct-direct-card__top">
        <div class="ct-direct-card__icon"><i class="fas fa-map-marker-alt"></i></div>
      </div>
      <div class="ct-direct-card__label">Location</div>
      <div class="ct-direct-card__value">Central Coast, NSW</div>
      <div class="ct-direct-card__meta">Sydney, Newcastle, Hunter</div>
      <p class="ct-direct-card__note">Travel fees quoted upfront if outside the Coast.</p>
    </div>
  </div>
</section>

<!-- ═══ FINAL CTA ═══ -->
<section class="ct-cta ct-reveal" id="ct-cta">
  <div class="ct-cta__eq" aria-hidden="true">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>
  <h2>Get a plan that fits.</h2>
  <p>Reply on the platform you found this link. Tailored plan within 24 hours.</p>
  <a href="#ct-direct" class="ct-btn ct-btn--primary">
    Discuss
    <span class="ct-btn__arrow">→</span>
  </a>
  <span class="ct-cta__note">Free · No obligation · Same-day reply for most enquiries</span>
</section>

<script>
  (function() {
    // ── Reveal on scroll ──
    function setupReveal() {
      const els = document.querySelectorAll('.ct-reveal');
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
      const nav = document.querySelector('.ct-mini-nav');
      if (!nav) return;
      const hero = document.querySelector('.ct-hero');
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
      document.querySelectorAll('a[href^="#ct-"]').forEach(a => {
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
      // Safety net
      setTimeout(function() {
        document.querySelectorAll('.ct-reveal:not(.is-visible)').forEach(function(el) {
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
