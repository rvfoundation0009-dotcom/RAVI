<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ravi Thungathurthi</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Cinzel:wght@400;600&family=Raleway:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #c9a84c;
    --gold-light: #f0d080;
    --gold-dark: #8a6a1e;
    --deep: #0a0a12;
    --card-bg: rgba(255,255,255,0.04);
    --glow: rgba(201,168,76,0.25);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--deep);
    min-height: 100vh;
    font-family: 'Raleway', sans-serif;
    overflow-x: hidden;
    position: relative;
  }

  .bg-canvas {
    position: fixed;
    inset: 0;
    z-index: 0;
    overflow: hidden;
  }

  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.18;
    animation: drift 12s ease-in-out infinite alternate;
  }

  .orb-1 {
    width: 600px; height: 600px;
    background: radial-gradient(circle, #c9a84c, transparent 70%);
    top: -150px; left: -150px;
    animation-delay: 0s;
  }

  .orb-2 {
    width: 500px; height: 500px;
    background: radial-gradient(circle, #4a3aaa, transparent 70%);
    bottom: -100px; right: -100px;
    animation-delay: -4s;
  }

  .orb-3 {
    width: 350px; height: 350px;
    background: radial-gradient(circle, #c9a84c, transparent 70%);
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    animation-delay: -8s;
  }

  @keyframes drift {
    0%   { transform: translate(0, 0) scale(1); }
    100% { transform: translate(40px, 40px) scale(1.08); }
  }

  .grain {
    position: fixed;
    inset: 0;
    z-index: 1;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
    opacity: 0.035;
    pointer-events: none;
  }

  .container {
    position: relative;
    z-index: 10;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 60px 20px;
  }

  .top-rule {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 40px;
    animation: fadeDown 1s ease 0.2s both;
  }

  .rule-line {
    width: 80px;
    height: 1px;
    background: linear-gradient(to right, transparent, var(--gold));
  }

  .rule-line.right {
    background: linear-gradient(to left, transparent, var(--gold));
  }

  .rule-diamond {
    width: 8px; height: 8px;
    background: var(--gold);
    transform: rotate(45deg);
  }

  .avatar-ring {
    width: 120px; height: 120px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, var(--gold-dark), var(--gold-light), var(--gold), var(--gold-dark));
    padding: 3px;
    margin-bottom: 28px;
    animation: fadeDown 1s ease 0.3s both;
    box-shadow: 0 0 40px var(--glow), 0 0 80px rgba(201,168,76,0.1);
    position: relative;
  }

  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: #0e0e1a;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Cinzel', serif;
    font-size: 2.8rem;
    font-weight: 600;
    color: var(--gold);
    letter-spacing: 2px;
  }

  .title-block {
    text-align: center;
    margin-bottom: 16px;
    animation: fadeDown 1s ease 0.4s both;
  }

  .name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 5vw, 3.2rem);
    font-weight: 900;
    color: #ffffff;
    letter-spacing: 2px;
    line-height: 1.1;
  }

  .name span { color: var(--gold); }

  .subtitle {
    font-family: 'Cinzel', serif;
    font-size: 0.75rem;
    letter-spacing: 6px;
    color: var(--gold);
    text-transform: uppercase;
    margin-top: 10px;
    opacity: 0.85;
  }

  .tagline {
    font-size: 0.9rem;
    color: rgba(255,255,255,0.4);
    margin-top: 8px;
    font-weight: 300;
    letter-spacing: 1px;
  }

  .divider {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, transparent, var(--gold), transparent);
    margin: 28px 0;
    animation: fadeDown 1s ease 0.5s both;
  }

  .cards {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
    width: 100%;
    max-width: 500px;
  }

  .card {
    position: relative;
    border-radius: 20px;
    padding: 28px 20px 24px;
    background: var(--card-bg);
    border: 1px solid rgba(201,168,76,0.15);
    cursor: pointer;
    text-decoration: none;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
    transition: transform 0.35s cubic-bezier(.22,.68,0,1.2), border-color 0.3s, box-shadow 0.3s, background 0.3s;
    overflow: hidden;
    animation: fadeUp 0.8s ease both;
  }

  .card:nth-child(1) { animation-delay: 0.6s; }
  .card:nth-child(2) { animation-delay: 0.75s; }
  .card:nth-child(3) { animation-delay: 0.9s; }
  .card:nth-child(4) { animation-delay: 1.05s; }

  .card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(201,168,76,0.08), transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .card:hover {
    transform: translateY(-8px) scale(1.03);
    border-color: var(--gold);
    box-shadow: 0 20px 60px rgba(0,0,0,0.5), 0 0 30px var(--glow);
    background: rgba(201,168,76,0.06);
  }

  .card:hover::before { opacity: 1; }
  .card:active { transform: translateY(-4px) scale(1.01); }

  .icon-wrap {
    width: 60px; height: 60px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    transition: transform 0.3s;
  }

  .card:hover .icon-wrap { transform: scale(1.1) rotate(-4deg); }
  .icon-wrap svg { width: 30px; height: 30px; }

  .card.whatsapp .icon-wrap {
    background: radial-gradient(circle at 30% 30%, #25d36620, #25d36608);
    border: 1px solid #25d36630;
    box-shadow: 0 0 20px #25d36615;
  }

  .card.facebook .icon-wrap {
    background: radial-gradient(circle at 30% 30%, #1877f220, #1877f208);
    border: 1px solid #1877f230;
    box-shadow: 0 0 20px #1877f215;
  }

  .card.instagram .icon-wrap {
    background: radial-gradient(circle at 30% 30%, #e105b620, #e105b608);
    border: 1px solid #e105b630;
    box-shadow: 0 0 20px #e105b615;
  }

  .card.website .icon-wrap {
    background: radial-gradient(circle at 30% 30%, #c9a84c20, #c9a84c08);
    border: 1px solid #c9a84c30;
    box-shadow: 0 0 20px #c9a84c15;
  }

  .card-label {
    font-family: 'Cinzel', serif;
    font-size: 0.7rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.7);
    transition: color 0.3s;
  }

  .card:hover .card-label { color: var(--gold-light); }

  .card-desc {
    font-size: 0.72rem;
    color: rgba(255,255,255,0.3);
    text-align: center;
    font-weight: 300;
    line-height: 1.4;
  }

  .card-arrow {
    position: absolute;
    top: 12px; right: 14px;
    opacity: 0;
    transform: translate(-4px, 4px);
    transition: opacity 0.3s, transform 0.3s;
    color: var(--gold);
    font-size: 0.85rem;
  }

  .card:hover .card-arrow { opacity: 1; transform: translate(0, 0); }

  .footer {
    margin-top: 48px;
    text-align: center;
    animation: fadeUp 1s ease 1.2s both;
  }

  .footer-text {
    font-size: 0.7rem;
    letter-spacing: 4px;
    color: rgba(255,255,255,0.2);
    text-transform: uppercase;
  }

  .footer-line {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    margin-top: 10px;
  }

  .footer-dot {
    width: 4px; height: 4px;
    background: var(--gold);
    border-radius: 50%;
    opacity: 0.5;
  }

  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .ripple {
    position: absolute;
    border-radius: 50%;
    background: rgba(201,168,76,0.3);
    transform: scale(0);
    animation: ripple 0.6s linear;
    pointer-events: none;
  }

  @keyframes ripple {
    to { transform: scale(4); opacity: 0; }
  }

  .avatar-ring::after {
    content: '';
    position: absolute;
    inset: -6px;
    border-radius: 50%;
    border: 1px solid rgba(201,168,76,0.3);
    animation: pulse-ring 2.5s ease-out infinite;
  }

  @keyframes pulse-ring {
    0%   { transform: scale(1); opacity: 0.5; }
    100% { transform: scale(1.2); opacity: 0; }
  }

  @media (max-width: 400px) {
    .cards { grid-template-columns: 1fr 1fr; gap: 12px; }
    .card { padding: 22px 14px 18px; }
    .name { font-size: 1.7rem; }
  }
</style>
</head>
<body>

<div class="bg-canvas">
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>
</div>
<div class="grain"></div>

<div class="container">

  <div class="top-rule">
    <div class="rule-line"></div>
    <div class="rule-diamond"></div>
    <div class="rule-line right"></div>
  </div>

  <div class="avatar-ring">
    <div class="avatar-inner">RT</div>
  </div>

  <div class="title-block">
    <div class="name">Ravi <span>Thungathurthi</span></div>
    <div class="subtitle">Connect &nbsp;·&nbsp; Follow &nbsp;·&nbsp; Discover</div>
    <div class="tagline">Find me across all platforms</div>
  </div>

  <div class="divider"></div>

  <div class="cards">

    <a class="card whatsapp" href="https://whatsapp.com/channel/0029VavLKDuJuyAAErokuC0u" target="_blank" rel="noopener">
      <span class="card-arrow">↗</span>
      <div class="icon-wrap">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149
