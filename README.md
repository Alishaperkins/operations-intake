<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;800;900&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #1B2B4B;
    --navy-dark: #111d33;
    --gold: #C9A84C;
    --gold-light: #dfc06e;
    --cream: #F5F4F0;
    --grey: #6B6B6B;
    --lgrey: #E2E0DA;
    --white: #ffffff;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--navy-dark);
    color: var(--white);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Squarespace wrapper — forces dark background regardless of page theme */
  #ap-form-root {
    background: var(--navy-dark);
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
  }

  /* ── HERO ── */
  .hero {
    background: var(--navy);
    position: relative;
    padding: 52px 24px 44px;
    text-align: center;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      -45deg,
      transparent,
      transparent 28px,
      rgba(201,168,76,0.04) 28px,
      rgba(201,168,76,0.04) 29px
    );
  }
  .hero-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.18em;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 14px;
    position: relative;
  }
  .hero h1 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: clamp(42px, 9vw, 68px);
    font-weight: 900;
    line-height: 0.92;
    text-transform: uppercase;
    position: relative;
    margin-bottom: 20px;
  }
  .hero h1 span { color: var(--gold); display: block; }
  .hero-sub {
    font-size: 15px;
    font-weight: 400;
    color: rgba(255,255,255,0.65);
    line-height: 1.6;
    max-width: 460px;
    margin: 0 auto 24px;
    position: relative;
  }
  .hero-sub strong { color: var(--white); font-weight: 600; }
  .gold-bar {
    height: 4px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    width: 100%;
    margin-top: 0;
  }

  /* ── TRUST BAR ── */
  .trust-bar {
    background: var(--gold);
    padding: 10px 24px;
    display: flex;
    justify-content: center;
    gap: 28px;
    flex-wrap: wrap;
  }
  .trust-item {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 0.08em;
    color: var(--navy);
    text-transform: uppercase;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .trust-item::before { content: '✦'; font-size: 9px; }

  /* ── FORM WRAPPER ── */
  .form-wrapper {
    max-width: 680px;
    margin: 0 auto;
    padding: 40px 24px 60px;
  }

  /* ── SECTION CARD ── */
  .section-card {
    background: #1a2a44;
    border: 1px solid #2e3f5c;
    border-radius: 2px;
    margin-bottom: 20px;
    overflow: hidden;
    opacity: 0;
    transform: translateY(18px);
    transition: opacity 0.5s ease, transform 0.5s ease;
  }
  .section-card.visible { opacity: 1; transform: translateY(0); }

  .card-header {
    background: var(--navy);
    padding: 14px 22px;
    display: flex;
    align-items: center;
    gap: 14px;
    border-bottom: 1px solid rgba(201,168,76,0.2);
  }
  .card-num {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 28px;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
    min-width: 28px;
  }
  .card-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 16px;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--white);
  }
  .card-body { padding: 22px 22px 18px; }

  /* ── FIELDS ── */
  .field-row {
    display: grid;
    gap: 14px;
    margin-bottom: 16px;
  }
  .field-row.two { grid-template-columns: 1fr 1fr; }
  @media (max-width: 520px) { .field-row.two { grid-template-columns: 1fr; } }

  .field { display: flex; flex-direction: column; gap: 5px; }
  .field label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gold);
  }
  .field label .req { color: rgba(255,255,255,0.35); margin-left: 2px; }

  input[type=text], input[type=email], input[type=tel], select, textarea {
    background: #152238;
    border: 1px solid #2e3f5c;
    border-radius: 1px;
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    padding: 10px 13px;
    outline: none;
    transition: border-color 0.2s, background 0.2s;
    width: 100%;
    -webkit-appearance: none;
  }
  input::placeholder, textarea::placeholder { color: rgba(255,255,255,0.28); }
  input:focus, select:focus, textarea:focus {
    border-color: var(--gold);
    background: #1a2e4a;
  }
  select option { background: var(--navy); color: var(--white); }
  textarea { resize: vertical; min-height: 80px; }

  /* ── CHECKBOX GROUPS ── */
  .check-group {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
    margin-top: 2px;
  }
  @media (max-width: 480px) { .check-group { grid-template-columns: 1fr; } }

  .check-item {
    display: flex;
    align-items: center;
    gap: 10px;
    background: #152238;
    border: 1px solid #2e3f5c;
    border-radius: 1px;
    padding: 9px 12px;
    cursor: pointer;
    transition: border-color 0.15s, background 0.15s;
    user-select: none;
  }
  .check-item:hover { border-color: rgba(201,168,76,0.4); background: #1e3050; }
  .check-item input[type=checkbox] { display: none; }
  .check-item.checked {
    border-color: var(--gold);
    background: #223355;
  }
  .check-box {
    width: 16px;
    height: 16px;
    border: 1.5px solid rgba(255,255,255,0.25);
    border-radius: 1px;
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.15s;
  }
  .check-item.checked .check-box {
    background: var(--gold);
    border-color: var(--gold);
  }
  .check-item.checked .check-box::after {
    content: '✓';
    font-size: 10px;
    color: var(--navy);
    font-weight: 700;
  }
  .check-label { font-size: 13px; color: rgba(255,255,255,0.8); line-height: 1.3; }

  /* ── RADIO GROUPS ── */
  .radio-group { display: flex; flex-direction: column; gap: 7px; margin-top: 2px; }
  .radio-item {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 9px 12px;
    background: #152238;
    border: 1px solid #2e3f5c;
    border-radius: 1px;
    cursor: pointer;
    transition: all 0.15s;
    user-select: none;
  }
  .radio-item:hover { border-color: rgba(201,168,76,0.4); }
  .radio-item input { display: none; }
  .radio-item.selected { border-color: var(--gold); background: #223355; }
  .radio-dot {
    width: 16px; height: 16px;
    border: 1.5px solid rgba(255,255,255,0.25);
    border-radius: 50%;
    flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.15s;
  }
  .radio-item.selected .radio-dot { border-color: var(--gold); }
  .radio-item.selected .radio-dot::after {
    content: '';
    width: 8px; height: 8px;
    background: var(--gold);
    border-radius: 50%;
  }
  .radio-label { font-size: 13px; color: rgba(255,255,255,0.8); }

  /* ── SECTION LABEL ── */
  .field-group-label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 8px;
    display: block;
  }

  /* ── DIVIDER ── */
  .divider {
    border: none;
    border-top: 1px solid rgba(255,255,255,0.07);
    margin: 18px 0;
  }

  /* ── SUBMIT ── */
  .submit-wrap {
    text-align: center;
    padding-top: 10px;
  }
  .submit-btn {
    display: inline-block;
    background: var(--gold);
    color: var(--navy);
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 17px;
    font-weight: 800;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    padding: 16px 48px;
    border: none;
    border-radius: 1px;
    cursor: pointer;
    transition: background 0.2s, transform 0.15s;
    width: 100%;
    max-width: 380px;
  }
  .submit-btn:hover { background: var(--gold-light); transform: translateY(-1px); }
  .submit-btn:active { transform: translateY(0); }
  .submit-note {
    font-size: 11px;
    color: rgba(255,255,255,0.35);
    margin-top: 10px;
    letter-spacing: 0.04em;
  }

  /* ── SUCCESS ── */
  .success-screen {
    display: none;
    text-align: center;
    padding: 60px 24px;
  }
  .success-screen.show { display: block; }
  .success-icon {
    font-size: 48px;
    margin-bottom: 20px;
  }
  .success-screen h2 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 36px;
    font-weight: 800;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 12px;
  }
  .success-screen h2 span { color: var(--gold); }
  .success-screen p {
    color: rgba(255,255,255,0.6);
    font-size: 15px;
    line-height: 1.7;
    max-width: 400px;
    margin: 0 auto;
  }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid rgba(255,255,255,0.07);
    padding: 24px;
    text-align: center;
  }
  footer p {
    font-size: 11px;
    color: rgba(255,255,255,0.3);
    line-height: 1.8;
  }
  footer a { color: var(--gold); text-decoration: none; }
</style>

<div id="ap-form-root">

<!-- HERO -->
<div class="hero">
  <p class="hero-label">Done-For-You Deliverables · Trades Edition</p>
  <h1>WE'LL BUILD<br><span>IT FOR YOU.</span></h1>
  <p class="hero-sub">Tell us what your trades business needs and we'll scope it out within <strong>24 hours.</strong> No fluff. Real deliverables, fixed scope, yours to keep.</p>
</div>
<div class="gold-bar"></div>

<!-- TRUST BAR -->
<div class="trust-bar">
  <span class="trust-item">SOP Libraries</span>
  <span class="trust-item">Compliance Frameworks</span>
  <span class="trust-item">Staff & Contractor Packs</span>
  <span class="trust-item">WHS Policy Packs</span>
</div>

<!-- FORM -->
<div class="form-wrapper">
  <form id="intakeForm" action="https://formspree.io/f/xvzwwyvy" method="POST">

    <!-- 01 YOUR BUSINESS -->
    <div class="section-card" data-delay="0">
      <div class="card-header">
        <span class="card-num">01</span>
        <span class="card-title">Your Business</span>
      </div>
      <div class="card-body">
        <div class="field-row two">
          <div class="field">
            <label>Full Name <span class="req">*</span></label>
            <input type="text" name="full_name" placeholder="Jane Smith" required>
          </div>
          <div class="field">
            <label>Business Name <span class="req">*</span></label>
            <input type="text" name="business_name" placeholder="Smith Plumbing Pty Ltd" required>
          </div>
        </div>
        <div class="field-row two">
          <div class="field">
            <label>Email Address <span class="req">*</span></label>
            <input type="email" name="email" placeholder="jane@smithplumbing.com.au" required>
          </div>
          <div class="field">
            <label>Phone Number <span class="req">*</span></label>
            <input type="tel" name="phone" placeholder="0400 000 000" required>
          </div>
        </div>
        <div class="field-row">
          <div class="field">
            <label>Trade / Industry <span class="req">*</span></label>
            <select name="trade" required>
              <option value="" disabled selected>Select your trade</option>
              <option>Plumbing</option>
              <option>Electrical</option>
              <option>Carpentry / Building</option>
              <option>HVAC / Air Conditioning</option>
              <option>Painting & Decorating</option>
              <option>Landscaping</option>
              <option>Concreting / Earthworks</option>
              <option>Roofing</option>
              <option>Tiling</option>
              <option>General Construction</option>
              <option>Other Trade</option>
            </select>
          </div>
        </div>
        <div class="field-row two">
          <div class="field">
            <label>Business Age</label>
            <select name="business_age">
              <option value="" disabled selected>Select</option>
              <option>Less than 1 year</option>
              <option>1–3 years</option>
              <option>3–5 years</option>
              <option>5+ years</option>
            </select>
          </div>
          <div class="field">
            <label>Team Size</label>
            <select name="team_size">
              <option value="" disabled selected>Select</option>
              <option>Just me</option>
              <option>2–5 (including contractors)</option>
              <option>6–15</option>
              <option>15+</option>
            </select>
          </div>
        </div>
      </div>
    </div>

    <!-- 02 WHAT WE BUILD FOR YOU -->
    <div class="section-card" data-delay="100">
      <div class="card-header">
        <span class="card-num">02</span>
        <span class="card-title">What Do You Need Built?</span>
      </div>
      <div class="card-body">
        <span class="field-group-label">Select everything that applies <span class="req">*</span></span>
        <div class="check-group" id="deliverables">
          <label class="check-item"><input type="checkbox" name="deliverables" value="SOP Library"><span class="check-box"></span><span class="check-label">SOP Library</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Compliance Framework"><span class="check-box"></span><span class="check-label">Compliance Framework</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="WHS Policy Pack"><span class="check-box"></span><span class="check-label">WHS Policy Pack</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Staff & Contractor Pack"><span class="check-box"></span><span class="check-label">Staff & Contractor Pack</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Quote & Invoice Templates"><span class="check-box"></span><span class="check-label">Quote & Invoice Templates</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Client Onboarding Pack"><span class="check-box"></span><span class="check-label">Client Onboarding Pack</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Tech Stack Setup"><span class="check-box"></span><span class="check-label">Tech Stack Setup</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="CRM & Workflow Setup"><span class="check-box"></span><span class="check-label">CRM & Workflow Setup</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Subcontractor Agreements"><span class="check-box"></span><span class="check-label">Subcontractor Agreements</span></label>
          <label class="check-item"><input type="checkbox" name="deliverables" value="Not sure – I need advice"><span class="check-box"></span><span class="check-label">Not sure — advise me</span></label>
        </div>
      </div>
    </div>

    <!-- 03 YOUR BIGGEST PROBLEM -->
    <div class="section-card" data-delay="200">
      <div class="card-header">
        <span class="card-num">03</span>
        <span class="card-title">What's Going Wrong Right Now?</span>
      </div>
      <div class="card-body">
        <span class="field-group-label">What's the biggest operational headache in your business? <span class="req">*</span></span>
        <div class="check-group" id="problems">
          <label class="check-item"><input type="checkbox" name="problems" value="No systems or SOPs"><span class="check-box"></span><span class="check-label">No systems or SOPs — everything's in my head</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="Staff not following process"><span class="check-box"></span><span class="check-label">Staff or subbies not following process</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="WHS compliance gaps"><span class="check-box"></span><span class="check-label">WHS compliance gaps / risk exposure</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="Quoting and invoicing inconsistent"><span class="check-box"></span><span class="check-label">Quoting and invoicing is inconsistent</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="Onboarding new staff is painful"><span class="check-box"></span><span class="check-label">Onboarding new staff is painful and slow</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="Growing and need structure"><span class="check-box"></span><span class="check-label">Growing fast and need structure to keep up</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="Admin consuming too much time"><span class="check-box"></span><span class="check-label">Admin is consuming too much of my time</span></label>
          <label class="check-item"><input type="checkbox" name="problems" value="Client communication issues"><span class="check-box"></span><span class="check-label">Client communication issues</span></label>
        </div>
        <hr class="divider">
        <div class="field">
          <label>Anything else you'd like us to know?</label>
          <textarea name="context" placeholder="Tell us more about your situation — the messier the better. We've seen it all."></textarea>
        </div>
      </div>
    </div>

    <!-- 04 SYSTEMS & TOOLS -->
    <div class="section-card" data-delay="300">
      <div class="card-header">
        <span class="card-num">04</span>
        <span class="card-title">Your Current Setup</span>
      </div>
      <div class="card-body">
        <span class="field-group-label">What tools or software do you currently use?</span>
        <div class="check-group" id="tools">
          <label class="check-item"><input type="checkbox" name="tools" value="Xero"><span class="check-box"></span><span class="check-label">Xero</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="MYOB"><span class="check-box"></span><span class="check-label">MYOB</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="ServiceM8"><span class="check-box"></span><span class="check-label">ServiceM8</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="Fergus"><span class="check-box"></span><span class="check-label">Fergus</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="Tradify"><span class="check-box"></span><span class="check-label">Tradify</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="Google Workspace"><span class="check-box"></span><span class="check-label">Google Workspace</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="Microsoft 365"><span class="check-box"></span><span class="check-label">Microsoft 365</span></label>
          <label class="check-item"><input type="checkbox" name="tools" value="Nothing formal yet"><span class="check-box"></span><span class="check-label">Nothing formal yet</span></label>
        </div>
      </div>
    </div>

    <!-- 05 TIMELINE & BUDGET -->
    <div class="section-card" data-delay="400">
      <div class="card-header">
        <span class="card-num">05</span>
        <span class="card-title">Timeline & Investment</span>
      </div>
      <div class="card-body">
        <div class="field-row">
          <div class="field">
            <label>How urgently do you need this? <span class="req">*</span></label>
            <div class="radio-group" id="urgency">
              <label class="radio-item"><input type="radio" name="urgency" value="ASAP"><span class="radio-dot"></span><span class="radio-label">ASAP — I needed this yesterday</span></label>
              <label class="radio-item"><input type="radio" name="urgency" value="Next few weeks"><span class="radio-dot"></span><span class="radio-label">Next few weeks — I'm ready to move</span></label>
              <label class="radio-item"><input type="radio" name="urgency" value="Next 1-3 months"><span class="radio-dot"></span><span class="radio-label">Next 1–3 months — planning ahead</span></label>
              <label class="radio-item"><input type="radio" name="urgency" value="Just exploring"><span class="radio-dot"></span><span class="radio-label">Just exploring for now</span></label>
            </div>
          </div>
        </div>
        <hr class="divider">
        <div class="field-row">
          <div class="field">
            <label>Approximate budget in mind?</label>
            <div class="radio-group" id="budget">
              <label class="radio-item"><input type="radio" name="budget" value="Under $500"><span class="radio-dot"></span><span class="radio-label">Under $500</span></label>
              <label class="radio-item"><input type="radio" name="budget" value="$500-$1500"><span class="radio-dot"></span><span class="radio-label">$500 – $1,500</span></label>
              <label class="radio-item"><input type="radio" name="budget" value="$1500-$3000"><span class="radio-dot"></span><span class="radio-label">$1,500 – $3,000</span></label>
              <label class="radio-item"><input type="radio" name="budget" value="$3000+"><span class="radio-dot"></span><span class="radio-label">$3,000+ — I want the full package</span></label>
              <label class="radio-item"><input type="radio" name="budget" value="No idea – quote me"><span class="radio-dot"></span><span class="radio-label">No idea — just quote me what it needs</span></label>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- SUBMIT -->
    <div class="submit-wrap">
      <button type="submit" class="submit-btn">Get My Free Scope & Quote →</button>
      <p class="submit-note">We'll review your details and respond within 24 hours. No obligation.</p>
    </div>

  </form>

  <!-- SUCCESS -->
  <div class="success-screen" id="successScreen">
    <div class="success-icon">✦</div>
    <h2>You're all set,<br><span>we'll be in touch.</span></h2>
    <p>Thanks for submitting your details. We'll review everything and come back to you with a clear scope and quote within 24 hours.</p>
  </div>
</div>

<footer>
  <p>
    <strong style="color:rgba(255,255,255,0.5)">Alisha Perkins Business Solutions</strong><br>
    ABN 96 479 101 233 &nbsp;·&nbsp; <a href="mailto:info@alishaperkins.com.au">info@alishaperkins.com.au</a> &nbsp;·&nbsp; 0421 203 908 &nbsp;·&nbsp; <a href="https://alishaperkins.com.au">alishaperkins.com.au</a>
  </p>
</footer>

<script>
  // Animate cards on load
  const cards = document.querySelectorAll('.section-card');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), parseInt(e.target.dataset.delay || 0));
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.08 });
  cards.forEach(c => observer.observe(c));

  // Checkbox toggle
  document.querySelectorAll('.check-item').forEach(item => {
    item.addEventListener('click', () => {
      const cb = item.querySelector('input[type=checkbox]');
      cb.checked = !cb.checked;
      item.classList.toggle('checked', cb.checked);
    });
  });

  // Radio toggle
  document.querySelectorAll('.radio-item').forEach(item => {
    item.addEventListener('click', () => {
      const radio = item.querySelector('input[type=radio]');
      const group = radio.name;
      document.querySelectorAll(`input[name="${group}"]`).forEach(r => {
        r.closest('.radio-item').classList.remove('selected');
      });
      radio.checked = true;
      item.classList.add('selected');
    });
  });


<script>
  // Animate cards on load
  const cards = document.querySelectorAll('.section-card');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), parseInt(e.target.dataset.delay || 0));
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.08 });
  cards.forEach(c => observer.observe(c));

  // Checkbox toggle
  document.querySelectorAll('.check-item').forEach(item => {
    item.addEventListener('click', () => {
      const cb = item.querySelector('input[type=checkbox]');
      cb.checked = !cb.checked;
      item.classList.toggle('checked', cb.checked);
    });
  });

  // Radio toggle
  document.querySelectorAll('.radio-item').forEach(item => {
    item.addEventListener('click', () => {
      const radio = item.querySelector('input[type=radio]');
      const group = radio.name;
      document.querySelectorAll(`input[name="${group}"]`).forEach(r => {
        r.closest('.radio-item').classList.remove('selected');
      });
      radio.checked = true;
      item.classList.add('selected');
    });
  });

  // Submit → Formspree
  document.getElementById('intakeForm').addEventListener('submit', async (e) => {
    e.preventDefault();
    const form = e.target;
    const btn = form.querySelector('.submit-btn');
    btn.textContent = 'Sending...';
    btn.disabled = true;
    try {
      const res = await fetch(form.action, {
        method: 'POST',
        body: new FormData(form),
        headers: { 'Accept': 'application/json' }
      });
      if (res.ok) {
        form.style.display = 'none';
        document.getElementById('successScreen').classList.add('show');
        window.scrollTo({ top: 0, behavior: 'smooth' });
      } else {
        btn.textContent = 'Something went wrong — please try again';
        btn.disabled = false;
      }
    } catch {
      btn.textContent = 'Something went wrong — please try again';
      btn.disabled = false;
    }
  });
</script>
