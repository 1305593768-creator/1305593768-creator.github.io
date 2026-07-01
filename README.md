[Uploading index.html…]()
<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Cassie's Content Journey</title>
  <meta name="description" content="周慧 Cassie 的内容营销作品集网站。">
  <style>
    :root {
      --cream: #FAF7F2;
      --cream-2: #FFFDF8;
      --gold: #E7C97D;
      --gold-soft: #F0DCA6;
      --gold-deep: #B98A2D;
      --gold-ink: #8A6320;
      --pink: #EFD8DE;
      --pink-2: #F8C8D2;
      --blue: #D8E9F4;
      --violet: #DCD5F4;
      --sage: #DCEAD7;
      --ink: #2C2C2C;
      --muted: #6B6B6B;
      --line: rgba(44, 44, 44, 0.10);
      --glass-top: rgba(255, 255, 255, 0.78);
      --glass-bottom: rgba(255, 253, 248, 0.46);
      --glass-border: rgba(255, 255, 255, 0.72);
      --shadow: 0 34px 80px -32px rgba(120, 84, 52, 0.42), 0 12px 30px -18px rgba(120, 84, 52, 0.30);
      --soft-shadow: 0 22px 48px -26px rgba(120, 84, 52, 0.36);
      --highlight: inset 0 1px 0 rgba(255, 255, 255, 0.85), inset 0 0 0 1px rgba(255, 255, 255, 0.32);
      --radius: 26px;
      --radius-sm: 18px;
      --nav-h: 76px;
      --serif: "Songti SC", Georgia, "Times New Roman", "Noto Serif SC", serif;
      --sans: -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", Arial, sans-serif;
      color-scheme: light;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; background: var(--cream); }

    body {
      margin: 0;
      min-width: 320px;
      background: transparent;
      color: var(--ink);
      font-family: var(--sans);
      line-height: 1.6;
      overflow-x: hidden;
      text-rendering: optimizeLegibility;
      -webkit-font-smoothing: antialiased;
    }

    a { color: inherit; text-decoration: none; }
    button { font: inherit; cursor: pointer; }
    img { display: block; max-width: 100%; }

    /* ---------- Atmosphere: sky, clouds, petals, particles ---------- */
    .sky {
      position: fixed;
      inset: -10vh 0 auto 0;
      height: 130vh;
      z-index: -3;
      pointer-events: none;
      background:
        radial-gradient(120% 80% at 50% -20%, rgba(216, 233, 244, 0.55), transparent 55%),
        radial-gradient(90% 60% at 12% 8%, rgba(239, 216, 222, 0.40), transparent 60%),
        radial-gradient(80% 60% at 88% 4%, rgba(231, 201, 125, 0.30), transparent 58%),
        linear-gradient(180deg, #FDF6EC 0%, var(--cream) 38%, var(--cream) 100%);
      will-change: transform;
    }

    .clouds {
      position: fixed;
      inset: 0;
      z-index: -2;
      pointer-events: none;
      overflow: hidden;
    }

    .clouds span {
      position: absolute;
      border-radius: 50%;
      filter: blur(34px);
      opacity: 0.7;
      background: radial-gradient(circle at 38% 36%, rgba(255, 255, 255, 0.95), rgba(255, 255, 255, 0) 70%);
      will-change: transform;
    }

    .clouds span:nth-child(1) { width: 460px; height: 200px; top: 8%;  left: -8%;  animation: drift 46s ease-in-out infinite alternate; }
    .clouds span:nth-child(2) { width: 360px; height: 160px; top: 24%; left: 64%;  opacity: 0.55; animation: drift 58s ease-in-out infinite alternate-reverse; }
    .clouds span:nth-child(3) { width: 520px; height: 220px; top: 52%; left: 18%;  opacity: 0.42; background: radial-gradient(circle at 40% 40%, rgba(255,251,242,0.9), rgba(255,251,242,0) 70%); animation: drift 64s ease-in-out infinite alternate; }
    .clouds span:nth-child(4) { width: 300px; height: 140px; top: 74%; left: 76%;  opacity: 0.4;  animation: drift 52s ease-in-out infinite alternate-reverse; }

    .ambient {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }

    .petal {
      position: absolute;
      top: -8vh;
      width: 11px;
      height: 14px;
      border-radius: 80% 10% 80% 10%;
      background: linear-gradient(135deg, rgba(248, 200, 210, 0.9), rgba(239, 216, 222, 0.5));
      opacity: 0;
      animation: petalFall linear infinite;
      will-change: transform, opacity;
    }

    .petal.gold { background: linear-gradient(135deg, rgba(240, 220, 166, 0.95), rgba(231, 201, 125, 0.45)); }

    .spark {
      position: absolute;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(255, 244, 214, 0.95), rgba(231, 201, 125, 0.0) 70%);
      box-shadow: 0 0 8px 2px rgba(231, 201, 125, 0.55);
      animation: floatUp linear infinite, twinkle 2.6s ease-in-out infinite;
      will-change: transform, opacity;
    }

    @keyframes drift {
      from { transform: translate3d(-4vw, 0, 0) scale(1); }
      to   { transform: translate3d(5vw, -1.4vh, 0) scale(1.06); }
    }

    @keyframes petalFall {
      0%   { transform: translate3d(0, 0, 0) rotate(0deg); opacity: 0; }
      10%  { opacity: 0.85; }
      90%  { opacity: 0.75; }
      100% { transform: translate3d(9vw, 116vh, 0) rotate(320deg); opacity: 0; }
    }

    @keyframes floatUp {
      0%   { transform: translate3d(0, 0, 0); opacity: 0; }
      14%  { opacity: 0.9; }
      86%  { opacity: 0.7; }
      100% { transform: translate3d(2vw, -80vh, 0); opacity: 0; }
    }

    @keyframes twinkle {
      0%, 100% { box-shadow: 0 0 5px 1px rgba(231, 201, 125, 0.35); }
      50%      { box-shadow: 0 0 12px 4px rgba(231, 201, 125, 0.7); }
    }

    @keyframes floaty {
      0%, 100% { transform: translate3d(0, 0, 0) rotate(var(--rot, 0deg)); }
      50%      { transform: translate3d(0, -13px, 0) rotate(calc(var(--rot, 0deg) + 1.2deg)); }
    }

    .floaty { animation: floaty 6.6s ease-in-out infinite; }
    .floaty-slow { animation: floaty 8.6s ease-in-out infinite; }

    /* ---------- Reveal ---------- */
    .reveal {
      opacity: 0;
      transform: translateY(34px);
      transition: opacity 900ms cubic-bezier(.2,.7,.2,1), transform 900ms cubic-bezier(.2,.7,.2,1);
    }
    .reveal.is-visible { opacity: 1; transform: none; }
    .reveal[data-delay="1"] { transition-delay: 90ms; }
    .reveal[data-delay="2"] { transition-delay: 180ms; }
    .reveal[data-delay="3"] { transition-delay: 270ms; }
    .reveal[data-delay="4"] { transition-delay: 360ms; }

    /* ---------- Navigation ---------- */
    .site-nav {
      position: sticky;
      top: 0;
      z-index: 50;
      min-height: var(--nav-h);
      background: linear-gradient(180deg, rgba(250, 247, 242, 0.9), rgba(250, 247, 242, 0.62));
      backdrop-filter: blur(20px) saturate(1.25);
      -webkit-backdrop-filter: blur(20px) saturate(1.25);
      border-bottom: 1px solid rgba(255, 255, 255, 0.5);
      box-shadow: 0 10px 30px -24px rgba(120, 84, 52, 0.5);
    }

    .nav-inner {
      width: min(1240px, calc(100% - 48px));
      min-height: var(--nav-h);
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 11px;
      min-width: 0;
      font-weight: 800;
      letter-spacing: 0.2px;
      white-space: nowrap;
    }

    .brand-mark {
      display: grid;
      place-items: center;
      width: 38px;
      height: 38px;
      border-radius: 50%;
      background: radial-gradient(circle at 35% 30%, #fff, rgba(231, 201, 125, 0.5) 78%);
      color: var(--gold-deep);
      font-size: 18px;
      box-shadow: 0 8px 22px -8px rgba(185, 138, 45, 0.65), var(--highlight);
    }

    .brand span:last-child { overflow: hidden; text-overflow: ellipsis; }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 4px;
      padding: 5px;
      border-radius: 999px;
      background: rgba(255, 255, 255, 0.55);
      border: 1px solid rgba(255, 255, 255, 0.6);
      box-shadow: 0 14px 30px -22px rgba(120, 84, 52, 0.6), var(--highlight);
    }

    .nav-links a {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 36px;
      padding: 0 15px;
      border-radius: 999px;
      color: #7a665f;
      font-size: 13px;
      font-weight: 600;
      white-space: nowrap;
      transition: background 220ms ease, color 220ms ease, box-shadow 220ms ease;
    }

    .nav-links a:hover { color: var(--ink); }
    .nav-links a.is-active {
      color: var(--gold-ink);
      background: linear-gradient(180deg, rgba(240, 220, 166, 0.85), rgba(231, 201, 125, 0.4));
      box-shadow: 0 8px 18px -10px rgba(185, 138, 45, 0.7);
    }

    /* ---------- Layout primitives ---------- */
    main { position: relative; }

    section { position: relative; scroll-margin-top: calc(var(--nav-h) + 18px); }

    .section {
      width: min(1240px, calc(100% - 48px));
      margin: 0 auto;
      padding: clamp(72px, 9vw, 120px) 0;
    }

    .glass {
      position: relative;
      border-radius: var(--radius);
      background: linear-gradient(155deg, var(--glass-top), var(--glass-bottom));
      border: 1px solid var(--glass-border);
      box-shadow: var(--shadow), var(--highlight);
      backdrop-filter: blur(22px) saturate(1.3);
      -webkit-backdrop-filter: blur(22px) saturate(1.3);
    }

    .glass::before {
      content: "";
      position: absolute;
      inset: 0;
      border-radius: inherit;
      background: radial-gradient(120% 80% at 50% -10%, rgba(255, 255, 255, 0.55), transparent 60%);
      pointer-events: none;
      opacity: 0.8;
    }

    .lift { transition: transform 420ms cubic-bezier(.2,.7,.2,1), box-shadow 420ms ease; }
    .lift:hover {
      transform: translateY(-6px);
      box-shadow: 0 44px 90px -34px rgba(120, 84, 52, 0.5), var(--highlight);
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      width: fit-content;
      min-height: 32px;
      padding: 0 14px;
      border-radius: 999px;
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.7), rgba(240, 220, 166, 0.34));
      border: 1px solid rgba(231, 201, 125, 0.5);
      color: var(--gold-ink);
      font-size: 12.5px;
      font-weight: 800;
      letter-spacing: 0.4px;
      line-height: 1;
      box-shadow: var(--highlight);
    }
    .eyebrow::before {
      content: "✦";
      font-size: 12px;
      color: var(--gold-deep);
    }

    .section-head {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      gap: 30px;
      margin-bottom: 44px;
    }

    .section-head h2 {
      margin: 16px 0 0;
      font-family: var(--serif);
      font-size: clamp(32px, 4.2vw, 54px);
      line-height: 1.1;
      font-weight: 600;
      color: var(--ink);
    }

    .section-head p {
      max-width: 460px;
      margin: 0;
      color: var(--muted);
      font-size: 15.5px;
      line-height: 1.85;
      text-align: right;
    }

    /* ---------- Hero ---------- */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 4fr) minmax(300px, 1.06fr);
      align-items: stretch;
      gap: 24px;
      width: min(1240px, calc(100% - 48px));
      margin: 0 auto;
      padding: clamp(40px, 5vw, 70px) 0 clamp(30px, 4vw, 52px);
    }

    .hero-left {
      position: relative;
      display: grid;
      align-content: start;
      min-height: 0;
      padding: clamp(28px, 3.4vw, 48px);
      overflow: hidden;
      isolation: isolate;
    }

    .hero-glow {
      position: absolute;
      z-index: -1;
      width: 60%;
      height: 60%;
      top: -10%;
      left: -6%;
      background: radial-gradient(circle, rgba(231, 201, 125, 0.4), transparent 65%);
      filter: blur(10px);
    }

    .hero-copy { position: relative; z-index: 3; max-width: 690px; }

    .hero h1 {
      margin: 20px 0 16px;
      font-family: var(--serif);
      font-size: clamp(46px, 6.6vw, 88px);
      line-height: 1.0;
      font-weight: 600;
      letter-spacing: 0.5px;
      color: var(--ink);
    }
    .hero h1 span { display: block; }
    .hero h1 .accent {
      background: linear-gradient(100deg, var(--gold-deep), var(--gold) 45%, #d9a93f 78%, var(--gold-deep));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      text-shadow: 0 1px 0 rgba(255, 255, 255, 0.4);
    }

    .profile-title { display: grid; gap: 8px; margin-bottom: 18px; }
    .profile-title strong { color: var(--ink); font-size: clamp(24px, 2.7vw, 34px); line-height: 1.2; font-weight: 700; }
    .profile-title span { color: #5d534d; font-size: 16px; font-weight: 600; }

    .hero-focus {
      width: fit-content;
      max-width: 100%;
      margin: 14px 0 22px;
      padding: 11px 20px;
      border-radius: 999px;
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.78), rgba(240, 220, 166, 0.3));
      border: 1px solid rgba(231, 201, 125, 0.5);
      color: var(--gold-ink);
      font-size: clamp(16px, 1.7vw, 21px);
      font-weight: 800;
      line-height: 1.35;
      box-shadow: var(--highlight);
    }

    .intro-list {
      display: grid;
      gap: 12px;
      max-width: 700px;
      margin: 0 0 24px;
      padding: 0;
      list-style: none;
    }
    .intro-list li {
      display: grid;
      grid-template-columns: 22px minmax(0, 1fr);
      gap: 10px;
      color: #4F4742;
      font-size: 15.5px;
      line-height: 1.75;
    }
    .intro-list li::before {
      content: "";
      margin-top: 9px;
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: radial-gradient(circle at 35% 30%, #fff, var(--gold) 75%);
      box-shadow: 0 0 0 4px rgba(231, 201, 125, 0.18);
    }

    .watch-box {
      width: min(540px, 100%);
      padding: 18px 22px;
      border-radius: var(--radius-sm);
      border: 1px solid rgba(231, 201, 125, 0.34);
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.62), rgba(239, 216, 222, 0.22));
    }
    .watch-box b { display: block; margin-bottom: 8px; color: var(--gold-ink); font-size: 17px; }
    .watch-box span { display: block; color: #4C4440; font-size: 15.5px; line-height: 1.85; }

    .hero-sticker {
      position: absolute;
      z-index: 2;
      display: grid;
      place-items: center;
      margin: 0;
      width: clamp(64px, 7.4vw, 92px);
      aspect-ratio: 1;
      border-radius: 50%;
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.92), rgba(240, 220, 166, 0.5));
      border: 1px solid rgba(231, 201, 125, 0.55);
      color: var(--gold-deep);
      box-shadow: var(--soft-shadow), var(--highlight);
    }
    .hero-sticker svg { width: 46%; height: 46%; }
    .hero-sticker.one { top: 6%; right: 9%; --rot: 7deg; transform: rotate(7deg); }
    .hero-sticker.two { right: 4%; bottom: 7%; width: clamp(52px, 6vw, 74px); --rot: -6deg; transform: rotate(-6deg); }

    .hero-right { display: grid; grid-template-rows: auto 1fr; gap: 18px; min-width: 0; }

    .about-card { position: relative; overflow: hidden; padding: 24px; }
    .card-eyebrow {
      display: flex;
      align-items: center;
      gap: 8px;
      margin: 0 0 16px;
      color: var(--gold-ink);
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 1.4px;
      text-transform: uppercase;
    }
    .card-eyebrow::before {
      content: "";
      width: 18px;
      height: 2px;
      border-radius: 2px;
      background: linear-gradient(90deg, var(--gold-deep), transparent);
    }

    .about-list { position: relative; z-index: 1; display: grid; gap: 13px; margin: 0; padding: 0; list-style: none; }
    .about-list li {
      display: grid;
      grid-template-columns: 28px minmax(0, 1fr);
      gap: 11px;
      align-items: center;
      color: #4D4741;
      font-size: 14px;
      line-height: 1.45;
      overflow-wrap: anywhere;
    }
    .about-list .ico {
      display: grid;
      place-items: center;
      width: 28px;
      height: 28px;
      border-radius: 9px;
      background: rgba(231, 201, 125, 0.16);
      color: var(--gold-deep);
    }
    .about-list .ico svg { width: 16px; height: 16px; }

    /* Data dashboard — the visual heart of the homepage */
    .data-card {
      position: relative;
      display: grid;
      align-content: start;
      gap: 14px;
      padding: 24px;
      background:
        radial-gradient(120% 70% at 50% -10%, rgba(240, 220, 166, 0.5), transparent 60%),
        linear-gradient(160deg, rgba(255, 255, 255, 0.82), rgba(255, 250, 235, 0.5));
      border-color: rgba(231, 201, 125, 0.55);
      box-shadow: 0 40px 84px -34px rgba(185, 138, 45, 0.55), var(--highlight);
    }
    .data-grid { display: grid; grid-template-columns: 1fr; gap: 11px; }
    .data-tile {
      position: relative;
      display: grid;
      grid-template-columns: 40px minmax(0, 1fr);
      gap: 13px;
      align-items: center;
      padding: 13px 15px;
      border-radius: var(--radius-sm);
      background: rgba(255, 255, 255, 0.62);
      border: 1px solid rgba(255, 255, 255, 0.7);
      box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.8);
    }
    .data-icon {
      display: grid;
      place-items: center;
      width: 40px;
      height: 40px;
      border-radius: 12px;
      background: linear-gradient(160deg, rgba(240, 220, 166, 0.7), rgba(231, 201, 125, 0.3));
      color: var(--gold-ink);
      box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.85);
    }
    .data-icon svg { width: 20px; height: 20px; }
    .stat-num {
      display: block;
      font-family: var(--serif);
      font-size: clamp(30px, 3.4vw, 42px);
      font-weight: 700;
      line-height: 1;
      letter-spacing: 0.5px;
      background: linear-gradient(120deg, var(--gold-deep), #d6a23a 55%, var(--gold-ink));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      white-space: nowrap;
    }
    .data-label { display: block; margin-top: 5px; color: #5F5550; font-size: 12.5px; font-weight: 700; line-height: 1.2; letter-spacing: 0.3px; }

    /* ---------- JD strip ---------- */
    .jd-strip {
      width: min(1240px, calc(100% - 48px));
      margin: clamp(18px, 2.4vw, 30px) auto 0;
      padding: 18px 22px;
      display: grid;
      grid-template-columns: auto repeat(5, minmax(0, 1fr));
      gap: 12px;
      align-items: center;
    }
    .jd-strip .eyebrow { justify-self: start; }
    .jd-badge {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      min-height: 50px;
      padding: 8px 14px;
      border-radius: 999px;
      border: 1px solid rgba(255, 255, 255, 0.7);
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.66), rgba(239, 216, 222, 0.26));
      color: #4E4641;
      font-size: 14px;
      font-weight: 700;
      text-align: center;
      line-height: 1.25;
      box-shadow: var(--highlight);
      transition: transform 320ms ease, box-shadow 320ms ease;
    }
    .jd-badge:hover { transform: translateY(-3px); box-shadow: 0 18px 30px -20px rgba(185, 138, 45, 0.6), var(--highlight); }
    .jd-badge::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: radial-gradient(circle at 35% 30%, #fff, var(--gold) 75%);
      box-shadow: 0 0 0 3px rgba(231, 201, 125, 0.2);
      flex: none;
    }

    /* ---------- Why Me ---------- */
    .why-grid { display: grid; grid-template-columns: minmax(0, 1.5fr) minmax(330px, 1fr); gap: 24px; }
    .ability-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 18px; }

    .ability-card { position: relative; min-height: 296px; padding: 26px; overflow: hidden; }
    .ability-card::after {
      content: "";
      position: absolute;
      right: -28px;
      bottom: -28px;
      width: 120px;
      height: 120px;
      border-radius: 50%;
      background: radial-gradient(circle at 40% 36%, rgba(240, 220, 166, 0.5), transparent 68%);
    }
    .ability-icon {
      display: grid;
      place-items: center;
      width: 56px;
      height: 56px;
      margin-bottom: 18px;
      border-radius: 18px;
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.85), rgba(240, 220, 166, 0.35));
      border: 1px solid rgba(231, 201, 125, 0.5);
      color: var(--gold-deep);
      box-shadow: 0 14px 30px -16px rgba(185, 138, 45, 0.6), var(--highlight);
    }
    .ability-icon svg { width: 27px; height: 27px; }
    .ability-card h3 { position: relative; z-index: 1; margin: 0 0 7px; font-size: 23px; color: var(--ink); line-height: 1.18; }
    .ability-card .source { position: relative; z-index: 1; display: block; margin-bottom: 15px; color: var(--muted); font-size: 13.5px; font-weight: 700; line-height: 1.45; }

    .ability-metrics { position: relative; z-index: 1; display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 14px; }
    .ability-metrics span, .brand-pill {
      display: inline-flex;
      align-items: center;
      min-height: 28px;
      padding: 0 12px;
      border-radius: 999px;
      background: linear-gradient(180deg, rgba(240, 220, 166, 0.55), rgba(231, 201, 125, 0.28));
      color: var(--gold-ink);
      font-size: 12px;
      font-weight: 800;
      line-height: 1;
      white-space: nowrap;
    }
    .brand-pill { background: linear-gradient(180deg, rgba(239, 216, 222, 0.6), rgba(248, 200, 210, 0.3)); color: #9a5566; }
    .ability-card p { position: relative; z-index: 1; margin: 0; color: #504944; font-size: 14.5px; line-height: 1.78; }

    /* Growth Path — exploration journey map */
    .path-panel { position: relative; min-height: 600px; padding: 28px 28px 30px; overflow: hidden; }
    .path-head { display: flex; align-items: center; justify-content: space-between; gap: 10px; margin: 0 0 8px; }
    .path-head h3 { margin: 0; font-family: var(--serif); color: var(--ink); font-size: 28px; line-height: 1; }
    .path-head .compass {
      display: grid;
      place-items: center;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: rgba(231, 201, 125, 0.16);
      color: var(--gold-deep);
    }
    .path-sub { margin: 0 0 18px; color: var(--muted); font-size: 13px; }

    .path-trail { position: absolute; left: 0; top: 86px; bottom: 18px; width: 86px; pointer-events: none; z-index: 0; }
    .path-trail svg { width: 100%; height: 100%; overflow: visible; }
    .path-trail path { fill: none; stroke: rgba(185, 138, 45, 0.5); stroke-width: 2.4; stroke-dasharray: 2 9; stroke-linecap: round; animation: trailMove 16s linear infinite; }
    @keyframes trailMove { to { stroke-dashoffset: -110; } }

    .path-steps { position: relative; z-index: 2; display: grid; gap: 22px; padding-left: 4px; }
    .path-step { display: grid; grid-template-columns: 78px minmax(0, 1fr); gap: 16px; align-items: center; }
    .path-pin { position: relative; display: grid; place-items: center; justify-self: center; }
    .path-pin .ring {
      width: 70px;
      height: 70px;
      border-radius: 50%;
      padding: 5px;
      background: linear-gradient(160deg, #fff, rgba(231, 201, 125, 0.5));
      box-shadow: 0 16px 30px -16px rgba(185, 138, 45, 0.7), var(--highlight);
    }
    .path-pin .ring .ring-ico {
      display: grid;
      place-items: center;
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: radial-gradient(circle at 38% 32%, #fff, rgba(255, 250, 235, 0.92));
      color: var(--gold-deep);
    }
    .path-pin .ring .ring-ico svg { width: 52%; height: 52%; }
    .path-pin .dot {
      position: absolute;
      right: 2px;
      bottom: 2px;
      width: 18px;
      height: 18px;
      border-radius: 50%;
      background: radial-gradient(circle at 35% 30%, #fff, var(--gold) 80%);
      box-shadow: 0 0 0 4px rgba(255, 255, 255, 0.85), 0 4px 10px rgba(185, 138, 45, 0.4);
    }
    .path-card { padding: 15px 17px; border-radius: var(--radius-sm); background: rgba(255, 255, 255, 0.6); border: 1px solid rgba(255, 255, 255, 0.7); box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.8); }
    .path-card time { display: inline-flex; align-items: center; gap: 6px; color: var(--gold-ink); font-weight: 800; font-size: 14px; }
    .path-card strong { display: block; margin: 5px 0 9px; color: var(--ink); font-size: 16px; line-height: 1.4; }
    .path-tags { display: flex; flex-wrap: wrap; gap: 6px; margin: 0; padding: 0; list-style: none; }
    .path-tags li {
      min-height: 24px;
      padding: 4px 10px;
      border-radius: 999px;
      background: rgba(231, 201, 125, 0.18);
      color: var(--gold-ink);
      font-size: 11.5px;
      font-weight: 700;
    }
    .path-flag {
      position: relative;
      z-index: 2;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      margin: 6px 0 0 18px;
      color: var(--gold-ink);
      font-size: 13px;
      font-weight: 800;
    }

    /* ---------- Core Cases ---------- */
    .case-section {
      width: min(100%, 1480px);
      margin: 0 auto;
      padding: clamp(72px, 9vw, 120px) 0;
      padding-left: max(24px, calc((100vw - 1240px) / 2));
    }
    .case-section .section-head { width: min(1240px, calc(100% - 48px)); margin-right: auto; }

    .case-track {
      display: flex;
      gap: 22px;
      overflow-x: auto;
      overscroll-behavior-x: contain;
      scroll-snap-type: x mandatory;
      padding: 8px max(24px, calc((100vw - 1240px) / 2)) 30px 4px;
    }
    .case-track::-webkit-scrollbar { height: 10px; }
    .case-track::-webkit-scrollbar-track { background: rgba(231, 201, 125, 0.16); border-radius: 999px; }
    .case-track::-webkit-scrollbar-thumb { background: linear-gradient(90deg, rgba(185, 138, 45, 0.5), rgba(231, 201, 125, 0.6)); border-radius: 999px; }

    .case-card { flex: 0 0 min(82vw, 536px); scroll-snap-align: start; min-height: 528px; padding: 28px; overflow: hidden; }
    .case-top { display: flex; align-items: center; justify-content: space-between; gap: 12px; margin-bottom: 18px; }
    .case-label { color: var(--gold-ink); font-size: 12.5px; font-weight: 900; letter-spacing: 0.6px; text-transform: uppercase; }
    .case-chip {
      display: inline-flex;
      align-items: center;
      min-height: 28px;
      padding: 0 13px;
      border-radius: 999px;
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.8), rgba(240, 220, 166, 0.4));
      border: 1px solid rgba(231, 201, 125, 0.5);
      color: var(--gold-ink);
      font-size: 12px;
      font-weight: 800;
    }
    .case-card h3 { margin: 0 0 14px; font-family: var(--serif); font-size: clamp(24px, 2.5vw, 32px); line-height: 1.22; color: #2F2D2C; font-weight: 600; }
    .case-card p { margin: 0; color: #5B534F; font-size: 14.5px; line-height: 1.78; }

    .case-flow { display: grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap: 10px; margin: 24px 0; }
    .case-flow div { position: relative; min-height: 116px; padding: 13px; border-radius: var(--radius-sm); background: rgba(255, 255, 255, 0.6); border: 1px solid rgba(255, 255, 255, 0.7); box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.8); }
    .case-flow div:not(:last-child)::after {
      content: "";
      position: absolute;
      right: -8px;
      top: 50%;
      width: 12px;
      height: 12px;
      border-top: 2px solid rgba(185, 138, 45, 0.5);
      border-right: 2px solid rgba(185, 138, 45, 0.5);
      transform: translateY(-50%) rotate(45deg);
      z-index: 3;
    }
    .case-flow b {
      display: grid;
      place-items: center;
      width: 28px;
      height: 28px;
      margin-bottom: 10px;
      border-radius: 50%;
      background: linear-gradient(160deg, var(--gold), #d6a23a);
      color: #5a3f0a;
      font-size: 13px;
      box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.7);
    }
    .case-flow span { display: block; color: #4D4742; font-size: 13px; font-weight: 700; line-height: 1.45; }

    .mini-diagram { display: grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap: 9px; margin: 24px 0; }
    .mini-diagram span {
      position: relative;
      display: grid;
      place-items: center;
      min-height: 76px;
      padding: 10px;
      border-radius: var(--radius-sm);
      border: 1px dashed rgba(185, 138, 45, 0.4);
      background: rgba(255, 253, 248, 0.55);
      color: var(--gold-ink);
      font-size: 13px;
      font-weight: 800;
      line-height: 1.35;
      text-align: center;
    }

    .case-results { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 14px; margin-top: 22px; }
    .result-box {
      padding: 16px 18px;
      border-radius: var(--radius-sm);
      border: 1px solid rgba(231, 201, 125, 0.4);
      background: linear-gradient(160deg, rgba(240, 220, 166, 0.32), rgba(255, 255, 255, 0.5));
    }
    .result-box strong {
      display: block;
      font-family: var(--serif);
      font-size: 36px;
      font-weight: 700;
      line-height: 1;
      background: linear-gradient(120deg, var(--gold-deep), #d6a23a, var(--gold-ink));
      -webkit-background-clip: text; background-clip: text; color: transparent;
    }
    .result-box span { display: block; margin-top: 7px; color: #6A5553; font-size: 13px; font-weight: 700; }

    /* ---------- Skills star map ---------- */
    .skill-section { display: grid; grid-template-columns: minmax(0, 1fr) minmax(320px, 0.5fr); align-items: center; gap: 26px; }

    .star-map { position: relative; min-height: 600px; padding: 24px; overflow: hidden; }
    .star-lines { position: absolute; inset: 0; width: 100%; height: 100%; z-index: 1; pointer-events: none; }
    .star-lines line {
      stroke: rgba(199, 154, 64, 0.82);
      stroke-width: 2.4;
      stroke-dasharray: 4 5;
      vector-effect: non-scaling-stroke;
      animation: trailMove 22s linear infinite;
    }
    .star-lines circle { fill: rgba(199, 154, 64, 0.95); }

    .skill-node {
      position: absolute;
      z-index: 2;
      display: grid;
      place-items: center;
      width: 138px;
      min-height: 84px;
      padding: 12px;
      border-radius: 18px;
      border: 1px solid rgba(231, 201, 125, 0.6);
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.88), rgba(255, 250, 235, 0.6));
      color: var(--ink);
      box-shadow: 0 0 0 6px rgba(231, 201, 125, 0.1), 0 22px 40px -22px rgba(185, 138, 45, 0.7), var(--highlight);
      font-weight: 800;
      font-size: 14px;
      line-height: 1.3;
      text-align: center;
      transition: transform 260ms cubic-bezier(.2,.7,.2,1), box-shadow 260ms ease, background 260ms ease;
    }
    .skill-node::before {
      content: "✦";
      display: block;
      margin-bottom: 5px;
      color: var(--gold-deep);
      font-size: 18px;
      line-height: 1;
      animation: starTwinkle 2.4s ease-in-out infinite;
    }
    @keyframes starTwinkle {
      0%, 100% { opacity: 0.78; transform: scale(1); filter: drop-shadow(0 0 1px rgba(231, 201, 125, 0.5)); }
      50%      { opacity: 1;    transform: scale(1.16); filter: drop-shadow(0 0 4px rgba(231, 201, 125, 0.85)); }
    }
    .skill-node:hover, .skill-node.is-active {
      transform: translateY(-5px) scale(1.03);
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.95), rgba(240, 220, 166, 0.5));
      box-shadow: 0 0 0 8px rgba(231, 201, 125, 0.16), 0 28px 50px -22px rgba(185, 138, 45, 0.85), var(--highlight);
    }
    .skill-node[data-skill="community"] { left: 7%;  top: 11%; }
    .skill-node[data-skill="hotspot"]   { left: 46%; top: 6%; }
    .skill-node[data-skill="kol"]       { right: 7%; top: 25%; }
    .skill-node[data-skill="content"]   { left: 14%; bottom: 21%; }
    .skill-node[data-skill="data"]      { left: 42%; bottom: 11%; }
    .skill-node[data-skill="team"]      { right: 11%; bottom: 27%; }

    .skill-detail { padding: 28px; min-height: 360px; }
    .skill-detail h3 { margin: 0 0 12px; font-family: var(--serif); color: var(--ink); font-size: 28px; line-height: 1.15; font-weight: 600; }
    .skill-detail p { margin: 0 0 18px; color: #554D48; font-size: 15.5px; line-height: 1.9; }
    .skill-detail ul { display: grid; gap: 11px; margin: 0; padding: 0; list-style: none; }
    .skill-detail li { display: grid; grid-template-columns: 22px minmax(0, 1fr); gap: 8px; color: #4F4843; font-size: 14px; line-height: 1.55; }
    .skill-detail li::before {
      content: "";
      margin-top: 7px;
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: radial-gradient(circle at 35% 30%, #fff, var(--gold) 78%);
      box-shadow: 0 0 0 3px rgba(231, 201, 125, 0.18);
    }
    .skill-icons-row { display: grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap: 10px; margin-top: 20px; }
    .skill-icons-row .ico {
      display: grid;
      place-items: center;
      aspect-ratio: 1;
      border-radius: 14px;
      border: 1px solid rgba(231, 201, 125, 0.4);
      background: linear-gradient(160deg, rgba(255, 255, 255, 0.8), rgba(240, 220, 166, 0.28));
      color: var(--gold-deep);
      box-shadow: var(--highlight);
    }
    .skill-icons-row .ico svg { width: 22px; height: 22px; }

    /* ---------- Footer ---------- */
    .footer { padding: 30px 24px 50px; color: var(--muted); text-align: center; font-size: 13px; }
    .footer .line { display: inline-flex; align-items: center; gap: 10px; flex-wrap: wrap; justify-content: center; }
    .footer .dot { width: 4px; height: 4px; border-radius: 50%; background: var(--gold); }

    /* ---------- Motion preferences ---------- */
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        scroll-behavior: auto !important;
        transition-duration: 0.01ms !important;
      }
      .reveal { opacity: 1; transform: none; }
      .petal, .spark { display: none; }
    }

    /* ---------- Responsive ---------- */
    @media (max-width: 1100px) {
      .nav-inner { flex-wrap: wrap; padding: 10px 0; }
      .nav-links { order: 3; width: 100%; justify-content: flex-start; overflow-x: auto; }
      .hero, .why-grid, .skill-section { grid-template-columns: 1fr; }
      .hero { min-height: 0; }
      .hero-left { min-height: 0; }
      .hero-right { grid-template-columns: minmax(0, 1fr) minmax(0, 1fr); grid-template-rows: auto; }
      .jd-strip { grid-template-columns: repeat(3, minmax(0, 1fr)); }
      .jd-strip .eyebrow { grid-column: 1 / -1; }
      .path-panel { min-height: 0; }
      .star-map { min-height: 560px; }
    }

    @media (max-width: 760px) {
      :root { --nav-h: 98px; --radius: 22px; }
      .site-nav { position: static; }
      .nav-inner, .section, .hero, .jd-strip, .case-section .section-head { width: min(100% - 28px, 1240px); }
      .brand { white-space: normal; }
      .nav-links a { min-height: 32px; padding: 0 9px; font-size: 11.5px; }
      .section { padding: 60px 0; }
      .hero { display: block; padding-top: 20px; }
      .hero-left { min-height: 0; padding: 24px 20px; }
      .hero h1 { font-size: 46px; }
      .hero-sticker { display: none; }
      .hero-right { grid-template-columns: 1fr; margin-top: 16px; }
      .about-card, .data-card, .ability-card, .path-panel, .case-card, .skill-detail { padding: 20px; }
      .jd-strip { margin-top: 16px; grid-template-columns: 1fr; }
      .section-head { display: block; }
      .section-head p { margin-top: 12px; text-align: left; font-size: 14px; }
      .ability-grid, .case-flow, .mini-diagram, .case-results { grid-template-columns: 1fr; }
      .case-flow div:not(:last-child)::after { display: none; }
      .ability-card { min-height: 0; }
      .case-section { padding-left: 14px; }
      .case-track { padding-right: 14px; }
      .case-card { flex-basis: min(88vw, 420px); min-height: 0; }
      .star-map { min-height: 660px; padding: 14px; }
      .star-map::after { width: 150px; right: 4%; }
      .skill-node { width: 120px; min-height: 76px; font-size: 12.5px; }
      .skill-node[data-skill="community"] { left: 3%;  top: 7%; }
      .skill-node[data-skill="hotspot"]   { left: auto; right: 3%; top: 11%; }
      .skill-node[data-skill="kol"]       { right: 6%; top: 33%; }
      .skill-node[data-skill="content"]   { left: 4%;  bottom: 33%; }
      .skill-node[data-skill="data"]      { left: 7%;  bottom: 10%; }
      .skill-node[data-skill="team"]      { right: 4%; bottom: 15%; }
    }
  </style>
</head>
<body>
  <div class="sky" aria-hidden="true"></div>
  <div class="clouds" aria-hidden="true"><span></span><span></span><span></span><span></span></div>
  <div class="ambient" id="ambient" aria-hidden="true"></div>

  <nav class="site-nav" aria-label="Primary navigation">
    <div class="nav-inner">
      <a class="brand" href="#overview" aria-label="Cassie's Content Journey">
        <span class="brand-mark">✦</span>
        <span>Cassie's Content Journey</span>
      </a>
      <div class="nav-links">
        <a href="#overview">Overview</a>
        <a href="#why-me">Why Me</a>
        <a href="#core-cases">Core Cases</a>
        <a href="#skills">Skills</a>
      </div>
    </div>
  </nav>

  <main>
    <!-- Overview -->
    <section class="hero" id="overview">
      <div class="hero-left glass lift reveal">
        <span class="hero-glow" aria-hidden="true"></span>
        <figure class="hero-sticker one floaty" aria-hidden="true"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="m12 3 1.9 5.4L19.5 10l-5.6 1.6L12 17l-1.9-5.4L4.5 10l5.6-1.6L12 3Z"/></svg></figure>
        <figure class="hero-sticker two floaty-slow" aria-hidden="true"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20.4 4.8 13.2a4.4 4.4 0 1 1 6.2-6.2l1 1 1-1a4.4 4.4 0 1 1 6.2 6.2L12 20.4Z"/></svg></figure>
        <div class="hero-copy">
          <span class="eyebrow">Portfolio</span>
          <h1><span>Cassie's</span><span class="accent">Content Journey</span></h1>
          <div class="profile-title">
            <strong>周慧 Cassie</strong>
            <span>河海大学应用经济学硕士在读（2027届）</span>
          </div>
          <div class="hero-focus">用户洞察 × 内容策略 × 圈层传播</div>
          <ul class="intro-list">
            <li>过去的经历横跨品牌营销、达人传播、内容运营与用户行为研究。</li>
            <li>我参与过 OutIn 与 Snow Peak、漫旅、朝日唯品等品牌联动项目，负责达人传播、内容策划与项目推进。</li>
            <li>我独立运营小红书账号，并基于 3 万+海外用户互动数据研究内容特征如何影响用户参与。</li>
          </ul>
          <div class="watch-box">
            <b>我更关注：</b>
            <span>为什么用户愿意停留？为什么愿意讨论？为什么愿意主动创造内容？</span>
          </div>
        </div>
      </div>

      <aside class="hero-right">
        <div class="about-card glass lift reveal" data-delay="1">
          <p class="card-eyebrow">About Me</p>
          <ul class="about-list">
            <li><span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M12 21s-7-5.2-7-10a7 7 0 0 1 14 0c0 4.8-7 10-7 10Z"/><circle cx="12" cy="11" r="2.4"/></svg></span><span>上海</span></li>
            <li><span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M3 8.5 12 4l9 4.5L12 13 3 8.5Z"/><path d="M7 10.6V15c0 1.4 2.6 2.6 5 2.6s5-1.2 5-2.6v-4.4"/></svg></span><span>河海大学<br>应用经济学硕士</span></li>
            <li><span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M3 8.5 12 4l9 4.5L12 13 3 8.5Z"/><path d="M7 10.6V15c0 1.4 2.6 2.6 5 2.6s5-1.2 5-2.6v-4.4"/></svg></span><span>南京林业大学<br>金融工程学士</span></li>
            <li><span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M4 5.5A1.5 1.5 0 0 1 5.5 4H12v16H5.5A1.5 1.5 0 0 1 4 18.5v-13Z"/><path d="M20 5.5A1.5 1.5 0 0 0 18.5 4H12v16h6.5a1.5 1.5 0 0 0 1.5-1.5v-13Z"/></svg></span><span>用户研究方向</span></li>
            <li><span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="5.5" width="18" height="13" rx="2.5"/><path d="m4 7 8 6 8-6"/></svg></span><span>1305593768@qq.com</span></li>
            <li><span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><rect x="7" y="3" width="10" height="18" rx="2.6"/><path d="M11 18h2"/></svg></span><span>18351845295</span></li>
          </ul>
        </div>

        <div class="data-card glass lift reveal" data-delay="2">
          <p class="card-eyebrow">Core Data</p>
          <div class="data-grid" aria-label="核心数据看板">
            <div class="data-tile">
              <span class="data-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="8.5" cy="8" r="3"/><path d="M3.5 19c0-2.9 2.2-5 5-5s5 2.1 5 5"/><path d="M16 6.2a3 3 0 0 1 0 5.6"/><path d="M17.6 14.4c2 .6 3.4 2.2 3.4 4.6"/></svg></span>
              <span class="data-body"><strong class="stat-num" data-count="100" data-suffix="+">100+</strong><span class="data-label">达人合作</span></span>
            </div>
            <div class="data-tile">
              <span class="data-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M12 4 4 7.6l8 3.6 8-3.6L12 4Z"/><path d="M4 12.2l8 3.6 8-3.6"/><path d="M4 16.6l8 3.6 8-3.6"/></svg></span>
              <span class="data-body"><strong class="stat-num" data-count="149" data-suffix="">149</strong><span class="data-label">内容发布</span></span>
            </div>
            <div class="data-tile">
              <span class="data-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="2"/><path d="M8 8a5.5 5.5 0 0 0 0 8"/><path d="M16 8a5.5 5.5 0 0 1 0 8"/><path d="M5 5a9.5 9.5 0 0 0 0 14"/><path d="M19 5a9.5 9.5 0 0 1 0 14"/></svg></span>
              <span class="data-body"><strong class="stat-num" data-count="110" data-suffix="W+">110W+</strong><span class="data-label">传播曝光</span></span>
            </div>
            <div class="data-tile">
              <span class="data-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20.4 4.8 13.2a4.4 4.4 0 1 1 6.2-6.2l1 1 1-1a4.4 4.4 0 1 1 6.2 6.2L12 20.4Z"/></svg></span>
              <span class="data-body"><strong class="stat-num" data-count="3700" data-suffix="+">3700+</strong><span class="data-label">账号粉丝</span></span>
            </div>
            <div class="data-tile">
              <span class="data-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M4 20V11"/><path d="M10 20V5"/><path d="M16 20v-8"/><path d="M3 20h18"/><path d="m16 6 1.6-1.6L19 6"/></svg></span>
              <span class="data-body"><strong class="stat-num" data-count="30000" data-suffix="+">30000+</strong><span class="data-label">研究样本</span></span>
            </div>
          </div>
        </div>
      </aside>
    </section>

    <div class="jd-strip glass reveal" aria-label="JD Match">
      <span class="eyebrow">JD Match</span>
      <span class="jd-badge">KOL合作运营</span>
      <span class="jd-badge">热点内容策划</span>
      <span class="jd-badge">内容破圈传播</span>
      <span class="jd-badge">用户洞察研究</span>
      <span class="jd-badge">社区内容共创</span>
    </div>

    <!-- Why Me -->
    <section class="section" id="why-me">
      <div class="section-head reveal">
        <div>
          <span class="eyebrow">Why Me</span>
          <h2>好的传播，始于理解用户。</h2>
        </div>
        <p>内容传播、热点洞察、用户研究与协作经验，汇成一套从人群理解到内容放大的工作方法。</p>
      </div>

      <div class="why-grid">
        <div class="ability-grid">
          <article class="ability-card glass lift reveal">
            <span class="ability-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="6" cy="12" r="2.4"/><circle cx="18" cy="6" r="2.4"/><circle cx="18" cy="18" r="2.4"/><path d="m8.1 10.9 7.8-3.6"/><path d="m8.1 13.1 7.8 3.6"/></svg></span>
            <h3>内容传播</h3>
            <span class="source">OutIn 品牌增长项目</span>
            <div class="ability-metrics">
              <span>100+ 达人合作</span>
              <span>149 篇内容</span>
              <span>110W+ 曝光</span>
            </div>
            <p>围绕消费场景与用户情绪组织内容，持续优化标题、首图与叙事结构，让传播从被看见走向被讨论。</p>
          </article>

          <article class="ability-card glass lift reveal" data-delay="1">
            <span class="ability-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="m12 3 1.9 5.4L19.5 10l-5.6 1.6L12 17l-1.9-5.4L4.5 10l5.6-1.6L12 3Z"/><path d="M18.5 14.5l.7 2 2 .7-2 .7-.7 2-.7-2-2-.7 2-.7.7-2Z"/></svg></span>
            <h3>热点洞察</h3>
            <span class="source">小红书个人账号运营</span>
            <div class="ability-metrics">
              <span>3700+ 粉丝</span>
              <span>多篇 2W+ 点赞</span>
            </div>
            <p>独立完成选题、内容创作与数据复盘，通过互动率、收藏率和评论内容反推用户兴趣点。</p>
          </article>

          <article class="ability-card glass lift reveal" data-delay="2">
            <span class="ability-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="6"/><path d="m20 20-4.3-4.3"/></svg></span>
            <h3>用户研究</h3>
            <span class="source">硕士研究 / Facebook 数据</span>
            <div class="ability-metrics">
              <span>3W+ 海外用户数据</span>
              <span>用户参与行为</span>
            </div>
            <p>把营销问题转化成研究问题：用户为什么愿意评论、分享，不同内容元素如何影响参与深度。</p>
          </article>

          <article class="ability-card glass lift reveal" data-delay="3">
            <span class="ability-icon"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13.5a3.5 3.5 0 0 0 5 0l2.5-2.5a3.5 3.5 0 0 0-5-5L11 7.5"/><path d="M14 10.5a3.5 3.5 0 0 0-5 0L6.5 13a3.5 3.5 0 0 0 5 5L13 16.5"/></svg></span>
            <h3>跨部门协作</h3>
            <span class="source">品牌联名项目推进</span>
            <div class="ability-metrics">
              <span class="brand-pill">Snow Peak</span>
              <span class="brand-pill">漫旅</span>
              <span class="brand-pill">朝日唯品</span>
            </div>
            <p>同时理解品牌诉求、用户兴趣与传播效果，推动内部团队与合作方完成方案、物料和活动落地。</p>
          </article>
        </div>

        <aside class="path-panel glass lift reveal" data-delay="1">
          <div class="path-head">
            <h3>Growth Path</h3>
            <span class="compass"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="8.5"/><path d="m15.5 8.5-2.2 4.8-4.8 2.2 2.2-4.8 4.8-2.2Z"/></svg></span>
          </div>
          <p class="path-sub">一段持续向内容生态靠近的探索旅程</p>

          <div class="path-trail" aria-hidden="true">
            <svg viewBox="0 0 86 460" preserveAspectRatio="none">
              <path d="M43 8 C 18 70, 70 130, 43 200 C 16 270, 72 330, 43 410"/>
            </svg>
          </div>

          <div class="path-steps">
            <div class="path-step">
              <div class="path-pin">
                <div class="ring"><span class="ring-ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="7.5" width="18" height="12" rx="2.5"/><path d="M8.5 7.5V6a2 2 0 0 1 2-2h3a2 2 0 0 1 2 2v1.5"/><path d="M3 12.5h18"/></svg></span></div>
                <span class="dot"></span>
              </div>
              <div class="path-card">
                <time>2025 · 起点</time>
                <strong>江苏苏豪汇升｜运营助理实习生</strong>
                <ul class="path-tags"><li>项目协同</li><li>多方沟通</li><li>合规管理</li></ul>
              </div>
            </div>
            <div class="path-step">
              <div class="path-pin">
                <div class="ring"><span class="ring-ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M4 10v4a1 1 0 0 0 1 1h2l8 4V5L7 9H5a1 1 0 0 0-1 1Z"/><path d="M18 9a3 3 0 0 1 0 6"/></svg></span></div>
                <span class="dot"></span>
              </div>
              <div class="path-card">
                <time>2026.1 – 2026.3</time>
                <strong>上海应帆数字科技｜财经 MCN 运营实习生</strong>
                <ul class="path-tags"><li>创作者研究</li><li>内容运营</li><li>达人生态</li></ul>
              </div>
            </div>
            <div class="path-step">
              <div class="path-pin">
                <div class="ring"><span class="ring-ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="m12 3 1.9 5.4L19.5 10l-5.6 1.6L12 17l-1.9-5.4L4.5 10l5.6-1.6L12 3Z"/><path d="M18.5 14.5l.7 2 2 .7-2 .7-.7 2-.7-2-2-.7 2-.7.7-2Z"/></svg></span></div>
                <span class="dot"></span>
              </div>
              <div class="path-card">
                <time>2026.4 – 2026.6</time>
                <strong>上海傲绅睿杰｜品牌策划实习生</strong>
                <ul class="path-tags"><li>品牌增长</li><li>达人传播</li><li>品牌联名</li><li>内容增长</li></ul>
              </div>
            </div>
          </div>
          <span class="path-flag"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M6 21V4"/><path d="M6 4h11l-2 3 2 3H6"/></svg>下一站 · 内容生态共创</span>
        </aside>
      </div>
    </section>

    <!-- Core Cases -->
    <section class="case-section" id="core-cases">
      <div class="section-head reveal">
        <div>
          <span class="eyebrow">Core Cases</span>
          <h2>从问题到方法，再到可复盘的结果。</h2>
        </div>
        <p>三个核心案例分别对应达人传播、内容运营与用户研究，呈现从问题、洞察到结果的完整路径。</p>
      </div>

      <div class="case-track" aria-label="横向案例展示">
        <article class="case-card glass lift reveal">
          <div class="case-top">
            <span class="case-label">Case 01 / 达人传播优化</span>
            <span class="case-chip">OutIn</span>
          </div>
          <h3>如何找到真正有转化价值的达人？</h3>
          <p>最初合作方向以泛生活方式达人为主，曝光表现良好，但实际互动与转化有限。</p>
          <div class="case-flow">
            <div><b>1</b><span>发现问题</span></div>
            <div><b>2</b><span>洞察用户</span></div>
            <div><b>3</b><span>调整达人策略</span></div>
            <div><b>4</b><span>传播效果提升</span></div>
          </div>
          <p>复盘评论区后发现，咖啡垂类达人虽然体量更小，但讨论更聚焦于产品体验与购买决策。</p>
          <div class="case-results">
            <div class="result-box"><strong>3000+</strong><span>点赞</span></div>
            <div class="result-box"><strong>800+</strong><span>收藏</span></div>
          </div>
        </article>

        <article class="case-card glass lift reveal" data-delay="1">
          <div class="case-top">
            <span class="case-label">Case 02 / 内容传播规律</span>
            <span class="case-chip">XHS</span>
          </div>
          <h3>为什么有些内容天然适合被分享？</h3>
          <p>高互动内容往往并非信息量最多，而是最能触发用户情绪共鸣。</p>
          <div class="mini-diagram">
            <span>选题逻辑</span>
            <span>内容结构</span>
            <span>情绪触发点</span>
            <span>数据结果</span>
          </div>
          <p>例如“大学生在校创业”比普通经验总结更能引起学生群体兴趣。用户分享的是内容带来的情绪价值。</p>
          <div class="case-results">
            <div class="result-box"><strong>2W+</strong><span>单篇点赞</span></div>
            <div class="result-box"><strong>3700+</strong><span>粉丝沉淀</span></div>
          </div>
        </article>

        <article class="case-card glass lift reveal" data-delay="2">
          <div class="case-top">
            <span class="case-label">Case 03 / 用户行为研究</span>
            <span class="case-chip">Research</span>
          </div>
          <h3>文化差异如何影响用户互动？</h3>
          <p>基于 Facebook 品牌内容与用户互动数据，观察文化元素、内容特征与用户行为之间的关系。</p>
          <div class="mini-diagram">
            <span>研究问题</span>
            <span>分析框架</span>
            <span>研究结论</span>
            <span>策略迁移</span>
          </div>
          <p>文化认同感、内容本土化程度与情绪表达，都会显著影响互动意愿。</p>
          <div class="case-results">
            <div class="result-box"><strong>3W+</strong><span>样本数据</span></div>
            <div class="result-box"><strong>User</strong><span>互动洞察</span></div>
          </div>
        </article>
      </div>
    </section>

    <!-- Skills -->
    <section class="section" id="skills">
      <div class="section-head reveal">
        <div>
          <span class="eyebrow">Skills</span>
          <h2>能力不是星级，而是一张可以连接的星图。</h2>
        </div>
        <p>社区内容工作需要同时连接观察、策划、合作、数据与协作，让每一次传播都有可复盘的判断依据。</p>
      </div>

      <div class="skill-section">
        <div class="star-map glass reveal" aria-label="技能星图">
          <svg class="star-lines" viewBox="0 0 100 100" preserveAspectRatio="none" aria-hidden="true">
            <line x1="14" y1="18" x2="52" y2="13"/>
            <line x1="14" y1="18" x2="86" y2="33"/>
            <line x1="14" y1="18" x2="21" y2="74"/>
            <line x1="14" y1="18" x2="49" y2="84"/>
            <line x1="14" y1="18" x2="84" y2="75"/>
            <line x1="52" y1="13" x2="86" y2="33"/>
            <line x1="52" y1="13" x2="21" y2="74"/>
            <line x1="52" y1="13" x2="49" y2="84"/>
            <line x1="52" y1="13" x2="84" y2="75"/>
            <line x1="86" y1="33" x2="21" y2="74"/>
            <line x1="86" y1="33" x2="49" y2="84"/>
            <line x1="86" y1="33" x2="84" y2="75"/>
            <line x1="21" y1="74" x2="49" y2="84"/>
            <line x1="21" y1="74" x2="84" y2="75"/>
            <line x1="49" y1="84" x2="84" y2="75"/>
            <circle cx="14" cy="18" r="0.9"/><circle cx="52" cy="13" r="0.9"/><circle cx="86" cy="33" r="0.9"/>
            <circle cx="21" cy="74" r="0.9"/><circle cx="49" cy="84" r="0.9"/><circle cx="84" cy="75" r="0.9"/>
          </svg>
          <button class="skill-node is-active" type="button" data-skill="community">玩家社区观察</button>
          <button class="skill-node" type="button" data-skill="hotspot">热点敏感度</button>
          <button class="skill-node" type="button" data-skill="kol">KOL合作</button>
          <button class="skill-node" type="button" data-skill="content">内容策划</button>
          <button class="skill-node" type="button" data-skill="data">数据分析</button>
          <button class="skill-node" type="button" data-skill="team">跨团队协作</button>
        </div>

        <aside class="skill-detail glass reveal" data-delay="1" aria-live="polite">
          <h3 id="skill-title">玩家社区观察</h3>
          <p id="skill-desc">我习惯通过评论区、二创内容与用户讨论理解社区情绪，先看用户为什么在某个内容下停留，再判断选题是否值得放大。</p>
          <ul id="skill-proof">
            <li>对应小红书账号内容复盘</li>
            <li>对应 Facebook 用户互动研究</li>
            <li>适合观察玩家社区创作动机</li>
          </ul>
          <div class="skill-icons-row" aria-hidden="true">
            <span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="6"/><path d="m20 20-4.3-4.3"/></svg></span>
            <span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="m12 3 1.9 5.4L19.5 10l-5.6 1.6L12 17l-1.9-5.4L4.5 10l5.6-1.6L12 3Z"/></svg></span>
            <span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M4 20s2-1 4-1 3 1 5 1 4-1 4-1"/><path d="M14.5 5.5 18 9l-7.5 7.5L7 17l.5-3.5L14.5 5.5Z"/></svg></span>
            <span class="ico"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20.4 4.8 13.2a4.4 4.4 0 1 1 6.2-6.2l1 1 1-1a4.4 4.4 0 1 1 6.2 6.2L12 20.4Z"/></svg></span>
          </div>
        </aside>
      </div>
    </section>

  </main>

  <footer class="footer">
    <span class="line">
      <span>周慧 Cassie</span><span class="dot"></span>
      <span>内容营销作品集</span><span class="dot"></span>
      <span>用户洞察 × 内容策略 × 圈层传播</span>
    </span>
  </footer>

  <script>
    (function () {
      var reduceMotion = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;

      /* Ambient petals + golden particles */
      var ambient = document.getElementById("ambient");
      if (ambient && !reduceMotion) {
        var frag = document.createDocumentFragment();
        for (var i = 0; i < 14; i++) {
          var p = document.createElement("span");
          p.className = "petal" + (i % 3 === 0 ? " gold" : "");
          p.style.left = (Math.random() * 100).toFixed(2) + "%";
          var dur = (12 + Math.random() * 12).toFixed(2);
          p.style.animationDuration = dur + "s";
          p.style.animationDelay = (-Math.random() * dur).toFixed(2) + "s";
          var s = (0.7 + Math.random() * 0.8).toFixed(2);
          p.style.transform = "scale(" + s + ")";
          frag.appendChild(p);
        }
        for (var j = 0; j < 16; j++) {
          var sp = document.createElement("span");
          sp.className = "spark";
          sp.style.left = (Math.random() * 100).toFixed(2) + "%";
          sp.style.bottom = (-10 + Math.random() * 10) + "%";
          var d2 = (10 + Math.random() * 14).toFixed(2);
          sp.style.animationDuration = d2 + "s, " + (2 + Math.random() * 2).toFixed(2) + "s";
          sp.style.animationDelay = (-Math.random() * d2).toFixed(2) + "s, 0s";
          frag.appendChild(sp);
        }
        ambient.appendChild(frag);
      }

      /* Parallax sky on scroll */
      var sky = document.querySelector(".sky");
      if (sky && !reduceMotion) {
        var ticking = false;
        window.addEventListener("scroll", function () {
          if (ticking) return;
          ticking = true;
          requestAnimationFrame(function () {
            sky.style.transform = "translate3d(0," + (window.scrollY * 0.12).toFixed(1) + "px,0)";
            ticking = false;
          });
        }, { passive: true });
      }

      /* Nav active state */
      var navLinks = Array.prototype.slice.call(document.querySelectorAll(".nav-links a"));
      var sections = navLinks.map(function (link) { return document.querySelector(link.getAttribute("href")); }).filter(Boolean);
      var navObserver = new IntersectionObserver(function (entries) {
        entries.forEach(function (entry) {
          if (!entry.isIntersecting) return;
          navLinks.forEach(function (link) {
            link.classList.toggle("is-active", link.getAttribute("href") === "#" + entry.target.id);
          });
        });
      }, { rootMargin: "-35% 0px -55% 0px", threshold: 0.01 });
      sections.forEach(function (section) { navObserver.observe(section); });

      /* Reveal on scroll */
      var revealObserver = new IntersectionObserver(function (entries) {
        entries.forEach(function (entry) {
          if (entry.isIntersecting) {
            entry.target.classList.add("is-visible");
            revealObserver.unobserve(entry.target);
          }
        });
      }, { rootMargin: "0px 0px -8% 0px", threshold: 0.1 });
      document.querySelectorAll(".reveal").forEach(function (node) { revealObserver.observe(node); });

      /* Count-up for core data */
      function animateCount(el) {
        var target = parseFloat(el.getAttribute("data-count")) || 0;
        var suffix = el.getAttribute("data-suffix") || "";
        var dur = 1500, start = null;
        function step(ts) {
          if (start === null) start = ts;
          var t = Math.min((ts - start) / dur, 1);
          var eased = 1 - Math.pow(1 - t, 3);
          var val = Math.round(target * eased);
          el.textContent = val.toLocaleString("en-US") + suffix;
          if (t < 1) requestAnimationFrame(step);
          else el.textContent = target.toLocaleString("en-US") + suffix;
        }
        requestAnimationFrame(step);
      }
      var statObserver = new IntersectionObserver(function (entries) {
        entries.forEach(function (entry) {
          if (!entry.isIntersecting) return;
          if (!reduceMotion) animateCount(entry.target);
          statObserver.unobserve(entry.target);
        });
      }, { threshold: 0.6 });
      document.querySelectorAll(".stat-num").forEach(function (el) { statObserver.observe(el); });

      /* Skill star map interactions */
      var skillData = {
        community: { title: "玩家社区观察", desc: "我习惯通过评论区、二创内容与用户讨论理解社区情绪，先看用户为什么在某个内容下停留，再判断选题是否值得放大。", proof: ["对应小红书账号内容复盘", "对应 Facebook 用户互动研究", "适合观察玩家社区创作动机"] },
        hotspot:   { title: "热点敏感度", desc: "持续关注平台热点变化与用户兴趣迁移，把热门话题转译成具体内容角度，而不是只追随热词。", proof: ["多篇小红书 2W+ 点赞内容", "围绕消费场景与情绪价值设计选题", "能够快速判断社区讨论的可延展方向"] },
        kol:       { title: "KOL合作", desc: "具备达人筛选、合作沟通、内容审核、上线跟进与数据复盘经验，关注达人与目标用户之间的信任关系。", proof: ["月均推进 100+ 达人合作", "优质内容 3000+ 点赞、800+ 收藏", "通过垂类匹配提升传播价值"] },
        content:   { title: "内容策划", desc: "能够从用户需求出发设计传播内容，把标题、首图、内容结构与互动触发点放在同一个策略链路里看。", proof: ["累计推动 149 篇内容发布", "OutIn 单平台传播 110W+", "个人账号验证可分享内容结构"] },
        data:      { title: "数据分析", desc: "具备用户行为研究与内容数据分析能力，能把阅读、互动、收藏、评论和研究数据转化为下一轮内容判断。", proof: ["3W+ 海外用户行为样本", "Facebook 品牌内容互动研究", "CTR、互动率、收藏率复盘经验"] },
        team:      { title: "跨团队协作", desc: "有品牌联名和多方沟通经验，能在合作方、内部团队和内容目标之间推进项目落地。", proof: ["Snow Peak、漫旅、朝日唯品联名项目", "方案沟通、物料筹备、活动落地", "兼顾品牌诉求与用户兴趣"] }
      };
      var skillTitle = document.querySelector("#skill-title");
      var skillDesc = document.querySelector("#skill-desc");
      var skillProof = document.querySelector("#skill-proof");
      document.querySelectorAll(".skill-node").forEach(function (node) {
        node.addEventListener("click", function () {
          document.querySelectorAll(".skill-node").forEach(function (item) { item.classList.remove("is-active"); });
          node.classList.add("is-active");
          var data = skillData[node.dataset.skill];
          if (!data) return;
          skillTitle.textContent = data.title;
          skillDesc.textContent = data.desc;
          skillProof.innerHTML = data.proof.map(function (item) { return "<li>" + item + "</li>"; }).join("");
        });
      });
    })();
  </script>
</body>
</html>
