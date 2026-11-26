# Lightstories
Photography 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Lightstories — Photography</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,500;0,9..144,600;1,9..144,400&family=Work+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    color-scheme: light dark;
    --bg: #F4EFE5;
    --bg-soft: #ECE4D4;
    --ink: #1B1812;
    --ink-soft: #5C5648;
    --line: rgba(27,24,18,0.14);
    --brass: #A9792F;
    --panel: #FFFFFF;
    --radius: 2px;
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #17140F;
      --bg-soft: #1F1B14;
      --ink: #F3EDE1;
      --ink-soft: #B9AF9B;
      --line: rgba(243,237,225,0.14);
      --brass: #D3A54C;
      --panel: #221D15;
    }
  }
  :root[data-theme="dark"] {
    --bg: #17140F;
    --bg-soft: #1F1B14;
    --ink: #F3EDE1;
    --ink-soft: #B9AF9B;
    --line: rgba(243,237,225,0.14);
    --brass: #D3A54C;
    --panel: #221D15;
  }
  * { box-sizing: border-box; }
  html {
    scroll-behavior: smooth;
    scroll-padding-top: calc(72px + env(safe-area-inset-top, 0px));
  }
  body {
    margin: 0;
    background: var(--bg);
    color: var(--ink);
    font-family: "Work Sans", -apple-system, "Segoe UI", sans-serif;
    font-weight: 300;
    line-height: 1.55;
    padding-top: env(safe-area-inset-top, 0px);
    padding-bottom: env(safe-area-inset-bottom, 0px);
    -webkit-text-size-adjust: 100%;
  }
  body::before {
    content: "";
    position: fixed;
    inset: 0 0 auto;
    height: env(safe-area-inset-top, 0px);
    z-index: 10;
    background: var(--bg);
  }
  h1, h2, h3, .display {
    font-family: "Fraunces", Georgia, serif;
    font-weight: 500;
    letter-spacing: -0.01em;
    margin: 0;
  }
  a { color: inherit; }
  img, svg { max-width: 100%; }

  .wrap { max-width: 1180px; margin: 0 auto; padding: 0 clamp(20px, 5vw, 56px); }

  /* ---------- Nav ---------- */
  nav {
    position: sticky;
    top: env(safe-area-inset-top, 0px);
    z-index: 5;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 18px clamp(20px, 5vw, 56px);
    background: color-mix(in srgb, var(--bg) 88%, transparent);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--line);
  }
  .logo {
    font-family: "Fraunces", serif;
    font-size: 1.15rem;
    font-weight: 500;
    text-decoration: none;
  }
  .logo em { font-style: italic; color: var(--brass); }
  .navlinks { display: flex; gap: clamp(16px, 3vw, 34px); align-items: center; }
  .navlinks a {
    text-decoration: none;
    font-size: 0.92rem;
    color: var(--ink-soft);
    transition: color .2s ease;
  }
  .navlinks a:hover, .navlinks a:focus-visible { color: var(--ink); }
  .navlinks a.cta {
    color: var(--ink);
    border: 1px solid var(--line);
    padding: 8px 16px;
    border-radius: var(--radius);
  }
  .navlinks a.cta:hover { border-color: var(--brass); color: var(--brass); }

  /* ---------- Hero ---------- */
  .hero {
    position: relative;
    padding: clamp(64px, 14vh, 150px) 0 clamp(48px, 9vh, 96px);
    overflow: hidden;
  }
  .hero-glow {
    position: absolute;
    width: 520px; height: 520px;
    border-radius: 50%;
    background: radial-gradient(circle, color-mix(in srgb, var(--brass) 35%, transparent) 0%, transparent 70%);
    top: -180px; right: -120px;
    pointer-events: none;
    filter: blur(10px);
  }
  .kicker {
    font-size: 0.95rem;
    color: var(--ink-soft);
    max-width: 30ch;
    margin-bottom: 22px;
  }
  h1.display {
    font-size: clamp(2.6rem, 7vw, 5.2rem);
    line-height: 0.98;
    max-width: 14ch;
  }
  .hero-foot {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
    margin-top: clamp(36px, 7vh, 64px);
    padding-top: 28px;
    border-top: 1px solid var(--line);
  }
  .hero-foot p { max-width: 42ch; color: var(--ink-soft); font-size: 0.95rem; margin: 0; }
  .hero-foot .stat strong { display: block; font-family: "Fraunces", serif; font-size: 1.6rem; font-weight: 500; }
  .hero-foot .stat span { font-size: 0.82rem; color: var(--ink-soft); }

  /* ---------- Section shells ---------- */
  section { padding: clamp(56px, 10vh, 110px) 0; }
  .section-head {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    gap: 24px;
    margin-bottom: clamp(32px, 6vh, 56px);
    border-bottom: 1px solid var(--line);
    padding-bottom: 20px;
  }
  .section-head h2 { font-size: clamp(1.7rem, 4vw, 2.5rem); font-weight: 500; }
  .section-head p { color: var(--ink-soft); max-width: 36ch; margin: 0; font-size: 0.95rem; }

  /* ---------- Gallery ---------- */
  .gallery {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: clamp(10px, 1.6vw, 18px);
  }
  .frame {
    position: relative;
    border-radius: var(--radius);
    overflow: hidden;
    aspect-ratio: 4 / 5;
    display: flex;
    align-items: flex-end;
    padding: 16px;
    color: #fff;
    isolation: isolate;
  }
  .frame::after {
    content: "";
    position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(0,0,0,0.55), transparent 55%);
    z-index: 0;
  }
  .frame span { position: relative; z-index: 1; font-size: 0.82rem; }
  .frame span strong { display: block; font-family: "Fraunces", serif; font-size: 1.05rem; font-weight: 500; }
  .f1 { grid-column: span 3; background: linear-gradient(145deg, #E7A94A, #9A4B2E 70%); }
  .f2 { grid-column: span 3; background: linear-gradient(160deg, #2B3A52, #0F1420 75%); }
  .f3 { grid-column: span 2; aspect-ratio: 4/4.6; background: linear-gradient(150deg, #C98A6B, #5B2E2A 80%); }
  .f4 { grid-column: span 2; aspect-ratio: 4/4.6; background: linear-gradient(150deg, #8C93A6, #30323D 80%); }
  .f5 { grid-column: span 2; aspect-ratio: 4/4.6; background: linear-gradient(150deg, #E7C27D, #7A5A2E 80%); }
  .f6 { grid-column: span 4; background: linear-gradient(135deg, #4A3340, #1A1420 70%); }
  .f7 { grid-column: span 2; background: linear-gradient(150deg, #D98F6B, #40221F 80%); }

  /* ---------- About ---------- */
  .about-grid {
    display: grid;
    grid-template-columns: 1.1fr 1fr;
    gap: clamp(32px, 6vw, 80px);
    align-items: center;
  }
  .about-grid .portrait {
    aspect-ratio: 3/4;
    border-radius: var(--radius);
    background: linear-gradient(160deg, #D9B56C, #4A2E1C 85%);
  }
  .about-grid p { color: var(--ink-soft); font-size: 1.02rem; max-width: 46ch; }
  .about-grid p + p { margin-top: 16px; }

  /* ---------- Services ---------- */
  .services {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--line);
    border: 1px solid var(--line);
  }
  .service {
    background: var(--bg);
    padding: 30px 26px;
  }
  .service h3 { font-size: 1.2rem; font-weight: 500; margin-bottom: 10px; }
  .service p { color: var(--ink-soft); font-size: 0.92rem; margin: 0; }

  /* ---------- Contact ---------- */
  footer {
    background: var(--bg-soft);
    border-top: 1px solid var(--line);
    padding: clamp(56px, 10vh, 100px) 0 40px;
  }
  .contact-grid {
    display: grid;
    grid-template-columns: 1.3fr 1fr;
    gap: 40px;
    align-items: start;
  }
  footer h2.display { font-size: clamp(2rem, 5vw, 3.4rem); max-width: 12ch; }
  .contact-list { list-style: none; margin: 28px 0 0; padding: 0; display: flex; flex-direction: column; gap: 14px; }
  .contact-list a { text-decoration: none; font-size: 1.05rem; border-bottom: 1px solid var(--line); padding-bottom: 14px; display: flex; justify-content: space-between; }
  .contact-list a span:last-child { color: var(--brass); }
  .contact-list a:hover span:last-child { text-decoration: underline; }
  .fineprint { margin-top: 56px; color: var(--ink-soft); font-size: 0.82rem; display: flex; justify-content: space-between; flex-wrap: wrap; gap: 10px; }

  @media (max-width: 760px) {
    .navlinks a:not(.cta) { display: none; }
    .gallery { grid-template-columns: repeat(2, 1fr); }
    .f1, .f2, .f6 { grid-column: span 2; }
    .f3, .f4, .f5, .f7 { grid-column: span 1; }
    .about-grid, .contact-grid { grid-template-columns: 1fr; }
    .services { grid-template-columns: 1fr; }
  }

  :focus-visible { outline: 2px solid var(--brass); outline-offset: 3px; }
  @media (prefers-reduced-motion: reduce) {
    html { scroll-behavior: auto; }
    * { transition: none !important; }
  }
</style>
</head>
<body>

<nav>
  <a href="#" class="logo">Light<em>stories</em></a>
  <div class="navlinks">
    <a href="#work">Work</a>
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#contact" class="cta">Get in touch</a>
  </div>
</nav>

<section class="hero">
  <div class="hero-glow" aria-hidden="true"></div>
  <div class="wrap">
    <p class="kicker">Lightstories Photography</p>
    <h1 class="display">Photographs built around the way light actually falls.</h1>
    <div class="hero-foot">
      <p>We photograph weddings, portraits and quiet in-between moments — chasing whatever light a day gives us, golden or grey, and building the story around it.</p>
      <div class="stat">
        <strong>200+</strong>
        <span>stories told</span>
      </div>
      <div class="stat">
        <strong>9</strong>
        <span>years shooting</span>
      </div>
    </div>
  </div>
</section>

<section id="work">
  <div class="wrap">
    <div class="section-head">
      <h2>Selected work</h2>
      <p>A handful of light conditions we keep coming back to — swap these frames for your own galleries.</p>
    </div>
    <div class="gallery">
      <div class="frame f1"><span>Golden hour<strong>Weddings</strong></span></div>
      <div class="frame f2"><span>Blue hour<strong>Editorial</strong></span></div>
      <div class="frame f3"><span>Window light<strong>Portraits</strong></span></div>
      <div class="frame f4"><span>Overcast<strong>Lifestyle</strong></span></div>
      <div class="frame f5"><span>Tungsten<strong>Events</strong></span></div>
      <div class="frame f6"><span>Candlelight<strong>Receptions</strong></span></div>
      <div class="frame f7"><span>Studio<strong>Portraiture</strong></span></div>
    </div>
  </div>
</section>

<section id="about" style="background:var(--bg-soft)">
  <div class="wrap about-grid">
    <div class="portrait" role="img" aria-label="Portrait placeholder"></div>
    <div>
      <h2 style="font-size:clamp(1.8rem,4vw,2.6rem); margin-bottom:18px;">About the studio</h2>
      <p>Lightstories started on the floor of a spare bedroom with one camera and a habit of noticing how afternoon light moved across a room. It's grown into a small studio built on the same instinct — watch first, then photograph.</p>
      <p>Every booking starts with a conversation about the people in front of the lens, not a shot list. The goal is always the same: pictures you'll still want on your wall in twenty years.</p>
    </div>
  </div>
</section>

<section id="services">
  <div class="wrap">
    <div class="section-head" style="border-bottom:none; padding-bottom:0;">
      <h2>What we shoot</h2>
      <p>Four ways to work with the studio.</p>
    </div>
  </div>
  <div class="wrap" style="padding-top:0;">
    <div class="services">
      <div class="service">
        <h3>Weddings</h3>
        <p>Full-day coverage, documentary-first, with a short list of must-have portraits planned in advance.</p>
      </div>
      <div class="service">
        <h3>Portraits</h3>
        <p>Individuals, couples and families, shot on location or in natural window light.</p>
      </div>
      <div class="service">
        <h3>Editorial & events</h3>
        <p>Brand shoots, launches and gatherings — fast-paced, low-intervention coverage.</p>
      </div>
      <div class="service">
        <h3>Prints & albums</h3>
        <p>Fine-art prints and hand-bound albums from any session, made after final selects.</p>
      </div>
    </div>
  </div>
</section>

<footer id="contact">
  <div class="wrap contact-grid">
    <div>
      <h2 class="display">Let's talk about your light.</h2>
      <p style="color:var(--ink-soft); max-width:40ch; margin-top:16px;">Tell us the date, the place, and who'll be in the frame — we'll tell you what the light's likely to do.</p>
    </div>
    <ul class="contact-list">
      <li><a href="https://instagram.com/lightstories__" target="_blank" rel="noopener"><span>Instagram</span><span>@lightstories__</span></a></li>
      <li><a href="mailto:hello@lightstories.studio"><span>Email</span><span>hello@lightstories.studio</span></a></li>
      <li><a href="#"><span>Based in</span><span>Your city</span></a></li>
    </ul>
  </div>
  <div class="wrap fineprint">
    <span>© 2026 Lightstories Photography</span>
    <span>Built with care</span>
  </div>
</footer>

</body>
</html>
