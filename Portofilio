<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Portfolio personal Darwis Haris — Creative Digital Worker.">
  <title>Darwis Haris — Personal Portfolio</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Space+Grotesk:wght@500;600;700;800&display=swap');

    :root {
      --bg: #050b16;
      --bg2: #071326;
      --panel: rgba(10,24,46,.5);
      --panel2: rgba(12,31,59,.4);
      --line: rgba(91,166,255,.12);
      --line2: rgba(91,166,255,.25);
      --blue: #2f8cff;
      --blue2: #58b5ff;
      --cyan: #73d7ff;
      --text: #f5f9ff;
      --muted: #8da4bf;
      --shadow: 0 24px 70px rgba(0,0,0,.42);
      --radius: 20px;
      
      /* Apple Signature Easing */
      --apple-ease: cubic-bezier(0.16, 1, 0.3, 1);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: Inter, system-ui, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      overflow-x: hidden;
    }
    
    /* Mengunci scroll saat animasi intro / full page berjalan */
    body.locked {
      overflow: hidden;
      height: 100vh;
    }

    /* Ambient Glow Background */
    body::before {
      content: ""; position: fixed; inset: 0; z-index: -2;
      background:
        radial-gradient(circle at 80% 0%, rgba(47,140,255,0.15), transparent 40%),
        radial-gradient(circle at 20% 100%, rgba(115,215,255,0.1), transparent 40%);
    }

    /* Grid Texture */
    body::after {
      content: ""; position: fixed; inset: 0; pointer-events: none; z-index: -1; opacity: .25;
      background-image:
        linear-gradient(rgba(93,155,220,.1) 1px, transparent 1px),
        linear-gradient(90deg, rgba(93,155,220,.1) 1px, transparent 1px);
      background-size: 40px 40px;
      mask-image: linear-gradient(to bottom, black 0%, rgba(0,0,0,.3) 75%, transparent 100%);
    }

    /* =========================================
       INTRO / PRELOADER (SEPERTI DI VIDEO)
       ========================================= */
    #intro {
      position: fixed; inset: 0; z-index: 100000;
      background: #000; 
      display: flex; align-items: center; justify-content: center;
      transition: transform 1.2s cubic-bezier(0.76, 0, 0.24, 1); 
      will-change: transform;
    }
    #intro.hidden {
      transform: translateY(-100%);
      pointer-events: none;
    }
    .intro-container {
      text-align: center;
      display: flex; flex-direction: column; align-items: center; gap: 8px;
    }
    .intro-text {
      color: #fff;
      opacity: 0;
      transform: translateY(15px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }
    .intro-text.active {
      opacity: 1;
      transform: translateY(0);
    }
    .intro-small {
      font-family: 'Inter', sans-serif; font-size: clamp(14px, 2vw, 18px); font-weight: 500;
      letter-spacing: 0.1em; color: rgba(255,255,255,0.8);
    }
    .intro-huge {
      font-family: 'Space Grotesk', sans-serif; font-size: clamp(32px, 6vw, 68px);
      font-weight: 800; letter-spacing: -0.02em; transform: scaleX(1.05);
    }
    .intro-link {
      font-family: monospace; font-size: 13px; color: rgba(255,255,255,0.4); 
      letter-spacing: 0.05em; margin-top: 15px;
    }

    a { color: inherit; text-decoration: none; }
    button, input, textarea { font: inherit; }

    /* Custom Cursor */
    .cursor {
      position: fixed; width: 6px; height: 6px; border-radius: 50%;
      background: var(--cyan); box-shadow: 0 0 20px 4px rgba(115,215,255,0.4);
      pointer-events: none; z-index: 9999; transform: translate(-50%,-50%);
      transition: opacity .3s var(--apple-ease);
    }

    /* Apple-like Glass Navbar */
    nav {
      position: fixed; top: 18px; left: 50%; transform: translateX(-50%);
      width: min(1120px, calc(100% - 32px)); height: 56px;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 20px; border: 1px solid rgba(255,255,255,0.05);
      background: rgba(5, 11, 22, 0.6); backdrop-filter: blur(24px) saturate(150%);
      -webkit-backdrop-filter: blur(24px) saturate(150%);
      border-radius: 100px; z-index: 100; box-shadow: 0 10px 30px rgba(0,0,0,.3);
      transition: 0.4s var(--apple-ease);
    }
    .brand { font-family: "Space Grotesk"; font-weight: 700; letter-spacing: -.03em; font-size: 15px;}
    .brand span { color: var(--blue2); }
    .navlinks { display: flex; gap: 4px; }
    .navlinks a {
      font-size: 12px; color: #9eb0c7; padding: 8px 16px; border-radius: 100px;
      transition: all 0.3s var(--apple-ease); font-weight: 500;
    }
    .navlinks a:hover, .navlinks a.active { color: #fff; background: rgba(255,255,255,0.1); }
    .menu { display: none; background: none; border: 0; color: #fff; font-size: 20px; cursor: pointer; }

    section { width: min(1120px, calc(100% - 32px)); margin: auto; }
    
    /* Hero Section */
    .hero {
      min-height: 100vh; display: grid; grid-template-columns: 1.1fr 0.9fr;
      align-items: center; gap: 60px; padding-top: 80px;
    }
    .hero-content { will-change: transform, opacity; }
    .eyebrow { color: var(--blue2); font-size: 11px; letter-spacing: .25em; text-transform: uppercase; margin-bottom: 24px; font-weight: 600; }
    h1 {
      font-family: "Space Grotesk"; font-size: clamp(48px, 7vw, 86px);
      line-height: .95; letter-spacing: -.05em; max-width: 760px; font-weight: 700;
    }
    h1 .fade { display: block; color: rgba(255,255,255,0.4); }
    .hero p { max-width: 580px; color: var(--muted); font-size: 15px; line-height: 1.7; margin: 32px 0; font-weight: 300;}
    .meta { display: flex; gap: 10px; flex-wrap: wrap; }
    .pill {
      border: 1px solid var(--line); background: rgba(255,255,255,0.03);
      padding: 8px 14px; border-radius: 100px; color: #a4b9d1; font-size: 11px;
      backdrop-filter: blur(10px); letter-spacing: 0.02em;
    }
    .actions { display: flex; gap: 12px; margin-top: 32px; }
    .btn {
      border: 1px solid var(--line2); background: rgba(255,255,255,0.05);
      color: #fff; border-radius: 100px; padding: 14px 24px; font-size: 13px; font-weight: 500;
      cursor: pointer; transition: all 0.4s var(--apple-ease); display: inline-flex; align-items: center; gap: 8px;
    }
    .btn.primary { background: #fff; color: #000; border-color: transparent; }
    .btn:hover { transform: scale(1.05); box-shadow: 0 10px 30px rgba(255,255,255,0.1); }
    .btn.primary:hover { box-shadow: 0 10px 30px rgba(255,255,255,0.2); }

    /* ID Card 3D CSS */
    .profile-wrap { display: flex; justify-content: center; align-items: center; position: relative; will-change: transform; }
    .perspective-container { perspective: 2000px; width: 100%; height: 500px; display: flex; justify-content: center; align-items: flex-start; position: relative; transform: scale(0.85); transform-origin: top center; }
    .lanyard-assembly { transform-style: preserve-3d; display: flex; flex-direction: column; align-items: center; transform-origin: 50% -200px; cursor: grab; margin-top: -80px; padding-bottom: 50px; padding-left: 50px; padding-right: 50px; }
    .lanyard-assembly:active { cursor: grabbing; }
    .lanyard-strap { width: 18px; height: 350px; background: linear-gradient(to right, var(--bg2), #111, var(--bg2)); position: relative; z-index: 1; box-shadow: 2px 0 10px rgba(0,0,0,0.5); display: flex; justify-content: center; align-items: flex-end; transform: translateZ(1px); }
    .lanyard-text { color: rgba(255,255,255, 0.2); writing-mode: vertical-rl; text-orientation: mixed; transform: rotate(180deg); font-size: 10px; font-weight: 700; letter-spacing: 4px; margin-bottom: 30px; pointer-events: none; }
    .metal-clip { width: 16px; height: 35px; background: linear-gradient(135deg, #aaa, #eee, #888, #ddd); border-radius: 4px; margin-top: -5px; margin-bottom: -15px; position: relative; z-index: 3; box-shadow: inset 0 0 5px rgba(0,0,0,0.5), 0 4px 6px rgba(0,0,0,0.6); transform: translateZ(2px); }
    .id-card { width: 260px; height: 380px; background: var(--bg2); border-radius: 16px; position: relative; transform-style: preserve-3d; box-shadow: 0 30px 60px -12px rgba(0,0,0,0.9), inset 0 0 0 1px rgba(255,255,255,0.1); z-index: 2; }
    .card-hole { width: 45px; height: 10px; background-color: var(--bg); border-radius: 10px; position: absolute; top: 16px; left: 50%; transform: translateX(-50%); box-shadow: inset 0 3px 5px rgba(0,0,0,0.8); border: 1px solid rgba(255,255,255,0.05); z-index: 10; }
    .card-front { position: absolute; width: 100%; height: 100%; backface-visibility: hidden; border-radius: 16px; padding: 0; display: flex; flex-direction: column; justify-content: flex-end; overflow: hidden; background: var(--bg2); }
    .photo-container { position: absolute; top: 0; left: 0; width: 100%; height: 100%; margin: 0; background: var(--bg); z-index: 0; }
    .photo-container img { width: 100%; height: 100%; object-fit: cover; filter: contrast(105%) brightness(90%); }
    .card-front::after { content: ''; position: absolute; top: 0; left: -100%; width: 50%; height: 100%; background: linear-gradient(to right, transparent, rgba(255,255,255,0.08), transparent); transform: skewX(-20deg); animation: cardShine 7s infinite var(--apple-ease); pointer-events: none; z-index: 2; }
    @keyframes cardShine { 0% { left: -100%; } 20% { left: 200%; } 100% { left: 200%; } }
    .id-details { position: relative; z-index: 1; width: 100%; text-align: center; padding: 60px 20px 25px; background: linear-gradient(to top, rgba(5,11,22,1) 0%, rgba(5,11,22,0.6) 60%, transparent 100%); display: flex; flex-direction: column; justify-content: flex-end; align-items: center; }
    .id-name { font-family: 'Space Grotesk', sans-serif; color: #fff; font-weight: 700; font-size: 24px; letter-spacing: 0.02em; margin: 0; }
    .id-role { color: var(--blue2); font-size: 12px; font-weight: 500; margin-top: 6px; letter-spacing: 0.05em; }
    .hint-drag { position: absolute; bottom: -35px; left: 50%; transform: translateX(-50%); font-size: 10px; color: rgba(255,255,255,0.4); font-family: monospace; letter-spacing: 0.2em; pointer-events: none; animation: pulse 3s infinite; }
    @keyframes pulse { 0%, 100% { opacity: 0.2; } 50% { opacity: 0.7; } }

    /* Sections */
    .section { padding: 140px 0 60px; }
    .section-head { display: flex; align-items: end; justify-content: space-between; gap: 25px; margin-bottom: 40px; }
    .kicker { font-size: 11px; letter-spacing: .25em; color: var(--blue2); text-transform: uppercase; font-weight: 600; margin-bottom: 12px;}
    h2 { font-family: "Space Grotesk"; font-size: clamp(36px, 5vw, 64px); letter-spacing: -.04em; font-weight: 700; line-height: 1; }
    .sub { color: var(--muted); font-size: 14px; max-width: 420px; line-height: 1.6; text-align: right; font-weight: 300; }

    /* About Cards */
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .card {
      border: 1px solid rgba(255,255,255,0.06); background: rgba(255,255,255,0.02);
      backdrop-filter: blur(20px); border-radius: var(--radius); padding: 36px;
      box-shadow: 0 20px 40px rgba(0,0,0,.2); transition: transform 0.6s var(--apple-ease), background 0.6s var(--apple-ease);
    }
    .card:hover { transform: translateY(-4px); background: rgba(255,255,255,0.04); }
    .card p { color: #9eb0c7; font-size: 14px; line-height: 1.8; font-weight: 300;}
    .stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin-top: 24px; }
    .stat { padding: 20px; border: 1px solid rgba(255,255,255,0.05); border-radius: 16px; background: rgba(0,0,0,0.2); }
    .stat strong { display: block; font-family: "Space Grotesk"; font-size: 28px; color: #fff; font-weight: 700;}
    .stat span { font-size: 11px; color: rgba(255,255,255,0.5); font-weight: 500; margin-top: 4px; display:block; }

    /* Portfolio Grid */
    .work-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px; }
    .project { min-height: 300px; position: relative; overflow: hidden; cursor: pointer; padding: 24px; display: flex; flex-direction: column;}
    .project .visual {
      height: 200px; border-radius: 14px; border: 1px solid rgba(255,255,255,0.05);
      margin-bottom: 24px; display: flex; align-items: center; justify-content: center;
      background-size: cover; background-position: center; position: relative;
      transition: transform 0.8s var(--apple-ease);
    }
    .project .visual::before { content: ""; position: absolute; inset: 0; background: rgba(0,0,0,0.2); border-radius: 14px; transition: 0.5s; }
    .project:hover .visual { transform: scale(1.03); }
    .project:hover .visual::before { background: rgba(0,0,0,0); }
    .project h3 { font-size: 20px; margin-bottom: 10px; display: flex; justify-content: space-between; align-items: center; font-family: "Space Grotesk"; font-weight: 600;}
    .project h3 span { font-size: 11px; color: var(--bg); background: #fff; padding: 6px 12px; border-radius: 100px; opacity: 0; transform: translateX(-10px); transition: 0.4s var(--apple-ease); }
    .project:hover h3 span { opacity: 1; transform: translateX(0); }
    .project p { font-size: 13px; color: #8da4bf; line-height: 1.6; font-weight: 300; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
    .tags { display: flex; gap: 8px; flex-wrap: wrap; margin-top: auto; padding-top: 20px;}
    .tag { font-size: 10px; color: #fff; border: 1px solid rgba(255,255,255,0.1); padding: 6px 12px; border-radius: 100px; background: rgba(255,255,255,0.03); backdrop-filter: blur(5px);}

    /* Skills & Tools Grid */
    .skills { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; }
    .skill { padding: 32px 20px; text-align: center; border: 1px solid rgba(255,255,255,0.05); background: rgba(255,255,255,0.02); border-radius: var(--radius); transition: all 0.5s var(--apple-ease); cursor: pointer; backdrop-filter: blur(10px); }
    .skill:hover { transform: translateY(-8px) scale(1.02); background: rgba(255,255,255,0.06); border-color: rgba(255,255,255,0.15); box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
    
    /* Modifikasi Ikon Menjadi Gambar/Logo */
    .skill .icon { display: flex; justify-content: center; align-items: center; height: 50px; margin-bottom: 16px; }
    .skill .icon img { 
      width: 44px; height: 44px; object-fit: contain; 
      filter: drop-shadow(0 4px 10px rgba(255,255,255,0.1)); 
      transition: transform 0.5s var(--apple-ease); 
    }
    .skill:hover .icon img { transform: scale(1.15) translateY(-4px); filter: drop-shadow(0 8px 15px rgba(255,255,255,0.25)); }
    
    .skill strong { display: block; font-size: 15px; color: #fff; font-weight: 600;}
    .skill span { display: block; color: rgba(255,255,255,0.5); font-size: 12px; margin-top: 6px; font-weight: 300;}
    .skill .hint { font-size: 10px; color: var(--blue2); margin-top: 16px; opacity: 0; transform: translateY(5px); transition: 0.4s var(--apple-ease); }
    .skill:hover .hint { opacity: 1; transform: translateY(0); }

    /* =========================================
       FULL PAGE DETAIL VIEW (PENGGANTI MODAL)
       ========================================= */
    #fullPageView {
      position: fixed; inset: 0; z-index: 99999;
      background: var(--bg);
      overflow-y: auto; overflow-x: hidden;
      opacity: 0; pointer-events: none;
      transform: translateY(40px);
      transition: opacity 0.5s var(--apple-ease), transform 0.5s var(--apple-ease);
    }
    #fullPageView.active {
      opacity: 1; pointer-events: auto; transform: translateY(0);
    }
    .fp-container {
      max-width: 1120px; margin: 0 auto; padding: 50px 20px 100px;
    }
    .fp-back {
      background: none; border: none; color: var(--muted); font-size: 16px; font-weight: 500;
      cursor: pointer; display: inline-flex; align-items: center; gap: 8px; margin-bottom: 50px;
      transition: 0.3s; padding: 10px 15px; border-radius: 100px;
    }
    .fp-back:hover { color: #fff; background: rgba(255,255,255,0.05); transform: translateX(-5px); }
    
    .fp-grid { display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 60px; align-items: start; }
    .fp-title { font-family: 'Space Grotesk'; font-size: clamp(40px, 5vw, 64px); margin-bottom: 24px; line-height: 1.05; letter-spacing: -0.03em; color: #fff;}
    .fp-desc { color: var(--muted); line-height: 1.8; font-size: 16px; font-weight: 300; margin-bottom: 40px; }
    
    .fp-stats { display: flex; gap: 20px; margin-bottom: 40px;}
    .fp-stat-box { 
      background: rgba(12,31,59,.4); border: 1px solid var(--line); 
      padding: 24px; border-radius: 20px; flex: 1; 
      display: flex; flex-direction: column; justify-content: center;
    }
    .fp-stat-box i { font-size: 26px; color: var(--blue2); margin-bottom: 15px; }
    .fp-stat-box .lbl { font-size: 12px; color: var(--muted); margin-bottom: 6px; }
    .fp-stat-box strong { font-size: 24px; color: #fff; font-family: 'Space Grotesk'; }
    
    .fp-main-img { width: 100%; border-radius: 24px; border: 1px solid var(--line); box-shadow: var(--shadow); object-fit: cover;}
    .fp-gallery { display: grid; grid-template-columns: 1fr; gap: 20px; }
    .fp-gallery img { width: 100%; border-radius: 20px; border: 1px solid var(--line); object-fit: cover; }
    
    /* Contact Section */
    .contact { display: grid; grid-template-columns: .8fr 1.2fr; gap: 20px; }
    .social-buttons { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; margin-top: 24px; }
    .social-btn { display: flex; align-items: center; gap: 12px; padding: 14px 18px; background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.08); border-radius: 14px; color: #fff; font-size: 13px; font-weight: 500; transition: all 0.4s var(--apple-ease); }
    .social-btn:hover { background: #fff; color: #000; transform: translateY(-3px); }
    .social-btn:hover i { color: #000; }
    .social-btn i { font-size: 18px; color: #fff; transition: 0.4s; }
    
    form { display: grid; gap: 16px; }
    input, textarea { width: 100%; background: rgba(0,0,0,0.2); border: 1px solid rgba(255,255,255,0.1); color: #fff; border-radius: 14px; padding: 16px; outline: none; font-size: 14px; transition: 0.3s var(--apple-ease); font-weight: 300;}
    input:focus, textarea:focus { border-color: rgba(255,255,255,0.5); background: rgba(0,0,0,0.4); box-shadow: 0 0 0 4px rgba(255,255,255,0.05); }
    textarea { min-height: 140px; resize: vertical; }
    
    footer { width: min(1120px, calc(100% - 32px)); margin: 100px auto 40px; padding-top: 30px; border-top: 1px solid rgba(255,255,255,0.1); display: flex; justify-content: space-between; color: rgba(255,255,255,0.4); font-size: 12px; }

    /* Scroll Reveal Animations */
    .reveal { opacity: 0; transform: translateY(40px) scale(0.98); transition: opacity 1.2s var(--apple-ease), transform 1.2s var(--apple-ease); will-change: opacity, transform; }
    .reveal.show { opacity: 1; transform: translateY(0) scale(1); }

    @media(max-width:800px) {
      nav { top: 10px; width: calc(100% - 32px); }
      .navlinks { display: none; position: absolute; top: 70px; left: 0; right: 0; flex-direction: column; background: rgba(10,15,25,0.95); backdrop-filter: blur(20px); padding: 15px; border: 1px solid rgba(255,255,255,0.1); border-radius: 16px; }
      .navlinks.open { display: flex; } .menu { display: block; }
      .hero { grid-template-columns: 1fr; padding-top: 130px; gap: 40px; text-align: center; }
      .hero p { margin: 24px auto; }
      .actions { justify-content: center; }
      .meta { justify-content: center; }
      .profile-wrap { order: -1; }
      .perspective-container { transform: scale(0.65); height: 380px; margin-top: -20px; }
      .about-grid, .contact { grid-template-columns: 1fr; } 
      .work-grid { grid-template-columns: 1fr; } 
      .skills { grid-template-columns: repeat(2, 1fr); }
      .section-head { display: block; text-align: center; }
      .sub { text-align: center; margin: 12px auto 0; }
      footer { display: block; text-align: center; line-height: 2; }
      .fp-grid { grid-template-columns: 1fr; gap: 40px; }
    }
  </style>
</head>

<body class="locked">

  <div id="intro">
    <div class="intro-container">
      <div class="intro-text intro-small" id="intro-1">Welcome to My</div>
      <div class="intro-text intro-huge" id="intro-2">Portfolio Website</div>
      <div class="intro-text intro-link" id="intro-3">darwisharis.com</div>
    </div>
  </div>

  <div class="cursor" id="cursor"></div>

  <nav id="navbar">
    <a class="brand" href="#home">Resss Studio<span>.</span></a>
    <div class="navlinks" id="navlinks">
      <a href="#home" class="active">Home</a>
      <a href="#about">About</a>
      <a href="#portfolio">Portfolio</a>
      <a href="#skills">Tools</a>
      <a href="#contact">Contact</a>
    </div>
    <button class="menu" id="menu"><i class="fa-solid fa-bars"></i></button>
  </nav>

  <main>
    <section class="hero" id="home">
      <div class="hero-content reveal">
        <div class="eyebrow">Personal Portfolio / 2026</div>
        <h1>Creative<br><span class="fade">Digital Worker.</span></h1>
        <p>
          Halo, saya <b style="color:#fff; font-weight:500;">Muhammad Darwis Harits Arjuno</b>. Biasa dipanggil Darwis atau Haris. Saya merupakan mahasiswa Institut Teknologi dan Bisnis Ahmad Dahlan Lamongan (ITBADLA). Saya berfokus pada eksplorasi gaya visual, mendokumentasikan momen perjalanan jarak jauh, dinamika street photography, dan meracik narasi digital.
        </p>
        <div class="meta">
          <span class="pill">Mahasiswa</span>
          <span class="pill">Graphic Design</span>
          <span class="pill">Content Creator</span>
          <span class="pill">Rider & Traveler</span>
        </div>
        <div class="actions">
          <a class="btn primary" href="#portfolio">View Projects</a>
          <a class="btn" href="#contact">Contact Me</a>
        </div>
      </div>
      
      <div class="profile-wrap reveal">
        <div class="perspective-container">
            <div class="lanyard-assembly" id="lanyardAssembly">
                <div class="lanyard-strap">
                    <span class="lanyard-text">CREATIVE WORKER</span>
                </div>
                <div class="metal-clip"></div>
                <div class="id-card">
                    <div class="card-hole"></div>
                    <div class="card-front">
                        <div class="photo-container">
                            <img src="https://6aad01abe86d4c28a058c63e.imgix.net/sandbox/ChatGPT%20Image%20Sep%2016,%202026,%2008_17_19%20AM.png" 
                                 alt="Portrait" 
                                 onerror="this.onerror=null; this.src='https://placehold.co/300x400/222/555?text=Photo';">
                        </div>
                        <div class="id-details">
                            <h2 class="id-name">Darwis Haris</h2>
                            <p class="id-role">Creative Editor</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="hint-drag">DRAG TO INTERACT</div>
        </div>
      </div>
    </section>

    <section class="section" id="about">
      <div class="section-head reveal">
        <div><div class="kicker">01 / About</div><h2>Tentang Saya.</h2></div>
        <div class="sub">Membangun pekerjaan yang rapi, komunikatif, dan memiliki nilai estetika tinggi.</div>
      </div>
      <div class="about-grid">
        <div class="card reveal stagger-1">
          <p>
            Saya memiliki ketertarikan yang mendalam pada dunia digital, desain, dokumentasi, dan teknologi. Dalam keseharian, saya menangani kebutuhan penyusunan informasi visual, serta membantu merancang materi komunikasi agar mudah dipahami, modern, dan tentunya menarik perhatian audiens.
          </p>
          <div class="stats">
            <div class="stat"><strong>01</strong><span>Admin & Office</span></div>
            <div class="stat"><strong>02</strong><span>Creative Content</span></div>
            <div class="stat"><strong>03</strong><span>Digital Projects</span></div>
          </div>
        </div>
        <div class="card reveal stagger-2">
          <div class="kicker" style="margin-bottom: 8px;">Focus Area</div>
          <h3 style="font-family:'Space Grotesk'; font-size:28px; margin-bottom:16px; font-weight:700;">Digital × Education</h3>
          <p>
            Fokus utama saya adalah memadukan kemampuan manajerial administrasi dengan kreativitas tanpa batas di ruang digital: meracik desain grafis, menulis copy/caption yang kuat, mendokumentasikan foto, hingga membangun antarmuka web interaktif untuk berbagai keperluan profesional maupun personal.
          </p>
        </div>
      </div>
    </section>

    <section class="section" id="portfolio">
      <div class="section-head reveal">
        <div><div class="kicker">02 / Selected Work</div><h2>Portfolio Showcase.</h2></div>
        <div class="sub">Klik pada setiap kartu untuk membuka presentasi proyek dalam satu layar penuh.</div>
      </div>
      <div class="work-grid">
        
        <article class="card project reveal stagger-1" data-type="portfolio" 
                 data-title="Social Media Content" 
                 data-img="https://images.unsplash.com/photo-1611162617474-5b21e879e113?q=80&w=1000&auto=format&fit=crop"
                 data-desc="Pengelolaan konten media sosial komprehensif. Mulai dari perumusan strategi interaksi, penulisan caption persuasif (copywriting), hingga penyusunan estetika feed Instagram yang harmonis. Berperan langsung dalam mendokumentasikan kegiatan dan meramunya menjadi publikasi digital berkualitas.">
          <div class="visual" style="background-image: url('https://images.unsplash.com/photo-1611162617474-5b21e879e113?q=80&w=600&auto=format&fit=crop');"></div>
          <h3>Social Media Content <span>Detail</span></h3>
          <p>Konten Instagram, caption, poster, dokumentasi kegiatan, dan publikasi digital.</p>
          <div class="tags"><span class="tag"><i class="fa-brands fa-instagram"></i> Instagram</span><span class="tag">Copywriting</span><span class="tag">Strategy</span></div>
        </article>

        <article class="card project reveal stagger-2" data-type="portfolio"
                 data-title="Graphic Design"
                 data-img="https://images.unsplash.com/photo-1626785773579-ef996f1301bc?q=80&w=1000&auto=format&fit=crop"
                 data-desc="Merancang materi komunikasi visual yang minimalis dan berdampak. Pekerjaan mencakup pembuatan layout presentasi, desain e-sertifikat, poster acara, tipografi, dan elemen identitas visual menggunakan perpaduan perangkat lunak desain modern.">
          <div class="visual" style="background-image: url('https://images.unsplash.com/photo-1626785773579-ef996f1301bc?q=80&w=600&auto=format&fit=crop');"></div>
          <h3>Graphic Design <span>Detail</span></h3>
          <p>Sertifikat, poster, typography, materi promosi, dan presentasi profesional.</p>
          <div class="tags"><span class="tag"><i class="fa-solid fa-pen-nib"></i> Layout</span><span class="tag">Branding</span><span class="tag">Visual</span></div>
        </article>

        <article class="card project reveal stagger-1" data-type="portfolio"
                 data-title="Photography & Video"
                 data-img="https://images.unsplash.com/photo-1516035069371-29a1b244cc32?q=80&w=1000&auto=format&fit=crop"
                 data-desc="Menangkap momen dan mengubahnya menjadi narasi visual (storytelling). Memiliki ketertarikan kuat pada fotografi lanskap, dokumentasi perjalanan riding, dan penyuntingan video pendek bergaya cinematic khusus untuk format Reels atau TikTok.">
          <div class="visual" style="background-image: url('https://images.unsplash.com/photo-1516035069371-29a1b244cc32?q=80&w=600&auto=format&fit=crop');"></div>
          <h3>Photo & Video <span>Detail</span></h3>
          <p>Fotografi lanskap, dokumentasi perjalanan, video pendek, dan editing cinematic.</p>
          <div class="tags"><span class="tag"><i class="fa-solid fa-camera"></i> Photo</span><span class="tag">Video</span><span class="tag">Editing</span></div>
        </article>

        <article class="card project reveal stagger-2" data-type="portfolio"
                 data-title="Web Development"
                 data-img="https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=1000&auto=format&fit=crop"
                 data-desc="Menerjemahkan ide desain menjadi baris kode. Merancang halaman antarmuka web (User Interface) yang interaktif, mulus, dan responsif (berjalan baik di desktop maupun ponsel) menggunakan kombinasi bahasa HTML, CSS modern, dan fungsi JavaScript interaktif.">
          <div class="visual" style="background-image: url('https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=600&auto=format&fit=crop');"></div>
          <h3>Web Project <span>Detail</span></h3>
          <p>Pengembangan landing page dan halaman antarmuka yang interaktif & responsif.</p>
          <div class="tags"><span class="tag"><i class="fa-brands fa-html5"></i> HTML/CSS</span><span class="tag">JavaScript</span><span class="tag">UI/UX</span></div>
        </article>

      </div>
    </section>

    <section class="section" id="skills">
      <div class="section-head reveal">
        <div><div class="kicker">03 / Toolkit</div><h2>Tools & Software.</h2></div>
        <div class="sub">Perangkat lunak penunjang eksekusi kreatif. Klik icon untuk melihat galeri karya di layar penuh.</div>
      </div>
      <div class="skills">
        
        <div class="skill reveal stagger-1" data-type="skill" data-title="Canva" 
             data-desc="Platform kolaboratif untuk mempercepat proses desain. Digunakan untuk layout media sosial, presentasi interaktif, dan grafis informasi ringan."
             data-gallery="https://images.unsplash.com/photo-1611162616305-c69b3fa7fbe0?w=1000&q=80,https://images.unsplash.com/photo-1626785774573-4b799315345d?w=1000&q=80">
          <div class="icon">
            <img src="https://6aad01abe86d4c28a058c63e.imgix.net/sandbox/1.png" alt="Canva Icon">
          </div>
          <strong>Canva</strong>
          <span>Graphic & Layout</span>
          <div class="hint">Buka ↗</div>
        </div>

        <div class="skill reveal stagger-2" data-type="skill" data-title="Photoshop" 
             data-desc="Perangkat pengolahan piksel tingkat lanjut untuk manipulasi foto, seleksi objek presisi tinggi, dan peracikan tipografi digital."
             data-gallery="https://images.unsplash.com/photo-1558655146-d09347e92766?w=1000&q=80,https://images.unsplash.com/photo-1542744094-3a31f272c490?w=1000&q=80">
          <div class="icon">
            <img src="https://6aad01abe86d4c28a058c63e.imgix.net/sandbox/2.png" alt="Photoshop Icon">
          </div>
          <strong>Photoshop</strong>
          <span>Advanced Editing</span>
          <div class="hint">Buka ↗</div>
        </div>

        <div class="skill reveal stagger-3" data-type="skill" data-title="Lightroom" 
             data-desc="Kamar gelap digital saya. Sangat vital untuk konsistensi color grading, manipulasi kurva cahaya, dan manajemen warna foto perjalanan alam."
             data-gallery="https://images.unsplash.com/photo-1558981806-ec527fa84c39?w=1000&q=80,https://images.unsplash.com/photo-1511556820780-d912e42b4980?w=1000&q=80">
          <div class="icon">
            <img src="https://6aad01abe86d4c28a058c63e.imgix.net/sandbox/Desain%20tanpa%20judul.png" alt="Lightroom Icon">
          </div>
          <strong>Lightroom</strong>
          <span>Color Grading</span>
          <div class="hint">Buka ↗</div>
        </div>

        <div class="skill reveal stagger-4" data-type="skill" data-title="CapCut" 
             data-desc="Digunakan untuk eksekusi video vertikal dinamis, memadukan transisi mulus dengan ritme musik, menghasilkan karya visual siap tayang."
             data-gallery="https://images.unsplash.com/photo-1574717024653-61fd2cf4d44d?w=1000&q=80,https://images.unsplash.com/photo-1516035069371-29a1b244cc32?w=1000&q=80">
          <div class="icon">
            <img src="https://6aad01abe86d4c28a058c63e.imgix.net/sandbox/Desain%20tanpa%20judul%20(2).png" alt="CapCut Icon">
          </div>
          <strong>CapCut</strong>
          <span>Video Production</span>
          <div class="hint">Buka ↗</div>
        </div>

      </div>
    </section>

    <section class="section" id="contact">
      <div class="section-head reveal">
        <div><div class="kicker">04 / Contact</div><h2>Let's Connect.</h2></div>
        <div class="sub">Punya proyek kreatif, rencana touring, atau sekadar ingin berbincang?</div>
      </div>
      <div class="contact">
        <div class="card reveal stagger-1">
          <div class="kicker" style="margin-bottom: 12px;">Direct Links</div>
          <p style="margin-bottom: 24px; font-size: 13px;">Jangkau saya melalui platform sosial atau kirim pesan instan langsung ke perangkat saya.</p>
          <div class="social-buttons">
            <a href="https://www.instagram.com/drws.hrs" target="_blank" rel="noopener noreferrer" class="social-btn">
              <i class="fa-brands fa-instagram"></i> Instagram
            </a>
            <a href="https://www.tiktok.com/@drws.hrs" target="_blank" rel="noopener noreferrer" class="social-btn">
              <i class="fa-brands fa-tiktok"></i> TikTok
            </a>
            <a href="https://www.threads.net/@drws.hrs" target="_blank" rel="noopener noreferrer" class="social-btn">
              <i class="fa-brands fa-threads"></i> Threads
            </a>
            <a href="https://wa.me/6285704238724" target="_blank" rel="noopener noreferrer" class="social-btn">
              <i class="fa-brands fa-whatsapp"></i> WhatsApp
            </a>
          </div>
        </div>
        <div class="card reveal stagger-2">
          <form id="contactForm">
            <input id="name" type="text" placeholder="Nama Anda" required>
            <input id="email" type="email" placeholder="Alamat Email" required>
            <textarea id="message" placeholder="Tuliskan pesan atau ide kolaborasi Anda di sini..." required></textarea>
            <button class="btn primary" type="submit" style="width: 100%; justify-content: center; margin-top: 8px;">
              Kirim Pesan via Email
            </button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <span>© 2026 ressss.studio. Crafted with precision.</span>
    <span>Lamongan, Indonesia</span>
  </footer>

  <div id="fullPageView">
    <div class="fp-container">
      <button class="fp-back" id="closeFP"><i class="fa-solid fa-arrow-left"></i> Kembali</button>
      <div id="fpBody">
        </div>
    </div>
  </div>

  <script>
    // ==========================================
    // 1. ANIMASI INTRO / PRELOADER
    // ==========================================
    window.addEventListener('load', () => {
      const introScreen = document.getElementById('intro');
      const text1 = document.getElementById('intro-1');
      const text2 = document.getElementById('intro-2');
      const text3 = document.getElementById('intro-3');

      // Memunculkan text (Fade In Berurutan)
      setTimeout(() => text1.classList.add('active'), 200);
      setTimeout(() => text2.classList.add('active'), 600);
      setTimeout(() => text3.classList.add('active'), 1000);

      // Tarik layar hitam ke atas (seperti gorden)
      setTimeout(() => {
        introScreen.classList.add('hidden');
        document.body.classList.remove('locked'); 
        initScrollReveal();
      }, 2800);
    });

    // ==========================================
    // 2. SCROLL REVEAL
    // ==========================================
    function initScrollReveal() {
      const observerOptions = { threshold: 0.1, rootMargin: '0px 0px -50px 0px' };
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            let delay = 0;
            if(entry.target.classList.contains('stagger-2')) delay = 150;
            if(entry.target.classList.contains('stagger-3')) delay = 300;
            if(entry.target.classList.contains('stagger-4')) delay = 450;
            
            setTimeout(() => {
              entry.target.classList.add('show');
            }, delay);
            observer.unobserve(entry.target);
          }
        });
      }, observerOptions);
      document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
    }

    // ==========================================
    // 3. FITUR-FITUR LAIN (Menu, Parallax, Cursor)
    // ==========================================
    const menu = document.getElementById('menu');
    const navlinks = document.getElementById('navlinks');
    menu.addEventListener('click', () => navlinks.classList.toggle('open'));

    // Smooth Apple Cursor
    const cursor = document.getElementById('cursor');
    let mouseX = 0, mouseY = 0, cursorX = 0, cursorY = 0;
    window.addEventListener('mousemove', e => { mouseX = e.clientX; mouseY = e.clientY; });
    function animateCursor() {
      cursorX += (mouseX - cursorX) * 0.2;
      cursorY += (mouseY - cursorY) * 0.2;
      cursor.style.left = cursorX + 'px';
      cursor.style.top = cursorY + 'px';
      requestAnimationFrame(animateCursor);
    }
    animateCursor();

    // Parallax & Dynamic Navbar
    const heroContent = document.querySelector('.hero-content');
    const profileWrap = document.querySelector('.profile-wrap');
    const navbar = document.getElementById('navbar');
    
    window.addEventListener('scroll', () => {
      const scrollY = window.scrollY;
      
      let current = 'home';
      document.querySelectorAll('main section[id]').forEach(sec => {
        if(scrollY >= sec.offsetTop - 250) current = sec.id;
      });
      document.querySelectorAll('.navlinks a').forEach(a => {
        a.classList.toggle('active', a.getAttribute('href') === '#' + current);
      });

      if(heroContent) heroContent.style.transform = `translateY(${scrollY * 0.15}px)`;
      if(profileWrap) profileWrap.style.transform = `translateY(${scrollY * -0.05}px)`;
      
      if(scrollY > 50) {
        navbar.style.background = 'rgba(5, 11, 22, 0.75)';
        navbar.style.border = '1px solid rgba(255,255,255,0.1)';
      } else {
        navbar.style.background = 'rgba(5, 11, 22, 0.5)';
        navbar.style.border = '1px solid rgba(255,255,255,0.05)';
      }
    });

    // Form Submit (Direct Email Mailto)
    document.getElementById('contactForm').addEventListener('submit', e => {
      e.preventDefault();
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const msg = document.getElementById('message').value;
      const subject = encodeURIComponent('Portofolio: Pesan dari ' + name);
      const body = encodeURIComponent('Halo Darwis,\n\nNama: ' + name + '\nEmail: ' + email + '\n\nPesan:\n' + msg);
      window.location.href = 'mailto:darwisharis.30@gmail.com?subject=' + subject + '&body=' + body;
    });

    // ==========================================
    // 4. LOGIKA HALAMAN PENUH (DETAIL VIEW)
    // ==========================================
    const fullPage = document.getElementById('fullPageView');
    const fpBody = document.getElementById('fpBody');
    const closeFP = document.getElementById('closeFP');

    document.querySelectorAll('.card.project, .skill').forEach(item => {
      item.addEventListener('click', () => {
        const type = item.getAttribute('data-type');
        const title = item.getAttribute('data-title');
        const desc = item.getAttribute('data-desc');

        if (type === 'portfolio') {
          const img = item.getAttribute('data-img');
          const tagsHTML = item.querySelector('.tags').innerHTML;
          
          fpBody.innerHTML = `
            <div class="fp-grid">
              <div class="fp-left">
                <h1 class="fp-title">${title}</h1>
                <p class="fp-desc">${desc}</p>
                
                <div class="fp-stats">
                  <div class="fp-stat-box">
                    <i class="fa-solid fa-code"></i>
                    <div class="lbl">Technologies Used</div>
                    <strong>3+</strong>
                  </div>
                  <div class="fp-stat-box">
                    <i class="fa-solid fa-star"></i>
                    <div class="lbl">Key Features</div>
                    <strong>Tersedia</strong>
                  </div>
                </div>

                <h3 style="font-family:'Space Grotesk'; font-size:18px; margin: 30px 0 15px;">Teknologi & Kategori</h3>
                <div class="tags" style="padding-top:0;">
                  ${tagsHTML}
                </div>
              </div>
              <div class="fp-right">
                <img src="${img}" alt="${title}" class="fp-main-img">
              </div>
            </div>
          `;
        } else if (type === 'skill') {
          const gallery = item.getAttribute('data-gallery').split(',');
          let imagesHTML = gallery.map(src => `<img src="${src}" alt="Gallery ${title}">`).join('');
          fpBody.innerHTML = `
            <div class="fp-grid">
              <div class="fp-left">
                <h1 class="fp-title">${title} Showcase</h1>
                <p class="fp-desc">${desc}</p>
                <div class="fp-stat-box" style="margin-top:20px;">
                    <i class="fa-solid fa-layer-group"></i>
                    <div class="lbl">Total Galeri</div>
                    <strong>${gallery.length} Karya</strong>
                </div>
              </div>
              <div class="fp-right fp-gallery">
                ${imagesHTML}
              </div>
            </div>
          `;
        }
        
        fullPage.scrollTo(0, 0); 
        fullPage.classList.add('active');
        document.body.classList.add('locked'); 
      });
    });

    closeFP.addEventListener('click', () => {
      fullPage.classList.remove('active');
      setTimeout(() => { document.body.classList.remove('locked'); }, 400); 
    });

    // ==========================================
    // 5. FISIKA KARTU 3D
    // ==========================================
    const assembly = document.getElementById('lanyardAssembly');
    let isDragging = false, dragStartX = 0, dragStartY = 0;
    let currentX = 0, currentY = 0, currentZ = 0;
    let targetX = 0, targetY = 0, targetZ = 0;
    let velX = 0, velY = 0, velZ = 0;
    const spring = 0.02, friction = 0.90;

    function startDrag(x, y) { isDragging = true; dragStartX = x; dragStartY = y; assembly.style.cursor = 'grabbing'; }
    function onDrag(x, y) {
      if (!isDragging) return;
      const deltaX = x - dragStartX, deltaY = y - dragStartY; 
      targetZ = -(deltaX * 0.12); targetY = (deltaX * 0.08); targetX = -(deltaY * 0.08); 
    }
    function endDrag() {
      if (!isDragging) return;
      isDragging = false; assembly.style.cursor = 'grab';
      targetX = 0; targetY = 0; targetZ = 0;
    }

    assembly.addEventListener('mousedown', e => { e.preventDefault(); startDrag(e.clientX, e.clientY); });
    window.addEventListener('mousemove', e => onDrag(e.clientX, e.clientY));
    window.addEventListener('mouseup', endDrag); window.addEventListener('mouseleave', endDrag); 
    assembly.addEventListener('touchstart', e => startDrag(e.touches[0].clientX, e.touches[0].clientY), { passive: true });
    window.addEventListener('touchmove', e => onDrag(e.touches[0].clientX, e.touches[0].clientY));
    window.addEventListener('touchend', endDrag);

    function animateCard() {
      velX += (targetX - currentX) * spring; velY += (targetY - currentY) * spring; velZ += (targetZ - currentZ) * spring;
      velX *= friction; velY *= friction; velZ *= friction;
      currentX += velX; currentY += velY; currentZ += velZ;
      
      const time = Date.now() * 0.001;
      let idleX = isDragging ? 0 : Math.sin(time) * 1.5;
      let idleY = isDragging ? 0 : Math.cos(time * 0.8) * 1.5;

      let clampX = Math.max(-45, Math.min(45, currentX + idleX));
      let clampY = Math.max(-45, Math.min(45, currentY + idleY));
      let clampZ = Math.max(-45, Math.min(45, currentZ));

      assembly.style.transform = `rotateX(${clampX}deg) rotateY(${clampY}deg) rotateZ(${clampZ}deg)`;
      requestAnimationFrame(animateCard);
    }
    animateCard();
  </script>
</body>
</html>
