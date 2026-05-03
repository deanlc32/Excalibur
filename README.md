<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Excalibur Consulting</title>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dim: #8A6E2F;
    --dark: #0A0A0F;
    --dark-2: #111118;
    --dark-3: #16161F;
    --dark-4: #1E1E2A;
    --dark-5: #252535;
    --text-primary: #F0EDE6;
    --text-secondary: #9A9AAA;
    --text-muted: #5A5A6A;
    --border: rgba(201,168,76,0.15);
    --border-subtle: rgba(255,255,255,0.06);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--dark);
    color: var(--text-primary);
    font-family: 'Georgia', serif;
    line-height: 1.7;
    font-size: 16px;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    background: rgba(10,10,15,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 0.5px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 3rem;
    height: 64px;
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 10px;
    text-decoration: none;
  }

  .sword-icon {
    width: 22px;
    height: 22px;
    fill: var(--gold);
  }

  .nav-brand {
    font-family: 'Georgia', serif;
    font-size: 17px;
    font-weight: normal;
    letter-spacing: 0.12em;
    color: var(--text-primary);
    text-transform: uppercase;
  }

  .nav-links {
    display: flex;
    align-items: center;
    gap: 2rem;
    list-style: none;
  }

  .nav-links a {
    color: var(--text-secondary);
    text-decoration: none;
    font-family: sans-serif;
    font-size: 13px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--gold); }

  .nav-cta {
    background: transparent;
    border: 0.5px solid var(--gold);
    color: var(--gold) !important;
    padding: 7px 18px;
    border-radius: 2px;
    cursor: pointer;
    font-family: sans-serif;
    font-size: 12px !important;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: background 0.2s, color 0.2s !important;
  }

  .nav-cta:hover {
    background: var(--gold) !important;
    color: var(--dark) !important;
  }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 8rem 2rem 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 50% 40%, rgba(201,168,76,0.06) 0%, transparent 70%),
      radial-gradient(ellipse 40% 60% at 20% 80%, rgba(201,168,76,0.03) 0%, transparent 60%);
  }

  .hero-grid {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
  }

  .hero-content {
    position: relative;
    max-width: 820px;
  }

  .hero-eyebrow {
    font-family: sans-serif;
    font-size: 11px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 2rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
  }

  .eyebrow-line {
    display: inline-block;
    width: 32px;
    height: 0.5px;
    background: var(--gold-dim);
  }

  .hero-title {
    font-family: 'Georgia', serif;
    font-size: clamp(2.4rem, 5vw, 4rem);
    font-weight: normal;
    line-height: 1.2;
    letter-spacing: 0.02em;
    color: var(--text-primary);
    margin-bottom: 1.5rem;
  }

  .hero-title em {
    font-style: italic;
    color: var(--gold-light);
  }

  .hero-sub {
    font-family: sans-serif;
    font-size: 17px;
    color: var(--text-secondary);
    max-width: 580px;
    margin: 0 auto 2.5rem;
    line-height: 1.7;
    font-weight: 300;
  }

  .hero-actions {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--gold);
    color: var(--dark);
    border: none;
    padding: 14px 32px;
    font-family: sans-serif;
    font-size: 13px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    cursor: pointer;
    border-radius: 2px;
    font-weight: 500;
    transition: background 0.2s;
  }

  .btn-primary:hover { background: var(--gold-light); }

  .btn-ghost {
    background: transparent;
    color: var(--text-secondary);
    border: 0.5px solid var(--border-subtle);
    padding: 14px 32px;
    font-family: sans-serif;
    font-size: 13px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    cursor: pointer;
    border-radius: 2px;
    transition: border-color 0.2s, color 0.2s;
  }

  .btn-ghost:hover { border-color: var(--gold-dim); color: var(--text-primary); }

  .hero-stats {
    display: flex;
    justify-content: center;
    gap: 3rem;
    margin-top: 4rem;
    padding-top: 3rem;
    border-top: 0.5px solid var(--border-subtle);
    flex-wrap: wrap;
  }

  .stat-item { text-align: center; }
  .stat-num {
    font-family: 'Georgia', serif;
    font-size: 2rem;
    color: var(--gold-light);
    display: block;
  }
  .stat-label {
    font-family: sans-serif;
    font-size: 12px;
    color: var(--text-muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* SECTION BASE */
  section {
    padding: 6rem 2rem;
  }

  .container {
    max-width: 1080px;
    margin: 0 auto;
  }

  .section-eyebrow {
    font-family: sans-serif;
    font-size: 11px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: 'Georgia', serif;
    font-size: clamp(1.6rem, 3vw, 2.4rem);
    font-weight: normal;
    color: var(--text-primary);
    margin-bottom: 1.5rem;
    line-height: 1.3;
  }

  .section-body {
    font-family: sans-serif;
    font-size: 16px;
    color: var(--text-secondary);
    max-width: 640px;
    line-height: 1.8;
  }

  /* PROBLEM SECTION */
  .problem-section {
    background: var(--dark-2);
    border-top: 0.5px solid var(--border-subtle);
    border-bottom: 0.5px solid var(--border-subtle);
  }

  .problem-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }

  .problem-quote {
    font-family: 'Georgia', serif;
    font-size: 1.4rem;
    font-style: italic;
    color: var(--text-secondary);
    line-height: 1.6;
    border-left: 2px solid var(--gold-dim);
    padding-left: 1.5rem;
  }

  .problem-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .problem-list li {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    font-family: sans-serif;
    font-size: 15px;
    color: var(--text-secondary);
  }

  .x-mark {
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: rgba(180,50,50,0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    margin-top: 3px;
    font-size: 10px;
    color: #e06060;
  }

  /* SERVICES */
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1px;
    background: var(--border-subtle);
    border: 0.5px solid var(--border-subtle);
    margin-top: 3rem;
  }

  .service-card {
    background: var(--dark-2);
    padding: 2rem 1.5rem;
    transition: background 0.2s;
  }

  .service-card:hover { background: var(--dark-3); }

  .service-icon {
    width: 36px;
    height: 36px;
    margin-bottom: 1rem;
    fill: var(--gold-dim);
  }

  .service-name {
    font-family: 'Georgia', serif;
    font-size: 1rem;
    color: var(--text-primary);
    margin-bottom: 0.5rem;
  }

  .service-desc {
    font-family: sans-serif;
    font-size: 13px;
    color: var(--text-muted);
    line-height: 1.6;
  }

  /* HOW IT WORKS */
  .how-section { background: var(--dark-3); }

  .steps {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
    margin-top: 3rem;
    position: relative;
  }

  .step {
    position: relative;
    text-align: center;
    padding: 2rem 1rem;
  }

  .step-num {
    font-family: 'Georgia', serif;
    font-size: 3rem;
    color: rgba(201,168,76,0.12);
    display: block;
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .step-title {
    font-family: 'Georgia', serif;
    font-size: 1.1rem;
    color: var(--gold-light);
    margin-bottom: 0.75rem;
  }

  .step-desc {
    font-family: sans-serif;
    font-size: 14px;
    color: var(--text-secondary);
    line-height: 1.7;
  }

  .step-connector {
    position: absolute;
    top: 2.8rem;
    right: -1rem;
    width: 2rem;
    height: 0.5px;
    background: linear-gradient(90deg, var(--gold-dim), transparent);
  }

  /* WHY EXCALIBUR */
  .why-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
    margin-top: 3rem;
  }

  .differentiator {
    border-bottom: 0.5px solid var(--border-subtle);
    padding: 1.25rem 0;
  }

  .diff-title {
    font-family: sans-serif;
    font-size: 13px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.4rem;
  }

  .diff-desc {
    font-family: sans-serif;
    font-size: 14px;
    color: var(--text-secondary);
    line-height: 1.6;
  }

  .narrative-block {
    background: var(--dark-4);
    border: 0.5px solid var(--border);
    border-radius: 2px;
    padding: 2rem;
  }

  .narrative-text {
    font-family: 'Georgia', serif;
    font-size: 1rem;
    color: var(--text-secondary);
    line-height: 1.9;
    font-style: italic;
  }

  .narrative-text p + p { margin-top: 1rem; }

  /* CTA */
  .cta-section {
    background: var(--dark-2);
    text-align: center;
    border-top: 0.5px solid var(--border);
  }

  .cta-title {
    font-family: 'Georgia', serif;
    font-size: clamp(1.6rem, 3vw, 2.4rem);
    font-weight: normal;
    color: var(--text-primary);
    margin-bottom: 1rem;
  }

  .cta-sub {
    font-family: sans-serif;
    font-size: 16px;
    color: var(--text-secondary);
    margin-bottom: 2.5rem;
  }

  .contact-row {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 1rem;
  }

  .contact-input {
    background: var(--dark-4);
    border: 0.5px solid var(--border-subtle);
    color: var(--text-primary);
    padding: 12px 20px;
    font-family: sans-serif;
    font-size: 14px;
    border-radius: 2px;
    width: 260px;
    outline: none;
    transition: border-color 0.2s;
  }

  .contact-input:focus { border-color: var(--gold-dim); }
  .contact-input::placeholder { color: var(--text-muted); }

  /* FOOTER */
  footer {
    background: var(--dark);
    border-top: 0.5px solid var(--border-subtle);
    padding: 2rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .footer-brand {
    font-family: sans-serif;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--text-muted);
  }

  .footer-copy {
    font-family: sans-serif;
    font-size: 12px;
    color: var(--text-muted);
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#">
    <svg class="sword-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <path d="M14.5 2L21 3l1 6.5-13 13-2-1-1.5-1.5L14.5 2z" fill="none" stroke="#C9A84C" stroke-width="1.2"/>
      <path d="M3 21l4-4" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round"/>
      <path d="M15 6l3 3" stroke="#C9A84C" stroke-width="1" opacity="0.5"/>
      <path d="M8 9l-5 1 1-5" fill="none" stroke="#C9A84C" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <span class="nav-brand">Excalibur</span>
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#how">How It Works</a></li>
    <li><a href="#why">Why Excalibur</a></li>
    <li><a href="#contact" class="nav-cta">Schedule a Call</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">
      <span class="eyebrow-line"></span>
      AI-Powered Business Consulting
      <span class="eyebrow-line"></span>
    </div>
    <h1 class="hero-title">
      Enterprise-Grade Consulting.<br>
      <em>Without the Enterprise Price Tag.</em>
    </h1>
    <p class="hero-sub">
      Excalibur deploys proprietary AI agents and specialized analytical frameworks to deliver the same caliber of business evaluation that top-tier firms charge a premium for — at a tenth of the cost, in a fraction of the time.
    </p>
    <div class="hero-actions">
      <button class="btn-primary" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Schedule a Discovery Call</button>
      <button class="btn-ghost" onclick="document.getElementById('services').scrollIntoView({behavior:'smooth'})">View Our Services</button>
    </div>
    <div class="hero-stats">
      <div class="stat-item">
        <span class="stat-num">1/10</span>
        <span class="stat-label">The cost of traditional firms</span>
      </div>
      <div class="stat-item">
        <span class="stat-num">10×</span>
        <span class="stat-label">Faster time to insight</span>
      </div>
      <div class="stat-item">
        <span class="stat-num">100%</span>
        <span class="stat-label">Tools yours to keep</span>
      </div>
    </div>
  </div>
</section>

<!-- PROBLEM -->
<section class="problem-section">
  <div class="container">
    <div class="problem-layout">
      <div>
        <p class="section-eyebrow">The Problem</p>
        <h2 class="section-title">Most businesses overpay for consulting.</h2>
        <p class="section-body">A McKinsey or EY engagement runs six to seven figures, takes months, and leaves you with a 200-page report that collects dust. The result is dependency, not capability.</p>
      </div>
      <div>
        <ul class="problem-list">
          <li><span class="x-mark">✕</span>Six-to-seven figure engagement fees</li>
          <li><span class="x-mark">✕</span>Months before any actionable output</li>
          <li><span class="x-mark">✕</span>Reports that don't translate to execution</li>
          <li><span class="x-mark">✕</span>No lasting tools or infrastructure left behind</li>
          <li><span class="x-mark">✕</span>Ongoing dependency on the consulting firm</li>
          <li><span class="x-mark">✕</span>Inaccessible to mid-market and growing businesses</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="container">
    <p class="section-eyebrow">What We Do</p>
    <h2 class="section-title">Deep diagnosis. Lasting infrastructure.</h2>
    <p class="section-body">We go deep where it matters — then we build what your team needs to operate at that level long after we're gone.</p>
    <div class="services-grid">
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24"><path d="M3 3h18v18H3z" fill="none" stroke="currentColor" stroke-width="1.2"/><path d="M3 9h18M9 9v12" stroke="currentColor" stroke-width="1.2"/><path d="M13 13h4M13 16h4" stroke="currentColor" stroke-width="1" opacity="0.6"/></svg>
        <p class="service-name">Cash Flow Analysis</p>
        <p class="service-desc">Granular mapping of cash inflows, outflows, and liquidity positions to surface risk and opportunity.</p>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24"><path d="M12 3l9 18H3L12 3z" fill="none" stroke="currentColor" stroke-width="1.2"/><path d="M12 10v5M12 17v.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
        <p class="service-name">Margin Optimization</p>
        <p class="service-desc">Identifying margin compression at every layer — pricing, COGS, overhead — and building a clear path to improvement.</p>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9" fill="none" stroke="currentColor" stroke-width="1.2"/><path d="M12 7v5l3 3" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/></svg>
        <p class="service-name">OPEX Reduction</p>
        <p class="service-desc">Systematic review of operational expenses to eliminate waste, renegotiate vendor terms, and right-size spend.</p>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24"><path d="M4 20l4-8 4 4 4-6 4 4" fill="none" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/></svg>
        <p class="service-name">Throughput Improvement</p>
        <p class="service-desc">Process analysis and workflow redesign to increase output, velocity, and operational efficiency across your business.</p>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2" fill="none" stroke="currentColor" stroke-width="1.2"/><path d="M7 12h10M7 8h6M7 16h8" stroke="currentColor" stroke-width="1" stroke-linecap="round"/></svg>
        <p class="service-name">AI Reporting Dashboards</p>
        <p class="service-desc">Custom-built, AI-driven financial and operational dashboards — built for your data, your team, your decisions.</p>
      </div>
      <div class="service-card">
        <svg class="service-icon" viewBox="0 0 24 24"><path d="M12 3C7 3 3 7 3 12s4 9 9 9 9-4 9-9" fill="none" stroke="currentColor" stroke-width="1.2"/><path d="M18 3l3 3-8 8-3-1-1-3 9-7z" fill="none" stroke="currentColor" stroke-width="1.2" stroke-linejoin="round"/></svg>
        <p class="service-name">Self-Service Analytics</p>
        <p class="service-desc">Tailored analytics platforms that empower your team to answer questions and generate insights without outside help.</p>
      </div>
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->
<section class="how-section" id="how">
  <div class="container">
    <p class="section-eyebrow">The Process</p>
    <h2 class="section-title">Evaluate. Optimize. Empower.</h2>
    <div class="steps">
      <div class="step">
        <span class="step-num">01</span>
        <p class="step-title">Evaluate</p>
        <p class="step-desc">Our AI agents perform a comprehensive business evaluation — financials, operations, margins, and throughput — with the depth of a top-tier engagement.</p>
        <div class="step-connector"></div>
      </div>
      <div class="step">
        <span class="step-num">02</span>
        <p class="step-title">Optimize</p>
        <p class="step-desc">We identify and implement targeted improvements: reducing OPEX, tightening margins, accelerating throughput, and prioritizing the highest-impact levers.</p>
        <div class="step-connector"></div>
      </div>
      <div class="step">
        <span class="step-num">03</span>
        <p class="step-title">Empower</p>
        <p class="step-desc">We build and hand off the tools your team will actually use — AI dashboards, automated reports, and self-service analytics — so the gains compound long after we're gone.</p>
      </div>
    </div>
  </div>
</section>

<!-- WHY EXCALIBUR -->
<section id="why">
  <div class="container">
    <p class="section-eyebrow">Why Excalibur</p>
    <h2 class="section-title">We're not replacing great consulting.<br>We're making it accessible.</h2>
    <div class="why-layout">
      <div>
        <div class="differentiator">
          <p class="diff-title">Fraction of the cost</p>
          <p class="diff-desc">Comparable outcomes to McKinsey or EY at roughly 1/10th the engagement cost, made possible by proprietary AI infrastructure.</p>
        </div>
        <div class="differentiator">
          <p class="diff-title">Speed to insight</p>
          <p class="diff-desc">Where traditional engagements take months, Excalibur moves in weeks — without sacrificing analytical depth.</p>
        </div>
        <div class="differentiator">
          <p class="diff-title">Infrastructure, not just advice</p>
          <p class="diff-desc">Every engagement ends with tools you own — dashboards, automation, and analytics platforms your team uses daily.</p>
        </div>
        <div class="differentiator">
          <p class="diff-title">No ongoing dependency</p>
          <p class="diff-desc">We build for your independence. When we leave, you're more capable than when we arrived — not reliant on the next retainer.</p>
        </div>
      </div>
      <div class="narrative-block">
        <div class="narrative-text">
          <p>When we walk out the door, you're not left with recommendations. You're left with infrastructure.</p>
          <p>Less time buried in spreadsheets. More visibility into what's actually driving your business. A team that makes faster, smarter decisions — without needing to hire an analyst or bring in another consultant.</p>
          <p>The businesses that have always deserved world-class consulting — but could never justify the price tag — that's exactly who we built this for.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="contact">
  <div class="container">
    <p class="section-eyebrow" style="text-align:center;">Get Started</p>
    <h2 class="cta-title">Ready to see what Excalibur can do?</h2>
    <p class="cta-sub">Schedule a no-commitment discovery call. We'll assess your business and outline exactly what an engagement would look like.</p>
    <div class="contact-row">
      <input class="contact-input" type="text" placeholder="Your name" />
      <input class="contact-input" type="email" placeholder="Business email" />
      <button class="btn-primary">Request a Call</button>
    </div>
    <p style="margin-top:1.25rem; font-family:sans-serif; font-size:12px; color:var(--text-muted);">Typical response within one business day.</p>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span class="footer-brand">Excalibur Consulting</span>
  <span class="footer-copy">© 2026 Excalibur. All rights reserved.</span>
</footer>

</body>
</html>
