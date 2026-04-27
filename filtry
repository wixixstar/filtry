<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Wydawnictwo Filtry — Hyper Editorial One Page</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Montserrat:wght@700;800;900&family=Playfair+Display:wght@600;700;800&display=swap" rel="stylesheet">
  <script src="https://unpkg.com/@studio-freight/lenis@1.0.42/dist/lenis.min.js"></script>

  <style>
    :root {
      --ink: #0f0f0d;
      --paper: #f4ecdf;
      --paper-2: #e7ddcd;
      --cream: #fff7ea;
      --muted: #756e63;
      --gold: #d8a846;
      --red: #983226;
      --green: #163b32;
      --blue: #172d44;
      --line: rgba(15,15,13,.14);
      --glass: rgba(255,255,255,.28);
      --shadow: 0 36px 120px rgba(15,15,13,.22);
      --mx: 50%;
      --my: 50%;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: auto; }

    body {
      font-family: "Inter", sans-serif;
      background: var(--paper);
      color: var(--ink);
      overflow-x: hidden;
      cursor: none;
    }

    body.menu-open { overflow: hidden; }
    a, button { cursor: none; }
    button { font: inherit; color: inherit; background: none; border: 0; }
    a { color: inherit; text-decoration: none; }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      z-index: -5;
      background:
        radial-gradient(circle at var(--mx) var(--my), rgba(216,168,70,.38), transparent 17vw),
        radial-gradient(circle at 10% 15%, rgba(152,50,38,.18), transparent 26vw),
        radial-gradient(circle at 88% 76%, rgba(22,59,50,.22), transparent 32vw),
        linear-gradient(135deg, #f8f0e1 0%, #e9decd 58%, #f5eee3 100%);
      transition: background .2s ease;
    }

    body::after {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      opacity: .25;
      z-index: 100;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 260 260' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.82' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.4'/%3E%3C/svg%3E");
      mix-blend-mode: multiply;
    }

    .cursor {
      position: fixed;
      left: 0;
      top: 0;
      z-index: 999;
      width: 22px;
      height: 22px;
      border: 1px solid rgba(15,15,13,.68);
      border-radius: 50%;
      pointer-events: none;
      transform: translate(-50%, -50%);
      mix-blend-mode: difference;
      background: rgba(255,255,255,.22);
      transition: width .25s ease, height .25s ease, background .25s ease;
    }

    .cursor.big { width: 72px; height: 72px; background: rgba(255,255,255,.08); }

    .nav {
      position: fixed;
      top: 20px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 80;
      width: min(1160px, calc(100% - 28px));
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      padding: 10px 12px 10px 18px;
      border: 1px solid rgba(255,255,255,.45);
      border-radius: 999px;
      background: rgba(244,236,223,.55);
      backdrop-filter: blur(22px);
      box-shadow: 0 18px 60px rgba(0,0,0,.1);
    }

    .logo { display: inline-flex; align-items: center; gap: 10px; font-weight: 950; letter-spacing: -.055em; }
    .logo-mark {
      width: 36px; height: 36px; border-radius: 50%;
      background: conic-gradient(from 120deg, var(--green), var(--gold), var(--red), var(--blue), var(--green));
      position: relative; animation: rotate 8s linear infinite;
    }
    .logo-mark::after { content:""; position:absolute; inset:9px; border-radius:inherit; background:var(--paper); }

    .menu-trigger {
      position: relative;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      padding: 12px 17px;
      border-radius: 999px;
      background: var(--ink);
      color: var(--paper);
      font-size: 12px;
      font-weight: 950;
      letter-spacing: .08em;
      text-transform: uppercase;
      overflow: hidden;
    }

    .menu-trigger::after {
      content: "";
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--gold);
      transition: transform .35s ease;
    }

    .menu-trigger:hover::after { transform: scale(1.8); }

    .menu-panel {
      position: fixed;
      inset: 0;
      z-index: 70;
      min-height: 100vh;
      padding: 110px 6vw 44px;
      background: rgba(15,15,13,.96);
      color: var(--paper);
      transform: translateY(-104%);
      transition: transform .8s cubic-bezier(.76,0,.24,1);
      overflow: hidden;
    }

    .menu-panel.open { transform: translateY(0); }

    .menu-panel::before {
      content: "MENU";
      position: absolute;
      right: -3vw;
      bottom: -5vw;
      font-family: "Montserrat", sans-serif;
      font-weight: 900;
      font-size: 25vw;
      line-height: .8;
      letter-spacing: -.12em;
      color: rgba(255,255,255,.035);
      pointer-events: none;
    }

    .menu-grid {
      position: relative;
      z-index: 1;
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 52px;
      height: 100%;
      align-items: end;
    }

    .menu-links {
      display: grid;
      gap: 10px;
      counter-reset: menu;
    }

    .menu-links a {
      counter-increment: menu;
      position: relative;
      display: grid;
      grid-template-columns: 72px 1fr;
      align-items: baseline;
      padding: 14px 0;
      border-bottom: 1px solid rgba(244,236,223,.13);
      transition: transform .3s ease, color .3s ease;
    }

    .menu-links a::before {
      content: "0" counter(menu);
      color: var(--gold);
      font-size: 12px;
      font-weight: 950;
      letter-spacing: .18em;
    }

    .menu-links strong {
      font-family: "Playfair Display", serif;
      font-size: clamp(44px, 7vw, 104px);
      line-height: .92;
      letter-spacing: -.075em;
      font-weight: 800;
    }

    .menu-links a:hover { transform: translateX(18px); color: var(--gold); }

    .menu-side {
      display: grid;
      gap: 20px;
    }

    .menu-image {
      min-height: 390px;
      border-radius: 40px;
      overflow: hidden;
      background:
        linear-gradient(rgba(15,15,13,.1), rgba(15,15,13,.38)),
        url('https://images.unsplash.com/photo-1526243741027-444d633d7365?auto=format&fit=crop&w=1200&q=80') center/cover;
      box-shadow: 0 40px 110px rgba(0,0,0,.42);
    }

    .menu-note {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }

    .menu-note div {
      min-height: 130px;
      padding: 20px;
      border-radius: 26px;
      border: 1px solid rgba(244,236,223,.14);
      background: rgba(255,255,255,.055);
    }

    .menu-note span {
      display: block;
      color: var(--gold);
      font-size: 11px;
      font-weight: 950;
      letter-spacing: .14em;
      text-transform: uppercase;
    }

    .menu-note p {
      margin-top: 12px;
      color: rgba(244,236,223,.68);
      line-height: 1.5;
      font-size: 14px;
    }

    .noise-title {
      position: fixed;
      left: 18px;
      bottom: 16px;
      z-index: 20;
      writing-mode: vertical-rl;
      color: rgba(15,15,13,.36);
      font-size: 10px;
      font-weight: 900;
      letter-spacing: .2em;
      text-transform: uppercase;
      pointer-events: none;
    }

    .scroll-meter {
      position: fixed;
      right: 18px;
      top: 50%;
      transform: translateY(-50%);
      width: 3px;
      height: 160px;
      background: rgba(15,15,13,.12);
      z-index: 30;
      border-radius: 999px;
      overflow: hidden;
    }
    .scroll-meter span { display:block; width:100%; height:0%; background:var(--red); border-radius:inherit; }

    .hero {
      min-height: 118vh;
      padding: 140px 6.5vw 100px;
      display: grid;
      grid-template-columns: 1fr .92fr;
      gap: 64px;
      align-items: center;
      position: relative;
      overflow: hidden;
      clip-path: polygon(0 0,100% 0,100% 90%,64% 100%,0 93%);
    }

    .hero::after {
      content:"";
      position:absolute;
      inset: 12% 48% auto auto;
      width: 38vw;
      height: 38vw;
      border: 1px solid rgba(15,15,13,.12);
      border-radius: 42% 58% 64% 36% / 42% 32% 68% 58%;
      animation: blob 15s ease-in-out infinite;
      pointer-events:none;
    }

    .eyebrow {
      width: fit-content;
      display:inline-flex; align-items:center; gap:10px;
      padding: 9px 13px; margin-bottom: 24px;
      border:1px solid var(--line); border-radius:999px;
      background:rgba(255,255,255,.32); backdrop-filter: blur(15px);
      color:var(--muted); font-size:12px; font-weight:900; text-transform:uppercase; letter-spacing:.12em;
    }
    .pulse { width:8px; height:8px; border-radius:50%; background:var(--red); box-shadow:0 0 0 0 rgba(152,50,38,.45); animation:pulse 1.8s infinite; }

    h1 {
      max-width: 980px;
      font-family:"Playfair Display", serif;
      font-size: clamp(58px, 10vw, 160px);
      line-height:.82;
      letter-spacing:-.08em;
      overflow: visible;
    }
    h1 span { display:block; }
    h1 .cut { color:var(--red); transform: translateX(4.5vw); }
    h1 .thin {
      font-family:"Montserrat", sans-serif;
      font-weight:900;
      font-size: clamp(16px, .18em, 28px);
      line-height: 1.15;
      letter-spacing:.01em;
      text-transform:uppercase;
      margin-top: 24px;
      color:rgba(15,15,13,.64);
    }

    .hero-copy { max-width: 650px; margin-top:30px; color:rgba(15,15,13,.7); font-size:clamp(18px,2vw,24px); line-height:1.55; letter-spacing:-.035em; }
    .hero-actions { display:flex; flex-wrap:wrap; gap:14px; margin-top:38px; }
    .btn { min-height:54px; padding:0 23px; border-radius:999px; border:1px solid var(--line); display:inline-flex; align-items:center; justify-content:center; gap:9px; font-weight:950; transition:.28s ease; }
    .btn.primary { background:var(--ink); color:var(--paper); box-shadow:0 20px 55px rgba(15,15,13,.2); }
    .btn:hover { transform:translateY(-5px); box-shadow:0 25px 70px rgba(15,15,13,.18); }

    .hero-visual {
      position:relative;
      min-height: 660px;
      transform-style:preserve-3d;
      perspective:1200px;
    }

    .video-frame {
      position:absolute;
      inset: 40px 0 auto auto;
      width:min(520px, 78vw);
      height: 560px;
      border-radius: 44px;
      overflow:hidden;
      box-shadow:var(--shadow);
      transform: rotate(4deg);
      background:
        linear-gradient(rgba(15,15,13,.16), rgba(15,15,13,.22)),
        url('https://images.unsplash.com/photo-1526243741027-444d633d7365?auto=format&fit=crop&w=1200&q=80') center/cover;
      isolation:isolate;
    }

    .video-frame::before {
      content:"MIEJSCE NA VIDEO / intro wydawnicze";
      position:absolute; left:24px; top:24px; z-index:2;
      padding:9px 12px; border-radius:999px;
      background:rgba(255,255,255,.18); color:#fff;
      font-size:10px; font-weight:950; letter-spacing:.14em; text-transform:uppercase;
      backdrop-filter:blur(14px);
    }
    .video-frame::after {
      content:"▶";
      position:absolute; left:50%; top:50%; transform:translate(-50%,-50%);
      width:86px; height:86px; border-radius:50%; display:grid; place-items:center;
      background:rgba(255,255,255,.22); color:#fff; font-size:32px;
      backdrop-filter: blur(12px); border:1px solid rgba(255,255,255,.28);
    }

    .floating-card {
      position:absolute;
      left: -18px;
      bottom: 60px;
      width: 280px;
      min-height: 310px;
      padding: 24px;
      border-radius: 34px;
      background: var(--green);
      color: var(--paper);
      box-shadow: var(--shadow);
      transform: rotate(-9deg) translateZ(80px);
      animation: float 6s ease-in-out infinite;
    }
    .floating-card small { font-size:11px; font-weight:950; letter-spacing:.17em; text-transform:uppercase; opacity:.72; }
    .floating-card strong { display:block; margin-top:80px; font-family:"Playfair Display",serif; font-size:38px; line-height:1; letter-spacing:-.055em; }

    .sphere {
      position:absolute;
      width: 150px;
      height: 150px;
      right: -18px;
      bottom: 22px;
      border-radius:50%;
      background: radial-gradient(circle at 32% 26%, #fff7d8 0 8%, #d8a846 22%, #983226 58%, #0f0f0d 100%);
      box-shadow: 0 38px 80px rgba(15,15,13,.22);
      animation: float 5.2s ease-in-out infinite reverse;
    }

    .marquee {
      position:relative; z-index:2;
      display:flex; overflow:hidden; border-block:1px solid var(--line);
      background:var(--ink); color:var(--paper);
      transform: rotate(-1.3deg) scaleX(1.04);
    }
    .marquee-track { display:flex; min-width:100%; animation:marquee 24s linear infinite; }
    .marquee span { padding:22px 30px; white-space:nowrap; font-family:"Playfair Display",serif; font-size:clamp(30px,4.4vw,70px); font-weight:800; letter-spacing:-.065em; }

    .container { width:min(1180px, calc(100% - 40px)); margin:0 auto; }
    .section-pad { padding: 130px 0; }
    .section-head { display:grid; grid-template-columns:.72fr 1.28fr; gap:54px; align-items:start; margin-bottom:64px; }
    .kicker { color:var(--red); font-size:12px; font-weight:950; text-transform:uppercase; letter-spacing:.18em; }
    h2 { font-family:"Playfair Display",serif; font-size:clamp(44px,6vw,92px); line-height:.96; letter-spacing:-.065em; overflow: visible; }
    .lead { color:rgba(15,15,13,.68); font-size:clamp(18px,2vw,24px); line-height:1.55; letter-spacing:-.035em; }

    .diagonal-section {
      padding: 160px 0 180px;
      background: var(--cream);
      clip-path: polygon(0 7%, 100% 0, 100% 91%, 0 100%);
      position:relative;
    }
    .diagonal-section::before {
      content:"";
      position:absolute; inset: 8% auto auto -11vw;
      width:32vw; height:32vw; border-radius:50%;
      background:rgba(216,168,70,.18); filter:blur(18px);
    }

    .asym-grid {
      display:grid;
      grid-template-columns: 1.15fr .85fr;
      grid-template-rows: auto auto;
      gap:18px;
    }
    .feature-card {
      position:relative;
      min-height: 380px;
      padding:34px;
      border:1px solid var(--line);
      border-radius: 38px;
      background:rgba(255,255,255,.42);
      backdrop-filter:blur(22px);
      box-shadow:0 22px 80px rgba(15,15,13,.08);
      overflow:hidden;
      transition:.35s ease;
    }
    .feature-card:hover { transform: translateY(-12px) rotate(-.8deg); box-shadow:0 36px 100px rgba(15,15,13,.14); }
    .feature-card.wide { grid-row: span 2; min-height: 760px; background: var(--ink); color:var(--paper); }
    .feature-card.photo {
      background: linear-gradient(rgba(15,15,13,.18), rgba(15,15,13,.32)), url('https://images.unsplash.com/photo-1519682337058-a94d519337bc?auto=format&fit=crop&w=1200&q=80') center/cover;
      color:#fff;
    }
    .feature-card .num { font-family:"Montserrat",sans-serif; font-size:64px; color:rgba(216,168,70,.78); letter-spacing:-.08em; line-height:1; font-weight:900; }
    .feature-card h3 { margin-top:34px; font-size:clamp(26px,3vw,48px); line-height:1.04; letter-spacing:-.055em; }
    .feature-card p { margin-top:18px; max-width:560px; color:rgba(117,110,99,.92); line-height:1.65; font-weight:550; }
    .feature-card.wide p, .feature-card.photo p { color:rgba(255,255,255,.72); }
    .feature-card.wide h3 { font-family:"Playfair Display",serif; font-size:clamp(50px,6.4vw,96px); line-height:.95; }

    .orbit {
      position:absolute;
      right: -70px;
      bottom: -80px;
      width: 330px;
      height: 330px;
      border-radius:50%;
      border:1px solid rgba(255,255,255,.18);
      animation: rotate 12s linear infinite;
    }
    .orbit::before, .orbit::after { content:""; position:absolute; border-radius:50%; background:var(--gold); }
    .orbit::before { width:34px; height:34px; left:40px; top:42px; }
    .orbit::after { width:18px; height:18px; right:20px; bottom:70px; background:var(--red); }

    .origin {
      min-height: 112vh;
      display:grid;
      align-items:center;
      background: var(--ink);
      color:var(--paper);
      overflow:hidden;
      clip-path: polygon(0 0, 100% 8%, 100% 100%, 0 91%);
    }
    .origin::before {
      content:"FILTRY";
      position:absolute; left:-4vw; bottom:-4vw;
      font-family:"Montserrat",sans-serif; font-size:22vw; font-weight:900; line-height:.78; letter-spacing:-.12em;
      color:rgba(255,255,255,.04); pointer-events:none;
    }
    .origin-grid { display:grid; grid-template-columns: .95fr 1.05fr; gap:72px; align-items:center; }
    .map-card {
      position:relative;
      min-height:620px;
      border-radius: 48px;
      overflow:hidden;
      box-shadow:var(--shadow);
      background:
        linear-gradient(135deg, rgba(15,15,13,.1), rgba(15,15,13,.72)),
        url('https://images.unsplash.com/photo-1518005020951-eccb494ad742?auto=format&fit=crop&w=1200&q=80') center/cover;
      transform: rotate(-2deg);
    }
    .map-card::after {
      content:"Warszawskie Filtry / metafora selekcji";
      position:absolute; left:28px; bottom:28px;
      max-width:360px;
      font-family:"Playfair Display",serif; font-size:44px; line-height:1; letter-spacing:-.055em;
    }
    .pin { position:absolute; left:52%; top:45%; width:24px; height:24px; border-radius:50%; background:var(--red); box-shadow:0 0 0 18px rgba(152,50,38,.18); animation:pulse 1.8s infinite; }

    .timeline { display:grid; gap:18px; }
    .timeline-item { display:grid; grid-template-columns:86px 1fr; gap:24px; padding:23px; border:1px solid rgba(255,255,255,.13); border-radius:28px; background:rgba(255,255,255,.055); backdrop-filter:blur(16px); }
    .year { font-family:"Montserrat",sans-serif; font-size:24px; color:var(--gold); letter-spacing:-.04em; font-weight:900; }
    .timeline-item h3 { font-size:21px; letter-spacing:-.045em; }
    .timeline-item p { margin-top:7px; color:rgba(244,236,223,.68); line-height:1.55; }

    .horizontal-wrap { height: 420vh; position:relative; background:var(--paper-2); }
    .horizontal-sticky { position:sticky; top:0; height:100vh; overflow:hidden; display:flex; align-items:center; }
    .horizontal-track { display:flex; gap:28px; padding-left:7vw; will-change:transform; }
    .panel {
      flex:0 0 min(820px, 84vw);
      min-height:72vh;
      border-radius: 48px;
      padding:44px;
      display:flex; flex-direction:column; justify-content:space-between;
      box-shadow:var(--shadow); overflow:hidden; position:relative;
    }
    .panel::before { content:""; position:absolute; inset:0; background:radial-gradient(circle at 80% 20%, rgba(255,255,255,.28), transparent 31%); }
    .panel::after { content:""; position:absolute; right:-10%; bottom:-20%; width:40%; height:55%; border-radius:50%; background:rgba(255,255,255,.1); filter:blur(3px); }
    .panel > * { position:relative; z-index:1; }
    .panel .tag { width:fit-content; padding:9px 12px; border-radius:999px; background:rgba(255,255,255,.2); font-size:11px; font-weight:950; letter-spacing:.13em; text-transform:uppercase; }
    .panel h3 { max-width:650px; font-family:"Playfair Display",serif; font-size:clamp(48px,6.2vw,92px); line-height:.94; letter-spacing:-.065em; }
    .panel p { max-width:560px; font-size:18px; line-height:1.6; opacity:.78; margin-top: 24px; }
    .panel.dark { background:var(--ink); color:var(--paper); }
    .panel.green { background:var(--green); color:var(--paper); }
    .panel.red { background:var(--red); color:var(--paper); }
    .panel.gold { background:var(--gold); color:var(--ink); }
    .panel.photo-2 { background: linear-gradient(rgba(15,15,13,.24), rgba(15,15,13,.58)), url('https://images.unsplash.com/photo-1524995997946-a1c2e315a42f?auto=format&fit=crop&w=1400&q=80') center/cover; color:#fff; }

    .cinema {
      min-height: 130vh;
      padding: 150px 0;
      background: #090908;
      color:var(--paper);
      position:relative;
      overflow:hidden;
      clip-path: polygon(0 4%, 100% 0, 100% 96%, 0 100%);
    }
    .cinema-frame {
      width:min(1180px, calc(100% - 40px));
      height: min(72vh, 720px);
      margin: 70px auto 0;
      border-radius: 48px;
      overflow:hidden;
      position:relative;
      box-shadow: 0 50px 130px rgba(0,0,0,.55);
      background:
        linear-gradient(120deg, rgba(9,9,8,.16), rgba(9,9,8,.78)),
        url('https://images.unsplash.com/photo-1495020689067-958852a7765e?auto=format&fit=crop&w=1600&q=80') center/cover;
      transform-origin:center;
      will-change:transform;
    }
    .cinema-frame::before { content:"VIDEO PLACEHOLDER / proces redakcyjny / rozmowy z autorami"; position:absolute; left:30px; top:30px; padding:10px 13px; border-radius:999px; background:rgba(255,255,255,.15); font-size:11px; font-weight:950; letter-spacing:.13em; text-transform:uppercase; backdrop-filter:blur(14px); }
    .cinema-frame::after { content:"PRESS PLAY"; position:absolute; left:50%; top:50%; transform:translate(-50%,-50%); width:150px; height:150px; border-radius:50%; display:grid; place-items:center; border:1px solid rgba(255,255,255,.34); background:rgba(255,255,255,.08); backdrop-filter:blur(15px); font-size:12px; font-weight:950; letter-spacing:.2em; }

    .manifesto { padding: 150px 0; background:#f8f2e8; }
    .manifesto-grid { display:grid; grid-template-columns: 1fr 1fr; gap:20px; }
    .quote { grid-row:span 2; min-height:650px; padding:46px; border-radius:48px; background:var(--ink); color:var(--paper); display:flex; flex-direction:column; justify-content:space-between; overflow:hidden; position:relative; }
    .quote::after { content:"“"; position:absolute; top:-80px; right:18px; font-family:"Playfair Display",serif; font-size:320px; color:rgba(255,255,255,.08); }
    .quote h2 { font-size:clamp(50px,6.8vw,100px); line-height: .96; }
    .quote p { color:rgba(244,236,223,.72); font-size:19px; line-height:1.65; }
    .mini { min-height:315px; padding:36px; border-radius:38px; border:1px solid var(--line); background:rgba(255,255,255,.58); overflow:hidden; position:relative; }
    .mini h3 { font-size:30px; letter-spacing:-.055em; }
    .mini p { margin-top:16px; color:var(--muted); line-height:1.65; }
    .mini::after { content:""; position:absolute; right:-50px; bottom:-70px; width:180px; height:180px; border-radius:44% 56% 63% 37%; background:rgba(216,168,70,.18); }

    .stats { padding: 120px 0 150px; }
    .stat-grid { display:grid; grid-template-columns:repeat(4,1fr); border:1px solid var(--line); border-radius:48px; overflow:hidden; background:rgba(255,255,255,.28); backdrop-filter:blur(20px); }
    .stat { min-height:230px; padding:34px; border-right:1px solid var(--line); }
    .stat:last-child { border-right:0; }
    .stat strong { display:block; font-family:"Montserrat",sans-serif; font-size:60px; letter-spacing:-.06em; line-height:1; font-weight:900; }
    .stat span { display:block; margin-top:18px; color:var(--muted); font-weight:750; line-height:1.45; }

    .final { min-height:110vh; padding:150px 7vw 80px; display:flex; align-items:center; justify-content:center; text-align:center; background:var(--ink); color:var(--paper); overflow:hidden; position:relative; }
    .final::before { content:""; position:absolute; width:72vw; height:72vw; border-radius:50%; border:1px solid rgba(255,255,255,.08); animation:rotate 30s linear infinite; }
    .final::after { content:""; position:absolute; width:32vw; height:32vw; border-radius:50%; background:radial-gradient(circle, rgba(216,168,70,.28), transparent 65%); filter:blur(20px); transform:translate(calc((var(--mx) - 50%) / 5), calc((var(--my) - 50%) / 5)); }
    .final-content { position:relative; z-index:1; max-width:1040px; }
    .final h2 { font-size:clamp(58px,9vw,142px); line-height: .92; }
    .final p { max-width:760px; margin:30px auto 0; color:rgba(244,236,223,.72); font-size:22px; line-height:1.55; letter-spacing:-.035em; }
    .footer-note { margin-top:52px; color:rgba(244,236,223,.45); font-size:13px; font-weight:900; letter-spacing:.13em; text-transform:uppercase; }

    .reveal { opacity:0; transform:translateY(44px); transition: .9s cubic-bezier(.2,.8,.2,1); }
    .reveal.in-view { opacity:1; transform:translateY(0); }
    .split-word { display:inline-block; overflow:visible; vertical-align:bottom; }
    .split-word span { display:inline-block; transform:translateY(110%); transition:transform .9s cubic-bezier(.2,.8,.2,1); }
    .in-view .split-word span { transform:translateY(0); }
    .magnetic { will-change:transform; }
    .parallax { will-change:transform; }

    @keyframes rotate { from{ transform:rotate(0deg);} to{ transform:rotate(360deg);} }
    @keyframes pulse { 70%{ box-shadow:0 0 0 14px rgba(152,50,38,0);} 100%{ box-shadow:0 0 0 0 rgba(152,50,38,0);} }
    @keyframes float { 0%,100%{ translate:0 0;} 50%{ translate:0 -18px;} }
    @keyframes blob { 0%,100%{ border-radius:42% 58% 64% 36% / 42% 32% 68% 58%; transform:rotate(0deg) scale(1);} 50%{ border-radius:62% 38% 34% 66% / 38% 64% 36% 62%; transform:rotate(18deg) scale(1.06);} }
    @keyframes marquee { from{ transform:translateX(0);} to{ transform:translateX(-50%);} }

    @media (max-width: 980px) {
      body { cursor:auto; }
      a, button { cursor:pointer; }
      .cursor, .scroll-meter, .noise-title { display:none; }
      .menu-panel { padding: 100px 22px 30px; overflow-y:auto; }
      .menu-grid, .hero, .section-head, .asym-grid, .origin-grid, .manifesto-grid { grid-template-columns:1fr; }
      .menu-grid { align-items:start; gap:28px; }
      .menu-links a { grid-template-columns: 44px 1fr; }
      .menu-links strong { font-size: clamp(40px, 13vw, 72px); }
      .menu-image { min-height: 260px; }
      .menu-note { grid-template-columns: 1fr; }
      .hero { padding-top:125px; clip-path:none; min-height:auto; }
      h1 .cut { transform:none; }
      .hero-visual { min-height:540px; }
      .video-frame { width:100%; height:460px; }
      .floating-card { left:10px; bottom:10px; width:230px; }
      .floating-card strong { font-size:32px; }
      .feature-card.wide { min-height:560px; }
      .origin { clip-path:none; }
      .map-card { min-height:450px; }
      .panel { min-height: 68vh; padding: 32px; }
      .stat-grid { grid-template-columns:1fr; }
      .stat { border-right:0; border-bottom:1px solid var(--line); }
      .stat:last-child { border-bottom:0; }
    }
  </style>
</head>
<body>
  <div class="cursor" id="cursor"></div>
  <div class="noise-title">filtered editorial system</div>
  <div class="scroll-meter"><span id="scrollMeter"></span></div>

  <nav class="nav">
    <a href="#top" class="logo magnetic" aria-label="Wydawnictwo Filtry">
      <span class="logo-mark"></span>
      <span>Filtry</span>
    </a>
    <button class="menu-trigger magnetic" id="menuTrigger" aria-label="Otwórz menu" aria-expanded="false">Menu</button>
  </nav>

  <aside class="menu-panel" id="menuPanel" aria-hidden="true">
    <div class="menu-grid">
      <div class="menu-links">
        <a href="#idea"><strong>Idea</strong></a>
        <a href="#poczatek"><strong>Geneza</strong></a>
        <a href="#katalog"><strong>Katalog</strong></a>
        <a href="#film"><strong>Obraz</strong></a>
        <a href="#dzisiaj"><strong>Dzisiaj</strong></a>
        <a href="#kontakt"><strong>Kontakt</strong></a>
      </div>
      <div class="menu-side">
        <div class="menu-image magnetic"></div>
        <div class="menu-note">
          <div><span>Profil</span><p>Proza, reportaż, eseistyka i literatura faktu wybierane z wyraźną redakcyjną intencją.</p></div>
          <div><span>Tożsamość</span><p>Warszawska, ambitna, świadoma. Marka dla czytelników, którzy szukają treści z ciężarem.</p></div>
        </div>
      </div>
    </div>
  </aside>

  <main id="top">
    <section class="hero">
      <div>
        <div class="eyebrow reveal"><span class="pulse"></span> Warszawska oficyna literacka / od 2020</div>
        <h1 class="reveal split-title">
          <span>Książki,</span>
          <span>które</span>
          <span class="cut">filtrują</span>
          <span>świat.</span>
          <span class="thin">ambitna proza · reportaż · esej</span>
        </h1>
        <p class="hero-copy reveal">
          Niezależne wydawnictwo z Warszawy, które stawia na świadomy wybór zamiast nadmiaru. Filtry publikują książki ważne, odważne i zaprojektowane jako początek rozmowy.
        </p>
        <div class="hero-actions reveal">
          <a class="btn primary magnetic" href="#idea">Wejdź w ideę</a>
          <a class="btn magnetic" href="#katalog">Zobacz katalog</a>
        </div>
      </div>

      <div class="hero-visual reveal parallax" data-speed="-0.12">
        <div class="video-frame magnetic"></div>
        <article class="floating-card">
          <small>kuratorka selekcja</small>
          <strong>Mniej tytułów. Więcej znaczenia.</strong>
        </article>
        <div class="sphere"></div>
      </div>
    </section>

    <div class="marquee" aria-hidden="true">
      <div class="marquee-track">
        <span>proza</span><span>reportaż</span><span>historia społeczna</span><span>nowe przekłady</span><span>debiuty</span><span>książki do rozmowy</span>
        <span>proza</span><span>reportaż</span><span>historia społeczna</span><span>nowe przekłady</span><span>debiuty</span><span>książki do rozmowy</span>
      </div>
    </div>

    <section id="idea" class="diagonal-section">
      <div class="container">
        <div class="section-head">
          <p class="kicker reveal">01 / Idea</p>
          <div>
            <h2 class="reveal">To nie katalog. To sposób patrzenia.</h2>
            <p class="lead reveal" style="margin-top:24px;">
              Filtry można opowiedzieć jako markę, która odsiewa szum i wydobywa teksty z realną wagą. Proza, reportaż i esej tworzą tu wspólną przestrzeń: dla pytań, kontekstu i rozmowy.
            </p>
          </div>
        </div>

        <div class="asym-grid">
          <article class="feature-card wide reveal parallax" data-speed="0.08">
            <div>
              <div class="num">01</div>
              <h3>Selekcja jako gest redakcyjny.</h3>
            </div>
            <p>Wydawnictwo nie komunikuje masowości. Komunikuje wybór. Dlatego strona pracuje światłem, przestrzenią i spokojnym rytmem — tak, aby każdy element wyglądał jak świadoma decyzja.</p>
            <div class="orbit"></div>
          </article>
          <article class="feature-card photo reveal parallax" data-speed="-0.06">
            <div class="num">02</div>
            <h3>Obraz zamiast dekoracji.</h3>
            <p>Duże kadry mogą pokazywać papier, miasto, archiwum, spotkania autorskie lub detale książek. Mają budować atmosferę, nie wypełniać pustkę.</p>
          </article>
          <article class="feature-card reveal parallax" data-speed="0.05">
            <div class="num">03</div>
            <h3>Ruch podporządkowany treści.</h3>
            <p>Animacje prowadzą uwagę: kursor zmienia światło, scroll odsłania warstwy, a poziome przejście katalogu działa jak przeglądanie półki.</p>
          </article>
        </div>
      </div>
    </section>

    <section id="poczatek" class="origin section-pad">
      <div class="container origin-grid">
        <div class="map-card reveal parallax" data-speed="0.12"><span class="pin"></span></div>
        <div>
          <p class="kicker reveal">02 / Geneza</p>
          <h2 class="reveal" style="margin-top:18px;">Warszawskie Filtry jako metafora wyboru.</h2>
          <p class="lead reveal" style="margin-top:28px; color:rgba(244,236,223,.7);">
            Nazwa prowadzi do miejsca związanego z oczyszczaniem i obiegiem. W warstwie marki staje się metaforą pracy redakcyjnej: przepuszczania przez filtr tego, co ważne, aktualne i warte rozmowy.
          </p>
          <div class="timeline" style="margin-top:34px;">
            <article class="timeline-item reveal"><div class="year">2020</div><div><h3>Start</h3><p>Powstaje młoda, warszawska oficyna skupiona na prozie i literaturze faktu.</p></div></article>
            <article class="timeline-item reveal"><div class="year">→</div><div><h3>Profil</h3><p>W katalogu pojawiają się przekłady, debiuty, reportaże i książki o wyraźnym ciężarze tematycznym.</p></div></article>
            <article class="timeline-item reveal"><div class="year">dziś</div><div><h3>Rozpoznawalność</h3><p>Filtry budują pozycję marki ambitnej, estetycznej i konsekwentnej redakcyjnie.</p></div></article>
          </div>
        </div>
      </div>
    </section>

    <section id="katalog" class="horizontal-wrap">
      <div class="horizontal-sticky">
        <div class="horizontal-track" id="horizontalTrack">
          <article class="panel dark">
            <span class="tag">03 / Katalog</span>
            <div><h3>Proza współczesna</h3><p>Wyraziste głosy, mocne narracje i literatura, która zostaje po lekturze dłużej niż sam fabularny impuls.</p></div>
          </article>
          <article class="panel photo-2">
            <span class="tag">Warstwa wizualna</span>
            <div><h3>Duży kadr zamiast miniatury</h3><p>W tej przestrzeni można umieścić zdjęcia książek, autorów albo krótką pętlę video. Strona od razu zyskuje bardziej premium charakter.</p></div>
          </article>
          <article class="panel green">
            <span class="tag">Literatura faktu</span>
            <div><h3>Reportaż i historia społeczna</h3><p>Książki, które dają kontekst, ale nie upraszczają rzeczywistości. Porządkują temat bez odbierania mu napięcia.</p></div>
          </article>
          <article class="panel red">
            <span class="tag">Przekłady</span>
            <div><h3>Klasyka czytana na nowo</h3><p>Nowe przekłady i ważne tytuły zagraniczne pozwalają zobaczyć znane tematy innym językiem.</p></div>
          </article>
          <article class="panel gold">
            <span class="tag">Debiuty</span>
            <div><h3>Ryzyko, które ma sens</h3><p>Nowe nazwiska są częścią tożsamości marki: odkrywanie głosów, które mogą zmienić ton rozmowy.</p></div>
          </article>
        </div>
      </div>
    </section>

    <section id="film" class="cinema">
      <div class="container">
        <p class="kicker reveal">04 / Obraz i dźwięk</p>
        <h2 class="reveal" style="margin-top:18px; max-width:980px;">Sekcja filmowa jak trailer wydawnictwa.</h2>
        <p class="lead reveal" style="margin-top:24px; color:rgba(244,236,223,.68); max-width:720px;">
          Tu może działać krótka pętla video: przewracane strony, detal papieru, Warszawa, rozmowa redakcyjna albo fragment spotkania autorskiego. Scroll lekko skaluje kadr, dzięki czemu sekcja ma kinowy rytm.
        </p>
      </div>
      <div class="cinema-frame reveal" id="cinemaFrame"></div>
    </section>

    <section id="dzisiaj" class="manifesto">
      <div class="container manifesto-grid">
        <article class="quote reveal">
          <div>
            <p class="kicker">05 / Dzisiaj</p>
            <h2 style="margin-top:18px;">Młode wydawnictwo z dojrzałym głosem.</h2>
          </div>
          <p>
            Filtry rozwijają katalog, prowadzą sprzedaż online i konsekwentnie budują markę dla czytelników, którzy szukają książek nieoczywistych, estetycznych i intelektualnie gęstych.
          </p>
        </article>
        <article class="mini reveal parallax" data-speed="0.08">
          <h3>Ton marki</h3>
          <p>Elegancki, miejski, inteligentny. Bliżej zaproszenia do rozmowy niż klasycznego komunikatu sprzedażowego.</p>
        </article>
        <article class="mini reveal parallax" data-speed="-0.06">
          <h3>Odbiorcy</h3>
          <p>Czytelnicy literatury ambitnej, osoby zainteresowane kulturą, reportażem, historią społeczną i świadomym wyborem książek.</p>
        </article>
      </div>
    </section>

    <section class="stats">
      <div class="container stat-grid reveal">
        <div class="stat"><strong>2020</strong><span>rok powstania wydawnictwa</span></div>
        <div class="stat"><strong>3</strong><span>proza, reportaż i esej jako główne obszary</span></div>
        <div class="stat"><strong>PL</strong><span>warszawska tożsamość i lokalny punkt wyjścia</span></div>
        <div class="stat"><strong>∞</strong><span>książki traktowane jako początek rozmowy</span></div>
      </div>
    </section>

    <section id="kontakt" class="final">
      <div class="final-content reveal">
        <p class="kicker">Wydawnictwo Filtry</p>
        <h2>Literatura po przejściu przez filtr.</h2>
        <p>
          One page jako editorial experience: światło reaguje na kursor, scroll buduje rytm, a treść odsłania się warstwami — jak dobrze zaprojektowana książka.
        </p>
        <div class="hero-actions" style="justify-content:center; margin-top:42px;">
          <a class="btn primary magnetic" style="background:var(--paper); color:var(--ink);" href="#top">Wróć na górę ↑</a>
        </div>
        <div class="footer-note">hyper modern one page / editorial motion system</div>
      </div>
    </section>
  </main>

  <script>
    const cursor = document.getElementById('cursor');
    const meter = document.getElementById('scrollMeter');
    const root = document.documentElement;
    const menuTrigger = document.getElementById('menuTrigger');
    const menuPanel = document.getElementById('menuPanel');
    let lenis;

    if (window.Lenis) {
      lenis = new Lenis({
        duration: 1.18,
        easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
        smoothWheel: true,
        wheelMultiplier: 0.92,
        touchMultiplier: 1.4
      });

      function raf(time) {
        lenis.raf(time);
        requestAnimationFrame(raf);
      }
      requestAnimationFrame(raf);
    }

    function toggleMenu(force) {
      const shouldOpen = typeof force === 'boolean' ? force : !menuPanel.classList.contains('open');
      menuPanel.classList.toggle('open', shouldOpen);
      document.body.classList.toggle('menu-open', shouldOpen);
      menuTrigger.setAttribute('aria-expanded', shouldOpen ? 'true' : 'false');
      menuTrigger.textContent = shouldOpen ? 'Zamknij' : 'Menu';
      menuPanel.setAttribute('aria-hidden', shouldOpen ? 'false' : 'true');
      if (lenis) shouldOpen ? lenis.stop() : lenis.start();
    }

    menuTrigger.addEventListener('click', () => toggleMenu());
    document.querySelectorAll('.menu-panel a').forEach((link) => {
      link.addEventListener('click', () => {
        toggleMenu(false);
      });
    });

    window.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') toggleMenu(false);
    });

    window.addEventListener('mousemove', (e) => {
      const x = e.clientX;
      const y = e.clientY;
      root.style.setProperty('--mx', `${(x / window.innerWidth) * 100}%`);
      root.style.setProperty('--my', `${(y / window.innerHeight) * 100}%`);
      if (cursor) {
        cursor.style.left = `${x}px`;
        cursor.style.top = `${y}px`;
      }
    });

    document.querySelectorAll('a, button, .magnetic, .video-frame, .cinema-frame').forEach((el) => {
      el.addEventListener('mouseenter', () => cursor && cursor.classList.add('big'));
      el.addEventListener('mouseleave', () => cursor && cursor.classList.remove('big'));
    });

    const revealEls = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) entry.target.classList.add('in-view');
      });
    }, { threshold: 0.14 });
    revealEls.forEach((el) => observer.observe(el));

    document.querySelectorAll('.split-title').forEach((title) => {
      [...title.children].forEach((line, i) => {
        const text = line.textContent;
        line.innerHTML = `<span class="split-word"><span style="transition-delay:${i * 90}ms">${text}</span></span>`;
      });
    });

    const horizontalWrap = document.querySelector('.horizontal-wrap');
    const horizontalTrack = document.getElementById('horizontalTrack');
    const cinemaFrame = document.getElementById('cinemaFrame');

    function onScroll() {
      const docHeight = document.documentElement.scrollHeight - window.innerHeight;
      const progressAll = Math.min(window.scrollY / docHeight, 1);
      if (meter) meter.style.height = `${progressAll * 100}%`;

      document.querySelectorAll('.parallax').forEach((el) => {
        const speed = parseFloat(el.dataset.speed || 0);
        const rect = el.getBoundingClientRect();
        const center = rect.top + rect.height / 2 - window.innerHeight / 2;
        el.style.transform = `translate3d(0, ${center * speed}px, 0)`;
      });

      if (horizontalWrap && horizontalTrack) {
        const rect = horizontalWrap.getBoundingClientRect();
        const maxScroll = horizontalTrack.scrollWidth - window.innerWidth + window.innerWidth * .14;
        const progress = Math.min(Math.max(-rect.top / (horizontalWrap.offsetHeight - window.innerHeight), 0), 1);
        horizontalTrack.style.transform = `translateX(${-progress * maxScroll}px)`;
      }

      if (cinemaFrame) {
        const rect = cinemaFrame.getBoundingClientRect();
        const p = Math.min(Math.max((window.innerHeight - rect.top) / (window.innerHeight + rect.height), 0), 1);
        const scale = .88 + p * .18;
        const rotate = -2 + p * 4;
        cinemaFrame.style.transform = `scale(${scale}) rotate(${rotate}deg)`;
      }
    }

    window.addEventListener('scroll', onScroll, { passive: true });
    if (lenis) lenis.on('scroll', onScroll);
    window.addEventListener('resize', onScroll);
    onScroll();

    document.querySelectorAll('.magnetic').forEach((el) => {
      el.addEventListener('mousemove', (e) => {
        const rect = el.getBoundingClientRect();
        const x = e.clientX - rect.left - rect.width / 2;
        const y = e.clientY - rect.top - rect.height / 2;
        el.style.transform = `translate(${x * .14}px, ${y * .14}px)`;
      });
      el.addEventListener('mouseleave', () => { el.style.transform = 'translate(0,0)'; });
    });
  </script>
</body>
</html>
