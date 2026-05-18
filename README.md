
<!DOCTYPE html>
<html>
<head>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Syne:wght@400;600;700;800&display=swap');

  :root {
    --cyan: #00F0FF;
    --pink: #FF006E;
    --purple: #7B2CBF;
    --bg: #0D1117;
    --bg2: #0a0e14;
    --surface: #111820;
    --surface2: #161d27;
    --border: rgba(255,255,255,0.06);
    --border-glow: rgba(0,240,255,0.15);
    --text: #E6EDF3;
    --muted: #8B949E;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── HERO ── */
  .hero {
    position: relative;
    padding: 52px 32px 44px;
    text-align: center;
    background: linear-gradient(180deg, #060c14 0%, #0D1117 100%);
    border-bottom: 1px solid var(--border);
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -60px; left: 50%; transform: translateX(-50%);
    width: 600px; height: 200px;
    background: radial-gradient(ellipse, rgba(0,240,255,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-eyebrow {
    font-size: 10px;
    letter-spacing: 0.25em;
    color: var(--cyan);
    text-transform: uppercase;
    margin-bottom: 14px;
    opacity: 0.7;
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: 52px;
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #ffffff 0%, #a0c4ff 50%, var(--cyan) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
  }

  .hero-sub {
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.05em;
    margin-bottom: 28px;
  }

  .hero-sub span {
    color: rgba(255,255,255,0.35);
    margin: 0 10px;
  }

  /* ── BADGE ROW ── */
  .badge-row {
    display: flex;
    justify-content: center;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 24px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 12px;
    border-radius: 4px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    border: 1px solid;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.2s;
  }

  .badge-cyan {
    background: rgba(0,240,255,0.06);
    border-color: rgba(0,240,255,0.3);
    color: var(--cyan);
  }
  .badge-cyan:hover { background: rgba(0,240,255,0.12); border-color: rgba(0,240,255,0.6); }

  .badge-pink {
    background: rgba(255,0,110,0.06);
    border-color: rgba(255,0,110,0.3);
    color: var(--pink);
  }
  .badge-pink:hover { background: rgba(255,0,110,0.12); border-color: rgba(255,0,110,0.6); }

  .badge-purple {
    background: rgba(123,44,191,0.08);
    border-color: rgba(123,44,191,0.35);
    color: #b57bee;
  }
  .badge-purple:hover { background: rgba(123,44,191,0.15); border-color: rgba(123,44,191,0.65); }

  .badge-white {
    background: rgba(255,255,255,0.04);
    border-color: rgba(255,255,255,0.12);
    color: rgba(255,255,255,0.6);
  }
  .badge-white:hover { background: rgba(255,255,255,0.08); border-color: rgba(255,255,255,0.25); }

  /* ── CTA BUTTONS ── */
  .cta-row {
    display: flex;
    justify-content: center;
    gap: 10px;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 9px 20px;
    border-radius: 5px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    border: 1px solid;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.25s;
  }

  .btn-primary {
    background: var(--cyan);
    border-color: var(--cyan);
    color: #000;
  }
  .btn-primary:hover { background: #33f5ff; box-shadow: 0 0 20px rgba(0,240,255,0.35); }

  .btn-outline-pink {
    background: transparent;
    border-color: rgba(255,0,110,0.5);
    color: var(--pink);
  }
  .btn-outline-pink:hover { background: rgba(255,0,110,0.08); border-color: var(--pink); box-shadow: 0 0 16px rgba(255,0,110,0.2); }

  .btn-outline {
    background: transparent;
    border-color: rgba(255,255,255,0.12);
    color: rgba(255,255,255,0.55);
  }
  .btn-outline:hover { background: rgba(255,255,255,0.05); border-color: rgba(255,255,255,0.25); color: #fff; }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent 0%, rgba(0,240,255,0.2) 20%, rgba(123,44,191,0.3) 50%, rgba(255,0,110,0.2) 80%, transparent 100%);
    margin: 0;
  }

  /* ── SECTION ── */
  .section {
    padding: 40px 32px;
    border-bottom: 1px solid var(--border);
  }

  .section-label {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 28px;
  }

  .section-num {
    font-size: 10px;
    color: var(--cyan);
    opacity: 0.6;
    letter-spacing: 0.15em;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 700;
    color: #fff;
    letter-spacing: -0.01em;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT GRID ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    align-items: start;
  }

  .code-block {
    background: #0a0e14;
    border: 1px solid rgba(0,240,255,0.1);
    border-radius: 8px;
    padding: 18px;
    font-size: 12px;
    line-height: 1.7;
  }

  .code-block .k { color: #ff7b72; }
  .code-block .s { color: #a5d6ff; }
  .code-block .v { color: var(--cyan); }
  .code-block .c { color: var(--muted); }
  .code-block .p { color: rgba(255,255,255,0.4); }

  .about-text {
    font-size: 12.5px;
    color: var(--muted);
    line-height: 1.8;
  }
  .about-text p { margin-bottom: 14px; }
  .about-text strong { color: #c9d1d9; font-weight: 600; }

  /* ── STACK TABLE ── */
  .stack-table {
    width: 100%;
    border-collapse: collapse;
  }
  .stack-table td {
    padding: 10px 14px;
    border-bottom: 1px solid var(--border);
    vertical-align: middle;
  }
  .stack-table td:first-child {
    font-size: 10px;
    letter-spacing: 0.12em;
    color: var(--muted);
    width: 110px;
    white-space: nowrap;
  }
  .stack-table tr:last-child td { border-bottom: none; }

  .pill-group { display: flex; flex-wrap: wrap; gap: 6px; }

  .pill {
    padding: 3px 10px;
    border-radius: 3px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.05em;
    border: 1px solid;
  }

  .pill-cyan { background: rgba(0,240,255,0.05); border-color: rgba(0,240,255,0.2); color: #7aecff; }
  .pill-pink { background: rgba(255,0,110,0.05); border-color: rgba(255,0,110,0.2); color: #ff6ea8; }
  .pill-purple { background: rgba(123,44,191,0.07); border-color: rgba(123,44,191,0.25); color: #c084fc; }
  .pill-green { background: rgba(63,185,80,0.05); border-color: rgba(63,185,80,0.2); color: #7ee787; }
  .pill-amber { background: rgba(240,160,0,0.05); border-color: rgba(240,160,0,0.2); color: #ffa657; }
  .pill-white { background: rgba(255,255,255,0.03); border-color: rgba(255,255,255,0.1); color: rgba(255,255,255,0.45); }

  /* ── PROJECT CARDS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 18px;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    opacity: 0;
    transition: opacity 0.25s;
  }

  .project-card.card-cyan::before { background: linear-gradient(90deg, transparent, var(--cyan), transparent); }
  .project-card.card-pink::before { background: linear-gradient(90deg, transparent, var(--pink), transparent); }
  .project-card.card-purple::before { background: linear-gradient(90deg, transparent, #b57bee, transparent); }
  .project-card.card-green::before { background: linear-gradient(90deg, transparent, #7ee787, transparent); }

  .project-card:hover { border-color: rgba(255,255,255,0.1); transform: translateY(-1px); }
  .project-card:hover::before { opacity: 1; }

  .project-num {
    font-size: 9px;
    letter-spacing: 0.2em;
    margin-bottom: 8px;
  }
  .num-cyan { color: var(--cyan); }
  .num-pink { color: var(--pink); }
  .num-purple { color: #b57bee; }
  .num-green { color: #7ee787; }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }

  .project-desc {
    font-size: 11px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 12px;
  }

  .project-pills { display: flex; flex-wrap: wrap; gap: 5px; margin-bottom: 14px; }

  .project-pill {
    padding: 2px 7px;
    border-radius: 2px;
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 0.05em;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    color: rgba(255,255,255,0.4);
  }

  .project-links { display: flex; gap: 7px; }

  .proj-btn {
    padding: 5px 11px;
    border-radius: 3px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.06em;
    border: 1px solid;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
  }

  .proj-btn-live-cyan { background: rgba(0,240,255,0.07); border-color: rgba(0,240,255,0.25); color: var(--cyan); }
  .proj-btn-live-cyan:hover { background: rgba(0,240,255,0.14); border-color: rgba(0,240,255,0.5); }

  .proj-btn-live-pink { background: rgba(255,0,110,0.07); border-color: rgba(255,0,110,0.25); color: var(--pink); }
  .proj-btn-live-pink:hover { background: rgba(255,0,110,0.14); border-color: rgba(255,0,110,0.5); }

  .proj-btn-live-purple { background: rgba(123,44,191,0.08); border-color: rgba(123,44,191,0.3); color: #b57bee; }
  .proj-btn-live-purple:hover { background: rgba(123,44,191,0.15); border-color: rgba(123,44,191,0.55); }

  .proj-btn-live-green { background: rgba(63,185,80,0.07); border-color: rgba(63,185,80,0.25); color: #7ee787; }
  .proj-btn-live-green:hover { background: rgba(63,185,80,0.14); border-color: rgba(63,185,80,0.5); }

  .proj-btn-gh { background: transparent; border-color: rgba(255,255,255,0.1); color: rgba(255,255,255,0.35); }
  .proj-btn-gh:hover { border-color: rgba(255,255,255,0.25); color: rgba(255,255,255,0.65); }

  .status-dot {
    display: inline-block;
    width: 5px; height: 5px;
    border-radius: 50%;
    margin-right: 5px;
    vertical-align: middle;
  }
  .dot-active { background: #7ee787; box-shadow: 0 0 6px #7ee787; }
  .dot-wip { background: #ffa657; box-shadow: 0 0 6px #ffa657; }

  /* ── CONNECT ── */
  .connect-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: flex-start;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 8px 16px;
    border-radius: 5px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    border: 1px solid;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    font-family: 'JetBrains Mono', monospace;
  }

  .social-li { background: rgba(10,102,194,0.07); border-color: rgba(10,102,194,0.3); color: #4f9fea; }
  .social-li:hover { background: rgba(10,102,194,0.14); border-color: rgba(10,102,194,0.6); box-shadow: 0 0 14px rgba(10,102,194,0.15); }

  .social-em { background: rgba(234,67,53,0.07); border-color: rgba(234,67,53,0.3); color: #f78070; }
  .social-em:hover { background: rgba(234,67,53,0.14); border-color: rgba(234,67,53,0.6); box-shadow: 0 0 14px rgba(234,67,53,0.15); }

  .social-gh { background: rgba(255,255,255,0.04); border-color: rgba(255,255,255,0.12); color: rgba(255,255,255,0.55); }
  .social-gh:hover { background: rgba(255,255,255,0.08); border-color: rgba(255,255,255,0.25); color: #fff; }

  .social-ig { background: rgba(228,64,95,0.07); border-color: rgba(228,64,95,0.25); color: #f4758a; }
  .social-ig:hover { background: rgba(228,64,95,0.14); border-color: rgba(228,64,95,0.5); }

  .social-pi { background: rgba(230,0,35,0.07); border-color: rgba(230,0,35,0.25); color: #f47070; }
  .social-pi:hover { background: rgba(230,0,35,0.14); border-color: rgba(230,0,35,0.5); }

  .social-lc { background: rgba(255,161,22,0.07); border-color: rgba(255,161,22,0.25); color: #ffa657; }
  .social-lc:hover { background: rgba(255,161,22,0.14); border-color: rgba(255,161,22,0.5); }

  /* ── FOOTER ── */
  .footer {
    padding: 28px 32px;
    text-align: center;
    background: var(--bg2);
  }
  .footer-text {
    font-size: 11px;
    color: rgba(255,255,255,0.18);
    letter-spacing: 0.08em;
  }
  .footer-sig { color: rgba(0,240,255,0.35); }

  .dot-sep { color: rgba(255,255,255,0.12); margin: 0 8px; }
</style>

<div style="background:#0D1117; min-height:100vh;">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-eyebrow">// full-stack engineer · vadodara, india</div>
    <div class="hero-name">JOEL KUNJUMON</div>
    <div class="hero-sub">
      React · Node · MongoDB<span>◆</span>Motion · Architecture · Systems
    </div>

    <div class="badge-row">
      <span class="badge badge-cyan">👁 Profile Views</span>
      <span class="badge badge-pink">⭐ GitHub Stars</span>
      <span class="badge badge-purple">◈ Followers</span>
      <span class="badge badge-white">● Open to Work</span>
    </div>

    <div class="cta-row">
      <span class="btn btn-primary">↗ Portfolio</span>
      <span class="btn btn-outline-pink">✉ Email Me</span>
      <span class="btn btn-outline">❖ LinkedIn</span>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-label">
      <span class="section-num">01</span>
      <span class="section-title">About</span>
      <div class="section-line"></div>
    </div>
    <div class="about-grid">
      <div class="code-block">
        <span class="k">const</span> <span class="v">joel</span> <span class="p">= {</span><br/>
        &nbsp;&nbsp;<span class="c">role:</span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="s">"Full-Stack Engineer"</span><span class="p">,</span><br/>
        &nbsp;&nbsp;<span class="c">focus:</span>&nbsp;&nbsp;&nbsp;<span class="s">"Motion · Architecture · UX"</span><span class="p">,</span><br/>
        &nbsp;&nbsp;<span class="c">stack:</span>&nbsp;&nbsp;&nbsp;<span class="p">[</span><span class="s">"React"</span><span class="p">,</span> <span class="s">"Node"</span><span class="p">,</span> <span class="s">"MongoDB"</span><span class="p">],</span><br/>
        &nbsp;&nbsp;<span class="c">building:</span>&nbsp;<span class="p">[</span><span class="s">"SaaS"</span><span class="p">,</span> <span class="s">"Dashboards"</span><span class="p">,</span> <span class="s">"AI Tools"</span><span class="p">],</span><br/>
        &nbsp;&nbsp;<span class="c">ethos:</span>&nbsp;&nbsp;&nbsp;<span class="s">"Pixel-precision frontends,<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;systems that scale."</span><br/>
        <span class="p">}</span>
      </div>
      <div class="about-text">
        <p>I architect <strong>clean MERN systems</strong> and obsess over how an app <em>feels</em> in motion. I care about the small details — easing curves, layout rhythm, request waterfalls — because those separate a project from a product.</p>
        <p>Currently building <strong>VaultBet</strong> (provably fair casino platform) and <strong>MeetConnect</strong> (WebRTC video app), while pursuing my MCA at Parul University.</p>
        <p>Open to <strong>full-time roles</strong>, freelance collabs, and interesting product conversations.</p>
      </div>
    </div>
  </div>

  <!-- STACK -->
  <div class="section">
    <div class="section-label">
      <span class="section-num">02</span>
      <span class="section-title">Tech Stack</span>
      <div class="section-line"></div>
    </div>
    <table class="stack-table">
      <tr>
        <td>Frontend</td>
        <td><div class="pill-group">
          <span class="pill pill-cyan">React</span>
          <span class="pill pill-cyan">Next.js</span>
          <span class="pill pill-cyan">Vite</span>
          <span class="pill pill-cyan">TypeScript</span>
          <span class="pill pill-cyan">Tailwind</span>
          <span class="pill pill-cyan">SASS</span>
          <span class="pill pill-cyan">Redux</span>
        </div></td>
      </tr>
      <tr>
        <td>Backend</td>
        <td><div class="pill-group">
          <span class="pill pill-pink">Node.js</span>
          <span class="pill pill-pink">Express</span>
          <span class="pill pill-pink">Socket.IO</span>
          <span class="pill pill-pink">JWT</span>
          <span class="pill pill-pink">REST APIs</span>
        </div></td>
      </tr>
      <tr>
        <td>Database</td>
        <td><div class="pill-group">
          <span class="pill pill-green">MongoDB</span>
          <span class="pill pill-green">Redis</span>
          <span class="pill pill-green">MySQL</span>
        </div></td>
      </tr>
      <tr>
        <td>Motion · 3D</td>
        <td><div class="pill-group">
          <span class="pill pill-purple">GSAP</span>
          <span class="pill pill-purple">Three.js</span>
          <span class="pill pill-purple">Framer</span>
          <span class="pill pill-purple">Lenis</span>
        </div></td>
      </tr>
      <tr>
        <td>Cloud · DevOps</td>
        <td><div class="pill-group">
          <span class="pill pill-amber">AWS</span>
          <span class="pill pill-amber">Vercel</span>
          <span class="pill pill-amber">Render</span>
          <span class="pill pill-amber">GitHub Actions</span>
        </div></td>
      </tr>
      <tr>
        <td>Tools</td>
        <td><div class="pill-group">
          <span class="pill pill-white">Git</span>
          <span class="pill pill-white">Postman</span>
          <span class="pill pill-white">Figma</span>
          <span class="pill pill-white">VS Code</span>
          <span class="pill pill-white">Linux</span>
        </div></td>
      </tr>
    </table>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-label">
      <span class="section-num">03</span>
      <span class="section-title">Featured Work</span>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <div class="project-card card-cyan">
        <div class="project-num num-cyan">01 · CASINO PLATFORM</div>
        <div class="project-name">VaultBet</div>
        <div class="project-desc"><span class="status-dot dot-wip"></span>In Progress &nbsp;·&nbsp; 5 provably fair games with real-time crash engine, JWT + Redis auth, HMAC-SHA256 sessions.</div>
        <div class="project-pills">
          <span class="project-pill">React</span><span class="project-pill">Node.js</span><span class="project-pill">Socket.IO</span><span class="project-pill">Redis</span><span class="project-pill">MongoDB</span>
        </div>
        <div class="project-links">
          <span class="proj-btn proj-btn-live-cyan">↗ Live Demo</span>
          <span class="proj-btn proj-btn-gh">GitHub</span>
        </div>
      </div>

      <div class="project-card card-pink">
        <div class="project-num num-pink">02 · WEBRTC APP</div>
        <div class="project-name">MeetConnect</div>
        <div class="project-desc"><span class="status-dot dot-wip"></span>In Progress &nbsp;·&nbsp; P2P video calling, Socket.IO signaling, custom DateTimePicker, meeting link dashboard.</div>
        <div class="project-pills">
          <span class="project-pill">React</span><span class="project-pill">WebRTC</span><span class="project-pill">Socket.IO</span><span class="project-pill">Node.js</span>
        </div>
        <div class="project-links">
          <span class="proj-btn proj-btn-live-pink">↗ Live Demo</span>
          <span class="proj-btn proj-btn-gh">GitHub</span>
        </div>
      </div>

      <div class="project-card card-purple">
        <div class="project-num num-purple">03 · TRAVEL PLATFORM</div>
        <div class="project-name">WanderLust</div>
        <div class="project-desc"><span class="status-dot dot-active"></span>Active &nbsp;·&nbsp; Airbnb-like platform with Mapbox, Razorpay payments, Cloudinary, OAuth, multi-step listing UI.</div>
        <div class="project-pills">
          <span class="project-pill">MERN</span><span class="project-pill">Mapbox</span><span class="project-pill">Razorpay</span><span class="project-pill">Cloudinary</span>
        </div>
        <div class="project-links">
          <span class="proj-btn proj-btn-live-purple">↗ Live Demo</span>
          <span class="proj-btn proj-btn-gh">GitHub</span>
        </div>
      </div>

      <div class="project-card card-green">
        <div class="project-num num-green">04 · CODE COLLAB</div>
        <div class="project-name">CodeDrop</div>
        <div class="project-desc"><span class="status-dot dot-active"></span>Shipped &nbsp;·&nbsp; Real-time code editor with Monaco, AI explanations, version history, permission-based editing.</div>
        <div class="project-pills">
          <span class="project-pill">React</span><span class="project-pill">Monaco Editor</span><span class="project-pill">Socket.IO</span><span class="project-pill">Node.js</span>
        </div>
        <div class="project-links">
          <span class="proj-btn proj-btn-live-green">↗ Live Demo</span>
          <span class="proj-btn proj-btn-gh">GitHub</span>
        </div>
      </div>

    </div>
  </div>

  <!-- CONNECT -->
  <div class="section">
    <div class="section-label">
      <span class="section-num">06</span>
      <span class="section-title">Let's Connect</span>
      <div class="section-line"></div>
    </div>
    <div class="connect-grid">
      <span class="social-btn social-li">❖ LinkedIn</span>
      <span class="social-btn social-em">✉ Email</span>
      <span class="social-btn social-gh">⬡ GitHub</span>
      <span class="social-btn social-lc">◈ LeetCode</span>
      <span class="social-btn social-ig">◎ Instagram</span>
      <span class="social-btn social-pi">◇ Pinterest</span>
    </div>
    <div style="margin-top: 18px; padding: 14px 18px; background: rgba(0,240,255,0.03); border: 1px solid rgba(0,240,255,0.1); border-radius: 5px; font-size: 11px; color: var(--muted);">
      Open to <span style="color:var(--cyan)">full-time roles</span>, freelance, collaborations, and serious product conversations.
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-text">
      <span class="footer-sig">// signed, Joel Kunjumon</span>
      <span class="dot-sep">·</span>
      Built with craft
      <span class="dot-sep">·</span>
      Shipped with care
      <span class="dot-sep">·</span>
      <span class="footer-sig">see you in the next deploy ↗</span>
    </div>
  </div>

</div>
