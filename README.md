

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Devie Rose Marmolejo — Software QA Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
<style>
  :root {
    --blush: #f5e6e8;
    --rose: #c9848f;
    --rose-deep: #9e5f69;
    --mauve: #d4a5ab;
    --cream: #fdf8f5;
    --warm-white: #fefcfa;
    --ink: #2d2323;
    --ink-light: #5a4a4a;
    --sage: #b8c4b8;
    --gold: #c8a96e;
    --border: rgba(201,132,143,0.2);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--ink);
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: rgba(253,248,245,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    padding: 1rem 2.5rem;
    display: flex; justify-content: space-between; align-items: center;
  }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.2rem; font-weight: 300; letter-spacing: 0.08em;
    color: var(--rose-deep);
  }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    font-size: 0.78rem; letter-spacing: 0.12em; text-transform: uppercase;
    color: var(--ink-light); text-decoration: none;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--rose-deep); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 7rem 5rem 4rem;
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; top: -20%; right: -10%;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(212,165,171,0.25) 0%, transparent 70%);
    border-radius: 50%; pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute; bottom: -15%; left: 20%;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(201,132,143,0.12) 0%, transparent 70%);
    border-radius: 50%; pointer-events: none;
  }
  .hero-text { position: relative; z-index: 2; }
  .hero-eyebrow {
    font-size: 0.72rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--rose); margin-bottom: 1.2rem;
    display: flex; align-items: center; gap: 0.8rem;
  }
  .hero-eyebrow::before {
    content: ''; display: block; width: 30px; height: 1px; background: var(--mauve);
  }
  .hero-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(3rem, 5vw, 4.5rem);
    font-weight: 300; line-height: 1.1;
    color: var(--ink); margin-bottom: 0.5rem;
  }
  .hero-name em { color: var(--rose-deep); font-style: italic; }
  .hero-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.4rem; font-weight: 300; font-style: italic;
    color: var(--ink-light); margin-bottom: 2rem;
  }
  .hero-tagline {
    font-size: 1rem; line-height: 1.8; color: var(--ink-light);
    max-width: 460px; margin-bottom: 2.5rem;
  }
  .hero-tagline strong { color: var(--rose-deep); font-weight: 500; }
  .hero-ctas { display: flex; gap: 1rem; flex-wrap: wrap; }
  .btn-primary {
    padding: 0.85rem 2rem; background: var(--rose-deep); color: white;
    border: none; border-radius: 40px; font-size: 0.82rem;
    letter-spacing: 0.08em; text-transform: uppercase; cursor: pointer;
    text-decoration: none; transition: all 0.3s;
    font-family: 'DM Sans', sans-serif;
  }
  .btn-primary:hover { background: var(--rose); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(158,95,105,0.3); }
  .btn-secondary {
    padding: 0.85rem 2rem; background: transparent; color: var(--rose-deep);
    border: 1.5px solid var(--mauve); border-radius: 40px; font-size: 0.82rem;
    letter-spacing: 0.08em; text-transform: uppercase; cursor: pointer;
    text-decoration: none; transition: all 0.3s;
    font-family: 'DM Sans', sans-serif;
  }
  .btn-secondary:hover { border-color: var(--rose-deep); transform: translateY(-2px); }

  /* PHOTO SIDE */
  .hero-visual {
    display: flex; justify-content: center; align-items: center;
    position: relative; z-index: 2;
  }
  .photo-ring {
    position: relative; width: 340px; height: 340px;
  }
  .photo-ring::before {
    content: '';
    position: absolute; inset: -12px;
    border-radius: 50%;
    background: conic-gradient(var(--mauve), var(--blush), var(--rose), var(--mauve));
    animation: spin 12s linear infinite;
    opacity: 0.6;
  }
  .photo-ring::after {
    content: '';
    position: absolute; inset: -6px;
    background: var(--cream);
    border-radius: 50%;
  }
  @keyframes spin { to { transform: rotate(360deg); } }
  .photo-frame {
    position: absolute; inset: 0; z-index: 2;
    border-radius: 50%; overflow: hidden;
    background: var(--blush);
  }
  .photo-frame img {
    width: 100%; height: 100%; object-fit: cover;
    object-position: center top;
  }

  /* BADGES */
  .hero-badges {
    display: flex; gap: 0.6rem; flex-wrap: wrap; margin-top: 1.5rem;
  }
  .badge {
    padding: 0.35rem 0.9rem;
    background: var(--blush); border-radius: 20px;
    font-size: 0.72rem; letter-spacing: 0.06em; color: var(--rose-deep);
    border: 1px solid var(--border);
  }

  /* SECTION SHARED */
  section { padding: 5rem 5rem; }
  .section-label {
    font-size: 0.68rem; letter-spacing: 0.22em; text-transform: uppercase;
    color: var(--mauve); margin-bottom: 0.6rem;
    display: flex; align-items: center; gap: 0.8rem;
  }
  .section-label::after {
    content: ''; flex: 1; max-width: 40px; height: 1px; background: var(--mauve);
  }
  .section-heading {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 3.5vw, 3rem); font-weight: 300;
    line-height: 1.2; margin-bottom: 1rem;
  }

  /* WHY QA IN AI ERA */
  .ai-era {
    background: linear-gradient(135deg, #2d2323 0%, #3d2e2e 100%);
    color: white; position: relative; overflow: hidden;
  }
  .ai-era::before {
    content: '';
    position: absolute; top: -50%; right: -10%;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(201,132,143,0.15) 0%, transparent 60%);
    border-radius: 50%;
  }
  .ai-era .section-label { color: var(--mauve); }
  .ai-era .section-heading { color: white; }
  .ai-era-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 2rem; margin-top: 3rem;
  }
  .ai-card {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(201,132,143,0.2);
    border-radius: 16px; padding: 2rem;
    transition: all 0.3s;
    position: relative; overflow: hidden;
  }
  .ai-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--rose), transparent);
    opacity: 0; transition: opacity 0.3s;
  }
  .ai-card:hover { background: rgba(255,255,255,0.07); transform: translateY(-4px); }
  .ai-card:hover::before { opacity: 1; }
  .ai-card-icon { font-size: 1.8rem; margin-bottom: 1rem; }
  .ai-card h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.3rem; font-weight: 400; color: white; margin-bottom: 0.6rem;
  }
  .ai-card p { font-size: 0.88rem; color: rgba(255,255,255,0.65); line-height: 1.7; }
  .ai-card .stat {
    margin-top: 1rem; font-size: 1.8rem; font-weight: 300;
    font-family: 'Cormorant Garamond', serif; color: var(--mauve);
  }

  /* VIBE CODING CALLOUT */
  .vibe-strip {
    background: var(--blush); padding: 3rem 5rem;
    display: flex; gap: 3rem; align-items: center;
    border-top: 1px solid var(--border); border-bottom: 1px solid var(--border);
  }
  .vibe-icon { font-size: 3rem; flex-shrink: 0; }
  .vibe-text h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.8rem; font-weight: 400; margin-bottom: 0.5rem;
  }
  .vibe-text h3 em { color: var(--rose-deep); }
  .vibe-text p { font-size: 0.9rem; line-height: 1.75; color: var(--ink-light); max-width: 700px; }

  /* VALUE / SAVE MONEY */
  .value-section { background: var(--warm-white); }
  .value-grid {
    display: grid; grid-template-columns: repeat(3,1fr);
    gap: 1.5rem; margin-top: 3rem;
  }
  .value-card {
    background: white; border-radius: 16px; padding: 2rem;
    border: 1px solid var(--border);
    transition: all 0.3s; position: relative;
  }
  .value-card:hover { box-shadow: 0 12px 40px rgba(158,95,105,0.1); transform: translateY(-3px); }
  .value-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 3.5rem; font-weight: 300; color: var(--rose);
    line-height: 1; margin-bottom: 0.3rem;
  }
  .value-card h3 {
    font-size: 0.9rem; font-weight: 500; color: var(--ink);
    margin-bottom: 0.7rem; letter-spacing: 0.03em;
  }
  .value-card p { font-size: 0.83rem; color: var(--ink-light); line-height: 1.7; }

  /* SKILLS */
  .skills-section { }
  .skills-grid {
    display: grid; grid-template-columns: repeat(2,1fr);
    gap: 1.5rem; margin-top: 3rem;
  }
  .skill-block {
    background: white; border-radius: 14px; padding: 1.8rem;
    border: 1px solid var(--border); transition: all 0.3s;
  }
  .skill-block:hover { box-shadow: 0 8px 30px rgba(158,95,105,0.08); }
  .skill-block-head {
    display: flex; align-items: center; gap: 0.8rem; margin-bottom: 1rem;
  }
  .skill-icon {
    width: 42px; height: 42px; border-radius: 10px;
    background: var(--blush); display: flex; align-items: center;
    justify-content: center; font-size: 1.2rem; flex-shrink: 0;
  }
  .skill-block h3 { font-size: 0.95rem; font-weight: 500; color: var(--ink); }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .skill-tag {
    padding: 0.3rem 0.8rem;
    background: var(--blush); border-radius: 20px;
    font-size: 0.72rem; color: var(--rose-deep); letter-spacing: 0.04em;
  }
  .upskilling-tag {
    background: linear-gradient(135deg, #f5e6e8, #fdf0d0);
    border: 1px dashed var(--gold); color: var(--ink-light);
  }

  /* CASE STUDY */
  .case-study {
    background: linear-gradient(160deg, var(--cream) 0%, var(--blush) 100%);
  }
  .case-card {
    background: white; border-radius: 20px; padding: 2.5rem;
    border: 1px solid var(--border); margin-top: 2.5rem;
    max-width: 860px;
  }
  .case-meta {
    display: flex; gap: 1rem; margin-bottom: 1.5rem; flex-wrap: wrap;
  }
  .case-pill {
    padding: 0.35rem 1rem; border-radius: 20px;
    font-size: 0.72rem; letter-spacing: 0.06em; text-transform: uppercase;
  }
  .pill-type { background: var(--blush); color: var(--rose-deep); }
  .pill-impact { background: #e8f5e9; color: #388e3c; }
  .case-card h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.6rem; font-weight: 400; margin-bottom: 1rem;
  }
  .case-steps {
    display: grid; grid-template-columns: repeat(3,1fr); gap: 1.2rem;
    margin: 1.5rem 0;
  }
  .case-step {
    padding: 1.2rem; background: var(--cream); border-radius: 12px;
    border-left: 3px solid var(--mauve);
  }
  .case-step .step-label {
    font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase;
    color: var(--mauve); margin-bottom: 0.4rem;
  }
  .case-step p { font-size: 0.83rem; line-height: 1.6; color: var(--ink-light); }
  .case-result {
    background: linear-gradient(135deg, var(--rose-deep), var(--rose));
    color: white; border-radius: 12px; padding: 1.2rem 1.5rem;
    font-size: 0.88rem; line-height: 1.7;
  }
  .case-result strong { font-weight: 500; }

  /* SAMPLE ARTIFACTS */
  .artifacts-section { background: white; }
  .artifacts-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 2.5rem;
  }
  .artifact-card {
    border: 1px solid var(--border); border-radius: 14px; overflow: hidden;
    transition: all 0.3s;
  }
  .artifact-card:hover { box-shadow: 0 10px 32px rgba(158,95,105,0.1); transform: translateY(-3px); }
  .artifact-header {
    padding: 1.2rem 1.5rem;
    background: var(--blush);
    display: flex; align-items: center; gap: 0.7rem;
    border-bottom: 1px solid var(--border);
  }
  .artifact-header span { font-size: 1rem; }
  .artifact-header h4 { font-size: 0.85rem; font-weight: 500; color: var(--ink); }
  .artifact-body { padding: 1.5rem; background: white; }

  /* Bug report table */
  .mini-table { width: 100%; border-collapse: collapse; font-size: 0.78rem; }
  .mini-table th {
    text-align: left; padding: 0.5rem 0.7rem;
    background: var(--blush); color: var(--rose-deep);
    font-weight: 500; font-size: 0.7rem; letter-spacing: 0.05em;
  }
  .mini-table td { padding: 0.5rem 0.7rem; color: var(--ink-light); border-bottom: 1px solid var(--border); }
  .mini-table tr:last-child td { border-bottom: none; }
  .status-pass { color: #388e3c; font-weight: 500; }
  .status-fail { color: #c62828; font-weight: 500; }
  .severity-high { background: #fdecea; color: #c62828; padding: 0.15rem 0.5rem; border-radius: 10px; font-size: 0.68rem; }

  /* CONTACT */
  .contact-section {
    background: linear-gradient(135deg, #2d2323 0%, #3d2e2e 100%);
    color: white; text-align: center;
  }
  .contact-section .section-label { color: var(--mauve); justify-content: center; }
  .contact-section .section-label::after { display: none; }
  .contact-section .section-heading { color: white; }
  .contact-links {
    display: flex; justify-content: center; gap: 1.5rem;
    margin-top: 2.5rem; flex-wrap: wrap;
  }
  .contact-link {
    display: flex; align-items: center; gap: 0.6rem;
    padding: 0.9rem 1.8rem; border-radius: 40px;
    font-size: 0.82rem; text-decoration: none;
    transition: all 0.3s;
  }
  .cl-email { background: var(--rose-deep); color: white; }
  .cl-li { background: rgba(255,255,255,0.08); color: white; border: 1px solid rgba(255,255,255,0.15); }
  .contact-link:hover { transform: translateY(-3px); opacity: 0.85; }
  .contact-note {
    margin-top: 2rem; font-size: 0.83rem;
    color: rgba(255,255,255,0.45); font-style: italic;
    font-family: 'Cormorant Garamond', serif;
  }

  /* FOOTER */
  footer {
    padding: 1.5rem 5rem; background: #1e1717;
    display: flex; justify-content: space-between; align-items: center;
  }
  footer p { font-size: 0.72rem; color: rgba(255,255,255,0.3); }
  footer .footer-rose { color: var(--rose); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .fade-up {
    animation: fadeUp 0.7s ease forwards;
    opacity: 0;
  }
  .delay-1 { animation-delay: 0.15s; }
  .delay-2 { animation-delay: 0.3s; }
  .delay-3 { animation-delay: 0.45s; }
  .delay-4 { animation-delay: 0.6s; }

  /* MOBILE */
  @media (max-width: 900px) {
    .hero { grid-template-columns: 1fr; padding: 7rem 2rem 4rem; }
    .hero-visual { margin-top: 2.5rem; }
    .photo-ring { width: 240px; height: 240px; }
    section { padding: 4rem 2rem; }
    .ai-era-grid, .value-grid, .skills-grid, .artifacts-grid, .case-steps { grid-template-columns: 1fr; }
    .vibe-strip { padding: 2.5rem 2rem; flex-direction: column; }
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    footer { padding: 1.5rem 2rem; flex-direction: column; gap: 0.5rem; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Devie Rose Marmolejo</div>
  <ul class="nav-links">
    <li><a href="#why-qa">Why QA</a></li>
    <li><a href="#value">Value</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#work">Work</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-text">
    <div class="hero-eyebrow fade-up">Software Quality Engineer</div>
    <h1 class="hero-name fade-up delay-1">
      Devie<br><em>Rose</em>
    </h1>
    <p class="hero-title fade-up delay-2">QA Specialist · AI Chatbot Testing · Business Automation</p>
    <p class="hero-tagline fade-up delay-3">
      I find the bugs before your customers do. With 2+ years of hands-on QA experience across <strong>AI chatbots, CRM automation,</strong> and <strong>web applications</strong> — I protect your product, your reputation, and your revenue.
    </p>
    <div class="hero-ctas fade-up delay-4">
      <a href="#contact" class="btn-primary">Let's Work Together</a>
      <a href="#work" class="btn-secondary">See My Work</a>
    </div>
    <div class="hero-badges fade-up delay-4">
      <span class="badge">JIRA</span>
      <span class="badge">Postman · REST API</span>
      <span class="badge">Agile / Scrum</span>
      <span class="badge">Miro</span>
      <span class="badge">Selenium · Java</span>
      <span class="badge">Appium ↗ Upskilling</span>
    </div>
  </div>
  <div class="hero-visual fade-up delay-2">
    <div class="photo-ring">
      <div class="photo-frame">
        <img src="186482576_745089542825050_7225207321409936644_n-removebg-preview.png" alt="Devie Rose Marmolejo" />
      </div>
    </div>
  </div>
</section>

<!-- WHY QA IN THE AI ERA -->
<section class="ai-era" id="why-qa">
  <div class="section-label">The Stakes Are Higher Now</div>
  <h2 class="section-heading">Why QA Matters<br>More in the AI Era</h2>
  <div class="ai-era-grid">
    <div class="ai-card">
      <div class="ai-card-icon">🤖</div>
      <h3>AI Makes Confident Mistakes</h3>
      <p>AI systems hallucinate, misclassify, and produce wrong outputs — fluently. A human QA engineer catches what automated checks miss: intent mismatches, edge cases, and logic failures that look right but aren't.</p>
      <div class="stat">Critical layer</div>
    </div>
    <div class="ai-card">
      <div class="ai-card-icon">🎨</div>
      <h3>Vibe Coding Ships Bugs Fast</h3>
      <p>"Vibe coding" — using AI to generate code rapidly — accelerates development but multiplies untested paths. Every AI-written feature needs structured validation. Speed without QA is just fast failure.</p>
      <div class="stat">Every sprint</div>
    </div>
    <div class="ai-card">
      <div class="ai-card-icon">💬</div>
      <h3>Chatbot Failures Damage Trust</h3>
      <p>A chatbot that gives the wrong answer to a customer doesn't just create a support ticket — it erodes brand trust. I've tested thousands of dialog flows, intents, and metadata mappings to prevent exactly this.</p>
      <div class="stat">Tested 1000s of scripts</div>
    </div>
    <div class="ai-card">
      <div class="ai-card-icon">🔗</div>
      <h3>Automation Breaks in Silence</h3>
      <p>CRM workflows and automated business processes fail quietly. A data mismatch in one node can corrupt downstream reporting for weeks. QA for automation isn't optional — it's the safety net the business depends on.</p>
      <div class="stat">Zero silent failures</div>
    </div>
  </div>
</section>

<!-- VIBE CODING CALLOUT -->
<div class="vibe-strip">
  <div class="vibe-icon">⚡</div>
  <div class="vibe-text">
    <h3>Your team is shipping faster with AI. <em>Who's catching what breaks?</em></h3>
    <p>When developers use AI tools to write code at speed, the testing gap widens. QA isn't just about finding bugs — it's about structuring quality into every release cycle, so your team can move fast <em>without</em> breaking things your users notice.</p>
  </div>
</div>

<!-- VALUE / SAVE MONEY -->
<section class="value-section" id="value">
  <div class="section-label">Return on Investment</div>
  <h2 class="section-heading">How Hiring Me<br>Saves Your Business</h2>
  <div class="value-grid">
    <div class="value-card">
      <div class="value-number">6×</div>
      <h3>Cost of Fixing Bugs in Production</h3>
      <p>Bugs found in production cost 6× more to fix than bugs caught in QA. I find issues before they reach your users — protecting revenue and reducing firefighting costs.</p>
    </div>
    <div class="value-card">
      <div class="value-number">30%</div>
      <h3>Chatbot Error Rate Reduced</h3>
      <p>In my last chatbot QA engagement, structured intent and metadata testing reduced misclassification by 30%, directly improving customer satisfaction and reducing support load.</p>
    </div>
    <div class="value-card">
      <div class="value-number">↓</div>
      <h3>Fewer Support Tickets, More Trust</h3>
      <p>Quality products generate fewer escalations. By validating business automation workflows and GUI systems end-to-end, I reduce the bugs that become support tickets and customer churn.</p>
    </div>
    <div class="value-card">
      <div class="value-number">✓</div>
      <h3>Business-Aligned Testing</h3>
      <p>My CRM automation background means I don't just test software — I understand what it's supposed to accomplish for the business. Test cases are grounded in real requirements, not just technical specs.</p>
    </div>
    <div class="value-card">
      <div class="value-number">⚡</div>
      <h3>Fast Ramp-Up, No Hand-Holding</h3>
      <p>With Agile/Scrum experience, JIRA proficiency, and 1000s of executed test scripts, I integrate into your team quickly and contribute from sprint one.</p>
    </div>
    <div class="value-card">
      <div class="value-number">📱</div>
      <h3>Expanding into Mobile Automation</h3>
      <p>Currently upskilling in Appium with Java — bringing modern mobile app testing capability to your team without the senior-level price tag. Early mover advantage for growing apps.</p>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="skills-section" id="skills">
  <div class="section-label">What I Bring</div>
  <h2 class="section-heading">Core Capabilities</h2>
  <div class="skills-grid">
    <div class="skill-block">
      <div class="skill-block-head">
        <div class="skill-icon">🤖</div>
        <h3>AI Chatbot QA</h3>
      </div>
      <div class="skill-tags">
        <span class="skill-tag">Intent Testing</span>
        <span class="skill-tag">Dialog Flow Design</span>
        <span class="skill-tag">Metadata Validation</span>
        <span class="skill-tag">Conversation Flow Mapping</span>
        <span class="skill-tag">Misclassification Detection</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-head">
        <div class="skill-icon">⚙️</div>
        <h3>Business Automation QA</h3>
      </div>
      <div class="skill-tags">
        <span class="skill-tag">CRM Workflow Validation</span>
        <span class="skill-tag">Access Control Testing</span>
        <span class="skill-tag">Power BI Data Validation</span>
        <span class="skill-tag">Cross-Source Data Integrity</span>
        <span class="skill-tag">Requirement Analysis</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-head">
        <div class="skill-icon">🛠️</div>
        <h3>Testing Tools & Methods</h3>
      </div>
      <div class="skill-tags">
        <span class="skill-tag">JIRA</span>
        <span class="skill-tag">Postman · REST API</span>
        <span class="skill-tag">Selenium · Java</span>
        <span class="skill-tag">Agile / Scrum</span>
        <span class="skill-tag">Miro</span>
        <span class="skill-tag">Functional Testing</span>
        <span class="skill-tag">GUI Testing</span>
        <span class="skill-tag">Regression Testing</span>
        <span class="skill-tag">k6 Performance Testing</span>
        <span class="skill-tag upskilling-tag">✦ Appium (Mobile) ↗</span>
      </div>
    </div>
    <div class="skill-block">
      <div class="skill-block-head">
        <div class="skill-icon">🧠</div>
        <h3>Business Intelligence</h3>
      </div>
      <div class="skill-tags">
        <span class="skill-tag">Requirement Translation</span>
        <span class="skill-tag">Test Case Design</span>
        <span class="skill-tag">Process Mapping</span>
        <span class="skill-tag">Stakeholder Communication</span>
        <span class="skill-tag">Dev Collaboration</span>
        <span class="skill-tag">CRM Process Conversion</span>
      </div>
    </div>
  </div>
</section>

<!-- CASE STUDY -->
<section class="case-study" id="work">
  <div class="section-label">Case Study</div>
  <h2 class="section-heading">Real Work, Real Impact</h2>
  <div class="case-card">
    <div class="case-meta">
      <span class="case-pill pill-type">AI Chatbot QA</span>
      <span class="case-pill pill-impact">↓ 30% Error Rate</span>
    </div>
    <h3>Customer Service Chatbot — End-to-End QA</h3>
    <p style="font-size:0.88rem;color:var(--ink-light);line-height:1.7;margin-bottom:0.5rem;">
      Tasked with ensuring a customer-facing AI chatbot handled high-volume service queries accurately across intents, metadata, and role-based access paths.
    </p>
    <div class="case-steps">
      <div class="case-step">
        <div class="step-label">Approach</div>
        <p>Designed dialog flow maps for all customer intents. Built structured test cases per intent-metadata pairing. Validated against real business rules.</p>
      </div>
      <div class="case-step">
        <div class="step-label">Execution</div>
        <p>Executed thousands of test scripts across environments. Logged all deviations in JIRA. Collaborated with devs on root-cause analysis for misclassifications.</p>
      </div>
      <div class="case-step">
        <div class="step-label">Outcome</div>
        <p>Chatbot misclassification rate reduced by 30%. Customer satisfaction scores improved. Fewer escalations to human agents post-launch.</p>
      </div>
    </div>
    <div class="case-result">
      <strong>Business Impact:</strong> A 30% drop in chatbot errors directly translated to fewer misdirected customers, reduced support cost, and measurably improved brand experience — all before a single user reported a problem.
    </div>
  </div>

  <!-- SAMPLE ARTIFACTS -->
  <div style="margin-top:3rem;">
    <div class="section-label" id="artifacts">Sample Artifacts</div>
    <div class="artifacts-grid" style="margin-top:1.5rem;">
      <div class="artifact-card">
        <div class="artifact-header">
          <span>🐛</span>
          <h4>Bug Report Sample</h4>
        </div>
        <div class="artifact-body">
          <table class="mini-table">
            <tr><th>Field</th><th>Detail</th></tr>
            <tr><td>Title</td><td>Incorrect chatbot response for payment intent</td></tr>
            <tr><td>Severity</td><td><span class="severity-high">High</span></td></tr>
            <tr><td>Step 1</td><td>Open chatbot interface</td></tr>
            <tr><td>Step 2</td><td>Enter: "How do I pay my bill?"</td></tr>
            <tr><td>Expected</td><td>Provides payment instructions</td></tr>
            <tr><td>Actual</td><td>Redirects to unrelated FAQ</td></tr>
            <tr><td>Status</td><td>Open → Dev assigned</td></tr>
          </table>
        </div>
      </div>
      <div class="artifact-card">
        <div class="artifact-header">
          <span>✅</span>
          <h4>Test Case Log</h4>
        </div>
        <div class="artifact-body">
          <table class="mini-table">
            <tr><th>ID</th><th>Feature</th><th>Status</th></tr>
            <tr><td>TC001</td><td>Chatbot Intent: Reset password</td><td class="status-pass">Pass</td></tr>
            <tr><td>TC002</td><td>Power BI vs CRM Q1 data</td><td class="status-fail">Fail</td></tr>
            <tr><td>TC003</td><td>GUI Announcement creation</td><td class="status-pass">Pass</td></tr>
            <tr><td>TC004</td><td>Access control: User role</td><td class="status-pass">Pass</td></tr>
            <tr><td>TC005</td><td>Payment metadata mapping</td><td class="status-fail">Fail</td></tr>
          </table>
        </div>
      </div>
      <div class="artifact-card">
        <div class="artifact-header">
          <span>🗺️</span>
          <h4>Dialog Flow Matrix</h4>
        </div>
        <div class="artifact-body">
          <table class="mini-table">
            <tr><th>Intent</th><th>Metadata</th><th>Expected Response</th></tr>
            <tr><td>Payment</td><td>Account ID, Amount</td><td>"Payment of $X confirmed"</td></tr>
            <tr><td>Access Control</td><td>User Role</td><td>"Access granted to dashboard"</td></tr>
            <tr><td>Announcement</td><td>Title, Date</td><td>"Published successfully"</td></tr>
            <tr><td>Reset Password</td><td>Email, Token</td><td>Reset link sent to email</td></tr>
          </table>
        </div>
      </div>
      <div class="artifact-card">
        <div class="artifact-header">
          <span>📋</span>
          <h4>What I Deliver on Every Engagement</h4>
        </div>
        <div class="artifact-body" style="display:flex;flex-direction:column;gap:0.7rem;">
          <div style="display:flex;gap:0.6rem;align-items:flex-start;">
            <span style="color:var(--rose);flex-shrink:0;">✦</span>
            <span style="font-size:0.82rem;color:var(--ink-light);line-height:1.6;">Structured test cases mapped to business requirements</span>
          </div>
          <div style="display:flex;gap:0.6rem;align-items:flex-start;">
            <span style="color:var(--rose);flex-shrink:0;">✦</span>
            <span style="font-size:0.82rem;color:var(--ink-light);line-height:1.6;">Clear, reproducible bug reports with severity ratings</span>
          </div>
          <div style="display:flex;gap:0.6rem;align-items:flex-start;">
            <span style="color:var(--rose);flex-shrink:0;">✦</span>
            <span style="font-size:0.82rem;color:var(--ink-light);line-height:1.6;">JIRA-tracked issues with dev-ready context</span>
          </div>
          <div style="display:flex;gap:0.6rem;align-items:flex-start;">
            <span style="color:var(--rose);flex-shrink:0;">✦</span>
            <span style="font-size:0.82rem;color:var(--ink-light);line-height:1.6;">Dialog flow maps and test matrices for AI systems</span>
          </div>
          <div style="display:flex;gap:0.6rem;align-items:flex-start;">
            <span style="color:var(--rose);flex-shrink:0;">✦</span>
            <span style="font-size:0.82rem;color:var(--ink-light);line-height:1.6;">End-to-end regression coverage before every release</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact-section" id="contact">
  <div class="section-label">Let's Connect</div>
  <h2 class="section-heading">Ready to protect<br>your product?</h2>
  <p style="color:rgba(255,255,255,0.55);font-size:0.9rem;margin-top:0.8rem;max-width:500px;margin-left:auto;margin-right:auto;line-height:1.7;">
    Whether you need a QA specialist for your AI product, CRM system, or web application — I'd love to hear about your project.
  </p>
  <div class="contact-links">
    <a href="mailto:deviekumar@gmail.com" class="contact-link cl-email">
      ✉ deviekumar@gmail.com
    </a>
    <a href="https://www.linkedin.com/in/devie-rose-marmolejo/" target="_blank" class="contact-link cl-li">
      in LinkedIn Profile
    </a>
  </div>
  <p class="contact-note">Open to freelance QA projects, contract roles, and full-time opportunities.</p>
</section>

<footer>
  <p>© 2025 <span class="footer-rose">Devie Rose Marmolejo</span> · Software QA Engineer</p>
  <p style="font-size:0.68rem;color:rgba(255,255,255,0.2);">Currently upskilling: Appium · Mobile Automation · Java</p>
</footer>

</body>
</html>
