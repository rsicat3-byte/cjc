# cjc
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Celestial Journey Consulting – Your Gateway to Global Education</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    /* ── TOKEN SYSTEM ── */
    :root {
      --navy:    #0B1F3A;
      --sky:     #1B6CA8;
      --gold:    #C8973A;
      --pearl:   #F4F7FB;
      --white:   #FFFFFF;
      --ink:     #1A1A2E;
      --mist:    #E8EFF7;
      --success: #2D7A55;
      --danger:  #B03A2E;
      --warn:    #C8973A;

      --display: 'Cormorant Garamond', Georgia, serif;
      --body:    'DM Sans', system-ui, sans-serif;
      --mono:    'DM Mono', monospace;

      --r-sm: 6px;
      --r-md: 12px;
      --r-lg: 20px;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: var(--body);
      color: var(--ink);
      background: var(--white);
      line-height: 1.6;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 900;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5vw;
      height: 68px;
      background: rgba(11,31,58,0.96);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(200,151,58,0.3);
    }
    .logo {
      display: flex; align-items: center; gap: 12px; text-decoration: none;
    }
    .logo-mark {
      width: 38px; height: 38px;
      background: linear-gradient(135deg, var(--sky), var(--gold));
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-family: var(--display);
      font-size: 16px; font-weight: 700; color: var(--white);
      letter-spacing: 1px;
      flex-shrink: 0;
    }
    .logo-text { color: var(--white); line-height: 1.2; }
    .logo-text strong { display: block; font-family: var(--display); font-size: 17px; font-weight: 600; letter-spacing: 0.5px; }
    .logo-text small { font-size: 10px; color: var(--gold); letter-spacing: 1.5px; text-transform: uppercase; font-weight: 300; }

    .nav-links { display: flex; gap: 32px; list-style: none; }
    .nav-links a { color: rgba(255,255,255,0.8); text-decoration: none; font-size: 14px; font-weight: 400; letter-spacing: 0.3px; transition: color .2s; }
    .nav-links a:hover { color: var(--gold); }
    .nav-cta {
      background: var(--gold); color: var(--navy);
      padding: 9px 22px; border-radius: var(--r-sm);
      font-size: 13px; font-weight: 600; text-decoration: none; letter-spacing: 0.3px;
      transition: background .2s, transform .15s;
    }
    .nav-cta:hover { background: #e0a940; transform: translateY(-1px); }

    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
    .hamburger span { display: block; width: 24px; height: 2px; background: var(--white); border-radius: 2px; transition: all .25s; }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      background: linear-gradient(160deg, var(--navy) 0%, #0F2E52 50%, #163B66 100%);
      display: flex; align-items: center;
      padding: 100px 5vw 80px;
      position: relative;
      overflow: hidden;
    }
    #hero::before {
      content: '';
      position: absolute; inset: 0;
      background:
        radial-gradient(ellipse 60% 80% at 70% 50%, rgba(27,108,168,0.25) 0%, transparent 70%),
        radial-gradient(ellipse 30% 40% at 85% 20%, rgba(200,151,58,0.12) 0%, transparent 60%);
    }

    /* Constellation dots */
    #hero::after {
      content: '';
      position: absolute; inset: 0;
      background-image:
        radial-gradient(circle 1.5px at 15% 25%, rgba(200,151,58,0.5) 0%, transparent 100%),
        radial-gradient(circle 1px at 35% 15%, rgba(255,255,255,0.4) 0%, transparent 100%),
        radial-gradient(circle 2px at 55% 35%, rgba(200,151,58,0.3) 0%, transparent 100%),
        radial-gradient(circle 1px at 75% 20%, rgba(255,255,255,0.3) 0%, transparent 100%),
        radial-gradient(circle 1.5px at 85% 45%, rgba(200,151,58,0.4) 0%, transparent 100%),
        radial-gradient(circle 1px at 25% 70%, rgba(255,255,255,0.25) 0%, transparent 100%),
        radial-gradient(circle 1px at 90% 75%, rgba(255,255,255,0.3) 0%, transparent 100%),
        radial-gradient(circle 1.5px at 60% 80%, rgba(200,151,58,0.2) 0%, transparent 100%);
      pointer-events: none;
    }

    .hero-inner { position: relative; z-index: 1; max-width: 720px; }
    .hero-eyebrow {
      display: inline-flex; align-items: center; gap: 10px;
      font-size: 12px; letter-spacing: 2.5px; text-transform: uppercase;
      color: var(--gold); font-weight: 500; margin-bottom: 28px;
    }
    .hero-eyebrow::before { content: ''; display: block; width: 28px; height: 1px; background: var(--gold); }

    h1.hero-title {
      font-family: var(--display);
      font-size: clamp(44px, 7vw, 84px);
      font-weight: 300;
      color: var(--white);
      line-height: 1.1;
      margin-bottom: 12px;
      letter-spacing: -0.5px;
    }
    h1.hero-title em {
      font-style: italic; color: var(--gold);
      font-weight: 300;
    }
    .hero-sub {
      font-size: clamp(15px, 2vw, 18px);
      color: rgba(255,255,255,0.72);
      max-width: 520px;
      line-height: 1.7;
      margin-bottom: 48px;
      font-weight: 300;
    }
    .hero-btns { display: flex; gap: 16px; flex-wrap: wrap; }
    .btn-primary {
      background: var(--gold); color: var(--navy);
      padding: 16px 36px; border-radius: var(--r-sm);
      font-weight: 600; font-size: 15px; text-decoration: none;
      letter-spacing: 0.2px;
      transition: all .2s;
      display: inline-block;
    }
    .btn-primary:hover { background: #e0a940; transform: translateY(-2px); box-shadow: 0 8px 24px rgba(200,151,58,0.35); }
    .btn-outline {
      border: 1.5px solid rgba(255,255,255,0.4); color: var(--white);
      padding: 15px 36px; border-radius: var(--r-sm);
      font-weight: 400; font-size: 15px; text-decoration: none;
      transition: all .2s; display: inline-block;
    }
    .btn-outline:hover { border-color: var(--gold); color: var(--gold); transform: translateY(-2px); }

    .hero-stats {
      position: absolute; bottom: 60px; right: 5vw;
      display: flex; gap: 48px;
      z-index: 1;
    }
    .stat { text-align: center; }
    .stat-num {
      font-family: var(--display);
      font-size: 42px; font-weight: 600; color: var(--gold);
      line-height: 1;
    }
    .stat-label { font-size: 11px; color: rgba(255,255,255,0.55); letter-spacing: 1px; text-transform: uppercase; margin-top: 4px; }

    /* ── SECTION BASE ── */
    section { padding: 96px 5vw; }
    .section-label {
      font-size: 11px; letter-spacing: 2.5px; text-transform: uppercase;
      color: var(--sky); font-weight: 500; margin-bottom: 16px;
      display: flex; align-items: center; gap: 10px;
    }
    .section-label::after { content: ''; flex: 1; max-width: 40px; height: 1px; background: var(--sky); }
    h2.section-title {
      font-family: var(--display);
      font-size: clamp(32px, 5vw, 54px);
      font-weight: 400; line-height: 1.15;
      color: var(--navy); margin-bottom: 20px;
    }
    h2.section-title em { font-style: italic; color: var(--sky); }
    .section-lead {
      font-size: 17px; color: #555; max-width: 600px; line-height: 1.75;
      font-weight: 300; margin-bottom: 56px;
    }

    /* ── WHY CJC ── */
    #why { background: var(--pearl); }
    .why-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 28px;
    }
    .why-card {
      background: var(--white);
      border-radius: var(--r-md);
      padding: 36px 32px;
      border-top: 3px solid transparent;
      transition: border-color .25s, box-shadow .25s, transform .25s;
      position: relative;
    }
    .why-card:hover {
      border-top-color: var(--gold);
      box-shadow: 0 12px 40px rgba(11,31,58,0.1);
      transform: translateY(-4px);
    }
    .why-icon {
      width: 48px; height: 48px;
      background: var(--mist);
      border-radius: var(--r-sm);
      display: flex; align-items: center; justify-content: center;
      font-size: 22px; margin-bottom: 20px;
    }
    .why-card h3 { font-family: var(--display); font-size: 22px; font-weight: 600; color: var(--navy); margin-bottom: 10px; }
    .why-card p { font-size: 14px; color: #666; line-height: 1.7; }

    /* ── SERVICES ── */
    #services { background: var(--white); }
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 24px;
    }
    .service-card {
      border: 1px solid var(--mist);
      border-radius: var(--r-md);
      padding: 32px 28px;
      transition: all .25s;
      cursor: default;
    }
    .service-card:hover { border-color: var(--sky); box-shadow: 0 8px 32px rgba(27,108,168,0.1); transform: translateY(-3px); }
    .service-num { font-family: var(--mono); font-size: 12px; color: var(--gold); letter-spacing: 1px; margin-bottom: 12px; }
    .service-card h3 { font-family: var(--display); font-size: 22px; font-weight: 600; color: var(--navy); margin-bottom: 10px; }
    .service-card p { font-size: 14px; color: #666; line-height: 1.7; }

    /* ── DESTINATIONS ── */
    #destinations { background: var(--navy); }
    #destinations .section-label { color: var(--gold); }
    #destinations .section-label::after { background: var(--gold); }
    #destinations h2.section-title { color: var(--white); }
    #destinations h2.section-title em { color: var(--gold); }
    #destinations .section-lead { color: rgba(255,255,255,0.65); }

    .dest-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 16px;
    }
    .dest-card {
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: var(--r-md);
      padding: 28px 24px;
      transition: all .25s;
      cursor: default;
    }
    .dest-card:hover {
      background: rgba(255,255,255,0.11);
      border-color: var(--gold);
      transform: translateY(-3px);
    }
    .dest-flag { font-size: 32px; margin-bottom: 14px; }
    .dest-card h3 { font-family: var(--display); font-size: 20px; font-weight: 600; color: var(--white); margin-bottom: 8px; }
    .dest-card p { font-size: 13px; color: rgba(255,255,255,0.55); line-height: 1.6; }

    /* ── 7 STEPS PROCESS ── */
    #process { background: var(--pearl); }
    .steps-list { max-width: 800px; }
    .step-item {
      display: flex; gap: 28px; align-items: flex-start;
      padding: 28px 0;
      border-bottom: 1px solid var(--mist);
    }
    .step-item:last-child { border-bottom: none; }
    .step-num {
      width: 48px; height: 48px; flex-shrink: 0;
      background: var(--navy);
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-family: var(--mono); font-size: 14px; font-weight: 500; color: var(--gold);
    }
    .step-body h3 { font-family: var(--display); font-size: 22px; font-weight: 600; color: var(--navy); margin-bottom: 6px; }
    .step-body p { font-size: 14px; color: #666; line-height: 1.7; }
    .step-body ul { margin-top: 8px; padding-left: 18px; }
    .step-body ul li { font-size: 13px; color: #666; line-height: 1.8; }

    /* ── VISA COMPARISON TABLE ── */
    #compare { background: var(--white); }
    .compare-table-wrap { overflow-x: auto; border-radius: var(--r-md); box-shadow: 0 4px 24px rgba(11,31,58,0.08); }
    table.compare {
      width: 100%; border-collapse: collapse; min-width: 560px;
    }
    table.compare thead th {
      background: var(--navy); color: var(--white);
      padding: 18px 24px; text-align: left;
      font-family: var(--display); font-size: 18px; font-weight: 400;
    }
    table.compare thead th:first-child { width: 36%; }
    table.compare thead th.au { color: var(--gold); }
    table.compare thead th.nz { color: #7EC8E3; }
    table.compare tbody tr:nth-child(even) { background: var(--pearl); }
    table.compare tbody td {
      padding: 14px 24px; font-size: 14px; color: #444;
      border-bottom: 1px solid var(--mist); vertical-align: top;
    }
    table.compare tbody td:first-child { font-weight: 500; color: var(--navy); }

    /* ── TESTIMONIALS ── */
    #testimonials { background: var(--pearl); }
    .testi-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 24px; }
    .testi-card {
      background: var(--white); border-radius: var(--r-md); padding: 32px;
      box-shadow: 0 4px 20px rgba(11,31,58,0.06);
      position: relative;
    }
    .testi-card::before {
      content: '\201C';
      font-family: var(--display); font-size: 80px; color: var(--gold);
      opacity: .2; position: absolute; top: 16px; left: 24px; line-height: 1;
    }
    .testi-card blockquote { font-size: 15px; color: #555; line-height: 1.7; margin-bottom: 16px; position: relative; z-index: 1; }
    .testi-author { font-weight: 600; font-size: 14px; color: var(--navy); }
    .testi-role { font-size: 12px; color: #888; }

    /* ── FOR PARENTS ── */
    #parents { background: linear-gradient(135deg, var(--sky) 0%, var(--navy) 100%); color: var(--white); }
    #parents .section-label { color: var(--gold); }
    #parents .section-label::after { background: var(--gold); }
    #parents h2.section-title { color: var(--white); }
    #parents .section-lead { color: rgba(255,255,255,0.7); }
    .parents-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; max-width: 800px; }
    .parents-item { display: flex; gap: 14px; align-items: flex-start; }
    .parents-icon { font-size: 22px; flex-shrink: 0; }
    .parents-item h4 { font-family: var(--display); font-size: 18px; color: var(--white); margin-bottom: 4px; }
    .parents-item p { font-size: 13px; color: rgba(255,255,255,0.65); line-height: 1.6; }

    /* ── CTA BANNER ── */
    #cta-banner {
      background: var(--gold);
      padding: 80px 5vw; text-align: center;
    }
    #cta-banner h2 { font-family: var(--display); font-size: clamp(28px, 4vw, 48px); font-weight: 400; color: var(--navy); margin-bottom: 12px; }
    #cta-banner p { font-size: 17px; color: rgba(11,31,58,0.75); margin-bottom: 36px; max-width: 500px; margin-left: auto; margin-right: auto; }
    .btn-dark { background: var(--navy); color: var(--white); padding: 16px 40px; border-radius: var(--r-sm); font-weight: 600; font-size: 15px; text-decoration: none; display: inline-block; transition: all .2s; }
    .btn-dark:hover { background: var(--ink); transform: translateY(-2px); }

    /* ── FOOTER ── */
    footer {
      background: var(--ink); color: rgba(255,255,255,0.55);
      padding: 64px 5vw 32px;
    }
    .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 48px; margin-bottom: 56px; }
    .footer-brand p { font-size: 14px; line-height: 1.7; margin-top: 16px; max-width: 260px; }
    .footer-col h4 { font-family: var(--display); font-size: 16px; font-weight: 600; color: var(--white); margin-bottom: 16px; }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 8px; }
    .footer-col ul li a { color: rgba(255,255,255,0.5); text-decoration: none; font-size: 13px; transition: color .2s; }
    .footer-col ul li a:hover { color: var(--gold); }
    .footer-bottom { border-top: 1px solid rgba(255,255,255,0.1); padding-top: 24px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px; }
    .footer-bottom span { font-size: 12px; }
    .portal-link { color: var(--gold); text-decoration: none; font-size: 13px; font-weight: 500; }
    .portal-link:hover { text-decoration: underline; }

    /* ── PORTAL PAGE ── */
    .page { display: none; }
    .page.active { display: block; }

    /* ── PORTAL AUTH ── */
    #portal-login {
      min-height: 100vh; background: var(--navy);
      display: flex; align-items: center; justify-content: center;
      padding: 80px 5vw;
    }
    .auth-box {
      background: var(--white); border-radius: var(--r-lg);
      padding: 52px 48px; max-width: 440px; width: 100%;
      box-shadow: 0 24px 80px rgba(0,0,0,0.35);
    }
    .auth-logo { text-align: center; margin-bottom: 32px; }
    .auth-logo .logo-mark { width: 56px; height: 56px; font-size: 22px; margin: 0 auto 12px; }
    .auth-logo h2 { font-family: var(--display); font-size: 28px; color: var(--navy); font-weight: 400; }
    .auth-logo p { font-size: 13px; color: #888; margin-top: 4px; }
    .form-group { margin-bottom: 20px; }
    .form-group label { display: block; font-size: 13px; font-weight: 500; color: var(--navy); margin-bottom: 6px; }
    .form-group input, .form-group select {
      width: 100%; padding: 12px 16px; border: 1.5px solid var(--mist); border-radius: var(--r-sm);
      font-family: var(--body); font-size: 14px; color: var(--ink);
      transition: border-color .2s; outline: none;
    }
    .form-group input:focus, .form-group select:focus { border-color: var(--sky); }
    .btn-submit {
      width: 100%; padding: 14px; background: var(--navy); color: var(--white);
      border: none; border-radius: var(--r-sm); font-family: var(--body);
      font-size: 15px; font-weight: 600; cursor: pointer; transition: background .2s;
      margin-top: 8px;
    }
    .btn-submit:hover { background: var(--sky); }
    .auth-switch { text-align: center; margin-top: 20px; font-size: 13px; color: #888; }
    .auth-switch a { color: var(--sky); text-decoration: none; }
    .auth-switch a:hover { text-decoration: underline; }
    .auth-tabs { display: flex; gap: 0; margin-bottom: 28px; border: 1.5px solid var(--mist); border-radius: var(--r-sm); overflow: hidden; }
    .auth-tab { flex: 1; padding: 10px; text-align: center; font-size: 13px; font-weight: 500; cursor: pointer; background: var(--pearl); color: #888; transition: all .2s; }
    .auth-tab.active { background: var(--navy); color: var(--white); }
    .alert { padding: 12px 16px; border-radius: var(--r-sm); font-size: 13px; margin-bottom: 16px; display: none; }
    .alert.success { background: #e8f5ee; color: var(--success); border-left: 3px solid var(--success); display: block; }
    .alert.error { background: #fdecea; color: var(--danger); border-left: 3px solid var(--danger); display: block; }

    /* ── APPLICANT DASHBOARD ── */
    #dashboard {
      min-height: 100vh; background: var(--pearl);
    }
    .dash-header {
      background: var(--navy); padding: 20px 5vw;
      display: flex; align-items: center; justify-content: space-between;
    }
    .dash-header .user-info { display: flex; align-items: center; gap: 16px; }
    .user-avatar {
      width: 40px; height: 40px; border-radius: 50%;
      background: linear-gradient(135deg, var(--sky), var(--gold));
      display: flex; align-items: center; justify-content: center;
      font-family: var(--display); font-size: 16px; font-weight: 600; color: var(--white);
    }
    .user-name { color: var(--white); font-size: 15px; font-weight: 500; }
    .user-role { color: rgba(255,255,255,0.55); font-size: 12px; }
    .btn-logout { background: rgba(255,255,255,0.12); color: var(--white); border: none; padding: 8px 18px; border-radius: var(--r-sm); font-family: var(--body); font-size: 13px; cursor: pointer; transition: background .2s; }
    .btn-logout:hover { background: rgba(255,255,255,0.2); }

    .dash-body { display: grid; grid-template-columns: 280px 1fr; min-height: calc(100vh - 80px); }
    .dash-sidebar { background: var(--white); padding: 28px 20px; border-right: 1px solid var(--mist); }
    .dash-sidebar h3 { font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: #aaa; margin-bottom: 12px; padding-left: 8px; }
    .dash-nav { list-style: none; margin-bottom: 32px; }
    .dash-nav li { margin-bottom: 4px; }
    .dash-nav li a {
      display: flex; align-items: center; gap: 10px;
      padding: 10px 12px; border-radius: var(--r-sm);
      font-size: 14px; color: #666; text-decoration: none; transition: all .2s;
    }
    .dash-nav li a:hover, .dash-nav li a.active { background: var(--pearl); color: var(--navy); font-weight: 500; }
    .dash-nav li a .nav-icon { font-size: 16px; }
    .progress-widget { background: var(--pearl); border-radius: var(--r-md); padding: 20px; margin-top: 16px; }
    .progress-widget h4 { font-size: 13px; font-weight: 600; color: var(--navy); margin-bottom: 12px; }
    .prog-bar { height: 8px; background: var(--mist); border-radius: 4px; overflow: hidden; margin-bottom: 8px; }
    .prog-fill { height: 100%; background: linear-gradient(90deg, var(--sky), var(--gold)); border-radius: 4px; transition: width .5s ease; }
    .prog-text { font-size: 12px; color: #888; }
    .prog-pct { font-family: var(--mono); font-weight: 500; color: var(--sky); }

    .dash-main { padding: 36px; overflow-y: auto; }
    .dash-panel { display: none; }
    .dash-panel.active { display: block; }
    .dash-panel-title { font-family: var(--display); font-size: 32px; font-weight: 400; color: var(--navy); margin-bottom: 6px; }
    .dash-panel-sub { font-size: 14px; color: #888; margin-bottom: 32px; }

    /* Checklist */
    .checklist-section { margin-bottom: 40px; }
    .checklist-section-title {
      font-family: var(--display); font-size: 20px; font-weight: 600; color: var(--navy);
      margin-bottom: 16px; padding-bottom: 8px; border-bottom: 2px solid var(--mist);
      display: flex; align-items: center; gap: 10px;
    }
    .checklist-section-title .sec-icon { font-size: 18px; }
    .checklist-item {
      display: grid;
      grid-template-columns: 24px 1fr auto auto;
      align-items: center; gap: 12px;
      padding: 14px 16px;
      border: 1.5px solid var(--mist);
      border-radius: var(--r-sm);
      margin-bottom: 8px;
      background: var(--white);
      transition: all .2s;
    }
    .checklist-item.completed { background: #f0fdf6; border-color: #b7e8ce; }
    .checklist-item.completed .item-name { color: #2D7A55; text-decoration: line-through; text-decoration-color: #b7e8ce; }
    .check-box {
      width: 22px; height: 22px; border-radius: 50%;
      border: 2px solid #ccc; cursor: pointer;
      display: flex; align-items: center; justify-content: center;
      transition: all .2s; flex-shrink: 0; background: var(--white);
    }
    .check-box.checked { border-color: var(--success); background: var(--success); }
    .check-box.checked::after { content: '✓'; color: white; font-size: 12px; font-weight: 700; }
    .item-name { font-size: 14px; color: var(--ink); font-weight: 400; }
    .item-status {
      font-size: 11px; padding: 4px 10px; border-radius: 20px;
      font-weight: 500; white-space: nowrap;
    }
    .status-pending { background: #FFF3CD; color: #856404; }
    .status-uploaded { background: #d4edda; color: #155724; }
    .status-required { background: #f8d7da; color: #721c24; }
    .upload-btn {
      padding: 7px 14px; font-size: 12px; font-weight: 500;
      border-radius: var(--r-sm); border: 1.5px solid var(--sky);
      color: var(--sky); background: transparent; cursor: pointer;
      font-family: var(--body); transition: all .2s; white-space: nowrap;
    }
    .upload-btn:hover { background: var(--sky); color: var(--white); }
    .upload-btn.replace { border-color: var(--gold); color: var(--gold); }
    .upload-btn.replace:hover { background: var(--gold); color: var(--white); }

    /* Upload Modal */
    .modal-overlay {
      display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.6);
      z-index: 9999; align-items: center; justify-content: center;
    }
    .modal-overlay.open { display: flex; }
    .modal {
      background: var(--white); border-radius: var(--r-lg); padding: 40px;
      max-width: 480px; width: 90%; box-shadow: 0 24px 80px rgba(0,0,0,0.3);
      position: relative;
    }
    .modal-close { position: absolute; top: 16px; right: 20px; background: none; border: none; font-size: 22px; cursor: pointer; color: #aaa; }
    .modal-close:hover { color: var(--ink); }
    .modal h3 { font-family: var(--display); font-size: 26px; color: var(--navy); margin-bottom: 6px; }
    .modal p.modal-doc { font-size: 13px; color: #888; margin-bottom: 24px; }
    .drop-zone {
      border: 2px dashed var(--mist); border-radius: var(--r-md);
      padding: 40px 24px; text-align: center; cursor: pointer;
      transition: all .2s; margin-bottom: 20px;
    }
    .drop-zone:hover, .drop-zone.drag-over { border-color: var(--sky); background: #EBF4FD; }
    .drop-zone .dz-icon { font-size: 40px; margin-bottom: 12px; }
    .drop-zone p { font-size: 14px; color: #888; line-height: 1.6; }
    .drop-zone strong { color: var(--sky); }
    #file-input { display: none; }
    .file-preview { background: var(--pearl); border-radius: var(--r-sm); padding: 12px 16px; font-size: 13px; color: #555; margin-bottom: 16px; display: none; }
    .file-preview.show { display: flex; align-items: center; gap: 10px; }
    .file-preview .file-icon { font-size: 20px; }

    /* Notifications Panel */
    .notify-list { list-style: none; }
    .notify-item {
      display: flex; gap: 16px; padding: 16px;
      border-radius: var(--r-sm); margin-bottom: 8px;
      background: var(--white); border-left: 3px solid var(--mist);
    }
    .notify-item.info { border-left-color: var(--sky); }
    .notify-item.success { border-left-color: var(--success); }
    .notify-item.warn { border-left-color: var(--warn); }
    .notify-icon { font-size: 20px; flex-shrink: 0; margin-top: 2px; }
    .notify-text h4 { font-size: 14px; font-weight: 600; color: var(--navy); margin-bottom: 2px; }
    .notify-text p { font-size: 13px; color: #777; }
    .notify-time { font-size: 11px; color: #aaa; margin-left: auto; white-space: nowrap; }

    /* Admin Panel */
    .admin-applicant-card {
      background: var(--white); border-radius: var(--r-md); padding: 24px;
      border: 1.5px solid var(--mist); margin-bottom: 12px;
      display: grid; grid-template-columns: 1fr auto; align-items: center; gap: 16px;
    }
    .appl-name { font-family: var(--display); font-size: 20px; color: var(--navy); margin-bottom: 4px; }
    .appl-meta { font-size: 13px; color: #888; }
    .appl-progress { display: flex; align-items: center; gap: 12px; margin-top: 8px; }
    .mini-bar { flex: 1; height: 6px; background: var(--mist); border-radius: 3px; overflow: hidden; max-width: 140px; }
    .mini-fill { height: 100%; background: linear-gradient(90deg, var(--sky), var(--gold)); border-radius: 3px; }
    .appl-pct { font-size: 12px; font-family: var(--mono); color: var(--sky); }
    .btn-view { padding: 9px 20px; background: var(--navy); color: var(--white); border: none; border-radius: var(--r-sm); font-family: var(--body); font-size: 13px; font-weight: 500; cursor: pointer; }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .nav-links, .nav-cta { display: none; }
      .hamburger { display: flex; }
      .hero-stats { position: static; margin-top: 60px; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
      .parents-grid { grid-template-columns: 1fr; }
      .dash-body { grid-template-columns: 1fr; }
      .dash-sidebar { display: none; }
      .checklist-item { grid-template-columns: 24px 1fr; }
      .item-status, .upload-btn { display: none; }
    }
    @media (max-width: 600px) {
      nav { padding: 0 4vw; }
      section { padding: 64px 4vw; }
      .auth-box { padding: 36px 28px; }
      .footer-grid { grid-template-columns: 1fr; }
      .dash-main { padding: 20px; }
    }

    /* Mobile nav drawer */
    .mobile-nav { display: none; position: fixed; inset: 0; background: var(--navy); z-index: 800; padding: 90px 5vw 40px; flex-direction: column; gap: 8px; }
    .mobile-nav.open { display: flex; }
    .mobile-nav a { color: rgba(255,255,255,0.85); text-decoration: none; font-size: 20px; font-family: var(--display); padding: 12px 0; border-bottom: 1px solid rgba(255,255,255,0.1); }
    .mobile-nav .mob-cta { color: var(--gold); font-weight: 600; border-bottom: none; margin-top: 16px; }

    .fade-in { opacity: 0; transform: translateY(20px); transition: opacity .5s ease, transform .5s ease; }
    .fade-in.visible { opacity: 1; transform: none; }
  </style>
</head>
<body>

<!-- ════════════════════════════
     MAIN WEBSITE PAGE
════════════════════════════ -->
<div class="page active" id="page-home">

  <!-- NAV -->
  <nav>
    <a class="logo" href="#hero" onclick="scrollToTop()">
      <div class="logo-mark">CJC</div>
      <div class="logo-text">
        <strong>Celestial Journey Consulting</strong>
        <small>International Education</small>
      </div>
    </a>
    <ul class="nav-links">
      <li><a href="#why">Why CJC</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#destinations">Destinations</a></li>
      <li><a href="#process">Process</a></li>
      <li><a href="#compare">Visa Guide</a></li>
    </ul>
    <a class="nav-cta" href="#" onclick="showPage('page-portal'); return false;">Applicant Portal</a>
    <div class="hamburger" onclick="toggleMobileNav()" aria-label="Menu">
      <span></span><span></span><span></span>
    </div>
  </nav>

  <!-- MOBILE NAV -->
  <div class="mobile-nav" id="mobile-nav">
    <a href="#why" onclick="closeMobileNav()">Why CJC</a>
    <a href="#services" onclick="closeMobileNav()">Services</a>
    <a href="#destinations" onclick="closeMobileNav()">Destinations</a>
    <a href="#process" onclick="closeMobileNav()">Process</a>
    <a href="#compare" onclick="closeMobileNav()">Visa Guide</a>
    <a href="#" class="mob-cta" onclick="showPage('page-portal'); closeMobileNav(); return false;">→ Applicant Portal</a>
  </div>

  <!-- HERO -->
  <section id="hero">
    <div class="hero-inner">
      <div class="hero-eyebrow">Celestial Journey Consulting</div>
      <h1 class="hero-title">Your Journey<br>to <em>Global Education</em><br>Starts Here.</h1>
      <p class="hero-sub">From the Philippines to Australia, New Zealand, Canada, the UK, Europe, and beyond — CJC guides you through every step, from choosing your school to landing abroad.</p>
      <div class="hero-btns">
        <a href="#process" class="btn-primary">See How It Works</a>
        <a href="#" class="btn-outline" onclick="showPage('page-portal'); return false;">Applicant Portal →</a>
      </div>
    </div>
    <div class="hero-stats">
      <div class="stat">
        <div class="stat-num">100+</div>
        <div class="stat-label">Partner Institutions</div>
      </div>
      <div class="stat">
        <div class="stat-num">7</div>
        <div class="stat-label">Steps to Study Abroad</div>
      </div>
      <div class="stat">
        <div class="stat-num">6+</div>
        <div class="stat-label">Destinations</div>
      </div>
    </div>
  </section>

  <!-- WHY CJC -->
  <section id="why">
    <div class="section-label">Why Choose Us</div>
    <h2 class="section-title">More than an agency —<br>your <em>education partner</em></h2>
    <p class="section-lead">CJC is a registered organization in the Philippines specializing in international student placements, visa guidance, and lifelong support.</p>
    <div class="why-grid">
      <div class="why-card fade-in">
        <div class="why-icon">🎯</div>
        <h3>Personalized Counseling</h3>
        <p>We match you with the right course, country, and institution — based on your goals, budget, and academic background.</p>
      </div>
      <div class="why-card fade-in">
        <div class="why-icon">🌐</div>
        <h3>Global Institution Network</h3>
        <p>Partnerships with reputable universities and colleges across Australia, New Zealand, Canada, the UK, USA, and Europe.</p>
      </div>
      <div class="why-card fade-in">
        <div class="why-icon">📋</div>
        <h3>End-to-End Support</h3>
        <p>From your first inquiry to arrival abroad — admissions, COE, visa application, OSHC, and pre-departure orientation.</p>
      </div>
      <div class="why-card fade-in">
        <div class="why-icon">🔒</div>
        <h3>Secure Document Portal</h3>
        <p>Upload, track, and manage your visa documents anytime through our secure applicant portal — accessible only to you and our team.</p>
      </div>
      <div class="why-card fade-in">
        <div class="why-icon">🎓</div>
        <h3>Scholarship Guidance</h3>
        <p>We help identify grants, discounts, and financial aid options to make international education more affordable.</p>
      </div>
      <div class="why-card fade-in">
        <div class="why-icon">✈️</div>
        <h3>Pre-Departure Orientation</h3>
        <p>Comprehensive briefings on culture, housing, budgeting, and academics so you arrive confident and prepared.</p>
      </div>
    </div>
  </section>

  <!-- SERVICES -->
  <section id="services">
    <div class="section-label">What We Do</div>
    <h2 class="section-title">Our <em>Services</em></h2>
    <p class="section-lead">Expert guidance at every stage of your international education journey.</p>
    <div class="services-grid">
      <div class="service-card fade-in">
        <div class="service-num">01</div>
        <h3>Educational Counseling</h3>
        <p>One-on-one sessions to identify the right course, school, and country aligned with your interests, skills, and long-term career goals.</p>
      </div>
      <div class="service-card fade-in">
        <div class="service-num">02</div>
        <h3>School & University Applications</h3>
        <p>Complete document preparation, application submission, and liaison with institutions on your behalf for higher acceptance rates.</p>
      </div>
      <div class="service-card fade-in">
        <div class="service-num">03</div>
        <h3>Visa Assistance</h3>
        <p>Expert help with forms, requirements, GS statements, and online lodgment — for Australia, New Zealand, Canada, UK, USA, and EU.</p>
      </div>
      <div class="service-card fade-in">
        <div class="service-num">04</div>
        <h3>Scholarship & Financial Aid</h3>
        <p>Identifying grants, institutional discounts, and financial aid opportunities to reduce your total study costs.</p>
      </div>
      <div class="service-card fade-in">
        <div class="service-num">05</div>
        <h3>Pre-Departure Orientation</h3>
        <p>Briefings on accommodation, culture, banking, transport, and academic expectations so you arrive fully prepared.</p>
      </div>
      <div class="service-card fade-in">
        <div class="service-num">06</div>
        <h3>Partnership Development</h3>
        <p>We collaborate with international universities and schools to expand pathways for Filipino students and build transnational programs.</p>
      </div>
    </div>
  </section>

  <!-- DESTINATIONS -->
  <section id="destinations">
    <div class="section-label">Study Destinations</div>
    <h2 class="section-title">The world is waiting —<br><em>where will you go?</em></h2>
    <p class="section-lead">CJC connects Filipino students with top institutions across six major study destinations.</p>
    <div class="dest-grid">
      <div class="dest-card">
        <div class="dest-flag">🇦🇺</div>
        <h3>Australia</h3>
        <p>High-quality education, post-study work opportunities, and a welcoming multicultural environment.</p>
      </div>
      <div class="dest-card">
        <div class="dest-flag">🇳🇿</div>
        <h3>New Zealand</h3>
        <p>Globally recognized qualifications in a safe, scenic country with strong graduate pathways.</p>
      </div>
      <div class="dest-card">
        <div class="dest-flag">🇨🇦</div>
        <h3>Canada</h3>
        <p>Affordable tuition, work-study opportunities, and clear pathways to permanent residency.</p>
      </div>
      <div class="dest-card">
        <div class="dest-flag">🇬🇧</div>
        <h3>United Kingdom</h3>
        <p>Prestigious universities and globally respected degrees, often completed in shorter durations.</p>
      </div>
      <div class="dest-card">
        <div class="dest-flag">🇺🇸</div>
        <h3>United States</h3>
        <p>Wide variety of programs, advanced research facilities, and rich campus life experiences.</p>
      </div>
      <div class="dest-card">
        <div class="dest-flag">🇪🇺</div>
        <h3>Europe</h3>
        <p>Affordable or subsidized tuition in many countries, rich cultural immersion, and quality education.</p>
      </div>
    </div>
  </section>

  <!-- 7 STEPS -->
  <section id="process">
    <div class="section-label">The CJC Process</div>
    <h2 class="section-title">7 Steps to<br><em>Study Abroad</em></h2>
    <p class="section-lead">From your first document submission to landing in your new country — here's how CJC walks you through it.</p>
    <div class="steps-list">
      <div class="step-item fade-in">
        <div class="step-num">01</div>
        <div class="step-body">
          <h3>Assessment Stage</h3>
          <p>Submit your initial documents for evaluation by the CJC team — passport, English proficiency certificate (IELTS or PTE), academic records, and CV.</p>
        </div>
      </div>
      <div class="step-item fade-in">
        <div class="step-num">02</div>
        <div class="step-body">
          <h3>Application & Offer Letter</h3>
          <p>Once evaluated, we provide a curated list of institutions. Upon your selection, we forward your documents and secure your Offer Letter — typically within 1 to 3 days.</p>
        </div>
      </div>
      <div class="step-item fade-in">
        <div class="step-num">03</div>
        <div class="step-body">
          <h3>Confirmation of Enrolment (COE)</h3>
          <p>Sign the Offer Letter, write your Statement of Purpose, complete the Genuine Student (GS) form, submit financial documents, pay the first semester tuition and OSHC, then receive your COE.</p>
        </div>
      </div>
      <div class="step-item fade-in">
        <div class="step-num">04</div>
        <div class="step-body">
          <h3>Visa Application Lodgment</h3>
          <p>With your COE in hand, we help you create your ImmiAccount, complete the online application, upload all documents, and pay the visa application fee (AUD 2,000 for Australia).</p>
        </div>
      </div>
      <div class="step-item fade-in">
        <div class="step-num">05</div>
        <div class="step-body">
          <h3>Medical Check-Up & Biometrics</h3>
          <p>After lodgment, you'll receive a notice for biometric collection and medical examination. These must be completed promptly as visa processing is paused until results are received.</p>
        </div>
      </div>
      <div class="step-item fade-in">
        <div class="step-num">06</div>
        <div class="step-body">
          <h3>Visa Outcome</h3>
          <p>Wait for the visa decision — typically 60 to 120 days for Australia. Complete applications are processed more efficiently.</p>
        </div>
      </div>
      <div class="step-item fade-in">
        <div class="step-num">07</div>
        <div class="step-body">
          <h3>Travel & Arrival</h3>
          <p>Once granted, book your ticket and arrange accommodation through platforms like Flatmate Finders, Flatmates.com.au, or AmberStudent. Visit your institution for enrolment and begin classes.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- COMPARISON TABLE -->
  <section id="compare">
    <div class="section-label">Visa Comparison</div>
    <h2 class="section-title">Australia <em>vs</em> New Zealand<br>Student Visa</h2>
    <p class="section-lead">A quick reference for Filipino students comparing the two most popular Pacific study destinations.</p>
    <div class="compare-table-wrap">
      <table class="compare">
        <thead>
          <tr>
            <th>Item</th>
            <th class="au">🇦🇺 Australia</th>
            <th class="nz">🇳🇿 New Zealand</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>Main Visa</td><td>Student Visa Subclass 500</td><td>Fee Paying Student Visa</td></tr>
          <tr><td>Admission Document</td><td>Confirmation of Enrolment (CoE)</td><td>Offer of Place</td></tr>
          <tr><td>Health Insurance</td><td>OSHC — mandatory throughout stay</td><td>Medical insurance usually required</td></tr>
          <tr><td>Work During Study</td><td>Up to 48 hrs/fortnight while classes are in session</td><td>Subject to visa conditions</td></tr>
          <tr><td>Dependents Allowed</td><td>Yes (spouse and children)</td><td>Yes (subject to eligibility)</td></tr>
          <tr><td>Post-Study Work</td><td>Available</td><td>Available</td></tr>
          <tr><td>Application Lead Time</td><td>6–12 weeks recommended</td><td>At least 3 months before travel</td></tr>
          <tr><td>English Test Required</td><td>Yes (IELTS, PTE, TOEFL)</td><td>Yes</td></tr>
          <tr><td>Tuition (Annual)</td><td>AUD 18,000 – AUD 55,000+</td><td>NZD 18,000 – NZD 45,000</td></tr>
          <tr><td>Living Costs (Annual)</td><td>AUD 29,750 – AUD 42,000</td><td>NZD 20,000+</td></tr>
          <tr><td>Visa Application Fee</td><td>Approx. AUD 2,000</td><td>Varies</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section id="testimonials">
    <div class="section-label">Student Stories</div>
    <h2 class="section-title">What our <em>students</em> say</h2>
    <p class="section-lead">Real experiences from Filipino students who made the journey with CJC.</p>
    <div class="testi-grid">
      <div class="testi-card fade-in">
        <blockquote>CJC made the entire application process stress-free. Their team walked me through every requirement and I got my Australian visa without any issues. I'm now studying Nursing at a top Melbourne university.</blockquote>
        <div class="testi-author">Maria S.</div>
        <div class="testi-role">Nursing Student, Melbourne, Australia</div>
      </div>
      <div class="testi-card fade-in">
        <blockquote>Thanks to Celestial Journey Consulting, I got into my dream school in Canada. They helped me write my statement of purpose and prepared all my financial documents perfectly.</blockquote>
        <div class="testi-author">Anna D.</div>
        <div class="testi-role">IT Student, Toronto, Canada</div>
      </div>
      <div class="testi-card fade-in">
        <blockquote>As parents, we were worried at first. But CJC guided us with complete clarity and professionalism. Our son is now thriving in New Zealand — we couldn't be more grateful.</blockquote>
        <div class="testi-author">Mr. & Mrs. Reyes</div>
        <div class="testi-role">Parents of an Engineering Student, Auckland, NZ</div>
      </div>
    </div>
  </section>

  <!-- FOR PARENTS -->
  <section id="parents">
    <div class="section-label">For Parents</div>
    <h2 class="section-title">Peace of mind.<br><em>While your child studies abroad.</em></h2>
    <p class="section-lead">Sending your child overseas is a life-changing decision. CJC ensures parents are never left in the dark.</p>
    <div class="parents-grid">
      <div class="parents-item">
        <div class="parents-icon">✅</div>
        <div>
          <h4>Transparent Guidance</h4>
          <p>We explain every step, every fee, and every requirement in plain language.</p>
        </div>
      </div>
      <div class="parents-item">
        <div class="parents-icon">💰</div>
        <div>
          <h4>Financial Planning Support</h4>
          <p>Assistance with cost projections, financial documentation, and scholarship options.</p>
        </div>
      </div>
      <div class="parents-item">
        <div class="parents-icon">📞</div>
        <div>
          <h4>Regular Communication</h4>
          <p>Updates at every stage — from application submission to visa approval and departure.</p>
        </div>
      </div>
      <div class="parents-item">
        <div class="parents-icon">🛡️</div>
        <div>
          <h4>Student Safety Guidance</h4>
          <p>Briefings on OSHC coverage, accommodation safety, and student welfare resources abroad.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA BANNER -->
  <section id="cta-banner">
    <h2>Your global journey starts here.</h2>
    <p>Let's shape your future together. Book a free consultation with our team today.</p>
    <a href="mailto:inquiry@cjc-edu.com" class="btn-dark">Book a Free Consultation</a>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-grid">
      <div class="footer-brand">
        <div class="logo">
          <div class="logo-mark">CJC</div>
          <div class="logo-text">
            <strong style="color:white">Celestial Journey Consulting</strong>
            <small>International Education</small>
          </div>
        </div>
        <p>Empowering Filipino students with opportunities for international education that open doors to academic excellence and global career success.</p>
      </div>
      <div class="footer-col">
        <h4>Services</h4>
        <ul>
          <li><a href="#services">Educational Counseling</a></li>
          <li><a href="#services">School Applications</a></li>
          <li><a href="#services">Visa Assistance</a></li>
          <li><a href="#services">Scholarships</a></li>
          <li><a href="#services">Pre-Departure</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Destinations</h4>
        <ul>
          <li><a href="#destinations">Australia</a></li>
          <li><a href="#destinations">New Zealand</a></li>
          <li><a href="#destinations">Canada</a></li>
          <li><a href="#destinations">United Kingdom</a></li>
          <li><a href="#destinations">Europe & USA</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Contact</h4>
        <ul>
          <li><a href="mailto:inquiry@cjc-edu.com">inquiry@cjc-edu.com</a></li>
          <li><a href="tel:+639157552815">+63 915 755 2815</a></li>
          <li><a href="#">Mandaluyong City, Philippines</a></li>
          <li><a href="#" onclick="showPage('page-portal'); return false;">Applicant Portal</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 Celestial Journey Consulting. All rights reserved. SEC-Registered.</span>
      <a href="#" class="portal-link" onclick="showPage('page-portal'); return false;">→ Applicant Login Portal</a>
    </div>
  </footer>

</div><!-- end #page-home -->


<!-- ════════════════════════════
     PORTAL PAGE
════════════════════════════ -->
<div class="page" id="page-portal">

  <!-- LOGIN SCREEN -->
  <div id="portal-login">
    <div class="auth-box">
      <div class="auth-logo">
        <div class="logo-mark" style="width:56px;height:56px;font-size:22px;margin:0 auto 12px;display:flex;align-items:center;justify-content:center;">CJC</div>
        <h2>Applicant Portal</h2>
        <p>Secure document management for CJC applicants</p>
      </div>

      <div class="auth-tabs">
        <div class="auth-tab active" onclick="switchTab('login')">Sign In</div>
        <div class="auth-tab" onclick="switchTab('register')">New Applicant</div>
      </div>

      <!-- LOGIN FORM -->
      <div id="login-form">
        <div id="login-alert"></div>
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" id="login-email" placeholder="yourname@email.com" />
        </div>
        <div class="form-group">
          <label>Password</label>
          <input type="password" id="login-password" placeholder="••••••••" />
        </div>
        <div class="form-group">
          <label>Sign in as</label>
          <select id="login-role">
            <option value="applicant">Applicant</option>
            <option value="admin">Admin / CJC Staff</option>
          </select>
        </div>
        <button class="btn-submit" onclick="handleLogin()">Sign In to Portal</button>
        <div class="auth-switch">
          <a href="#" onclick="showPage('page-home'); return false;">← Return to CJC Website</a>
        </div>
      </div>

      <!-- REGISTER FORM -->
      <div id="register-form" style="display:none">
        <div id="register-alert"></div>
        <div class="form-group">
          <label>Full Name</label>
          <input type="text" id="reg-name" placeholder="Juan Dela Cruz" />
        </div>
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" id="reg-email" placeholder="yourname@email.com" />
        </div>
        <div class="form-group">
          <label>Study Destination</label>
          <select id="reg-dest">
            <option value="">Select country...</option>
            <option>Australia</option>
            <option>New Zealand</option>
            <option>Canada</option>
            <option>United Kingdom</option>
            <option>United States</option>
            <option>Europe</option>
          </select>
        </div>
        <div class="form-group">
          <label>Password</label>
          <input type="password" id="reg-password" placeholder="Min. 8 characters" />
        </div>
        <button class="btn-submit" onclick="handleRegister()">Create My Account</button>
        <div class="auth-switch">
          <a href="#" onclick="showPage('page-home'); return false;">← Return to CJC Website</a>
        </div>
      </div>
    </div>
  </div>

  <!-- APPLICANT DASHBOARD -->
  <div id="dashboard" style="display:none">
    <div class="dash-header">
      <div class="logo">
        <div class="logo-mark" style="width:34px;height:34px;font-size:14px;display:flex;align-items:center;justify-content:center;">CJC</div>
        <div class="logo-text">
          <strong style="font-size:15px;">Celestial Journey Consulting</strong>
          <small>Applicant Portal</small>
        </div>
      </div>
      <div class="user-info">
        <div class="user-avatar" id="avatar-initials">JD</div>
        <div>
          <div class="user-name" id="user-display-name">Juan Dela Cruz</div>
          <div class="user-role" id="user-display-role">Applicant — Australia</div>
        </div>
      </div>
      <button class="btn-logout" onclick="handleLogout()">Sign Out</button>
    </div>

    <div class="dash-body">
      <!-- Sidebar -->
      <div class="dash-sidebar">
        <h3>Navigation</h3>
        <ul class="dash-nav">
          <li><a href="#" class="active" onclick="switchPanel('overview')"><span class="nav-icon">🏠</span> Overview</a></li>
          <li><a href="#" onclick="switchPanel('checklist')"><span class="nav-icon">📋</span> Document Checklist</a></li>
          <li><a href="#" onclick="switchPanel('uploads')"><span class="nav-icon">📁</span> My Uploads</a></li>
          <li><a href="#" onclick="switchPanel('notifications')"><span class="nav-icon">🔔</span> Notifications</a></li>
          <li id="admin-nav-item" style="display:none"><a href="#" onclick="switchPanel('admin')"><span class="nav-icon">⚙️</span> Admin Panel</a></li>
        </ul>

        <div class="progress-widget">
          <h4>Application Progress</h4>
          <div class="prog-bar"><div class="prog-fill" id="prog-fill" style="width:0%"></div></div>
          <div class="prog-text"><span class="prog-pct" id="prog-pct">0%</span> of documents submitted</div>
        </div>
      </div>

      <!-- Main Content -->
      <div class="dash-main">

        <!-- OVERVIEW -->
        <div class="dash-panel active" id="panel-overview">
          <div class="dash-panel-title">Welcome back, <span id="overview-name">Juan</span> 👋</div>
          <div class="dash-panel-sub">Here's a summary of your CJC application status.</div>

          <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:16px;margin-bottom:36px;">
            <div style="background:var(--white);border-radius:var(--r-md);padding:24px;border:1.5px solid var(--mist);">
              <div style="font-size:32px;font-family:var(--display);color:var(--navy);font-weight:600;" id="ov-uploaded">0</div>
              <div style="font-size:13px;color:#888;margin-top:4px;">Documents Uploaded</div>
            </div>
            <div style="background:var(--white);border-radius:var(--r-md);padding:24px;border:1.5px solid var(--mist);">
              <div style="font-size:32px;font-family:var(--display);color:var(--gold);font-weight:600;" id="ov-pending">0</div>
              <div style="font-size:13px;color:#888;margin-top:4px;">Pending Documents</div>
            </div>
            <div style="background:var(--white);border-radius:var(--r-md);padding:24px;border:1.5px solid var(--mist);">
              <div style="font-size:32px;font-family:var(--display);color:var(--success);font-weight:600;" id="ov-progress">0%</div>
              <div style="font-size:13px;color:#888;margin-top:4px;">Completion Rate</div>
            </div>
          </div>

          <div style="background:var(--white);border-radius:var(--r-md);padding:28px;border:1.5px solid var(--mist);">
            <h3 style="font-family:var(--display);font-size:22px;color:var(--navy);margin-bottom:16px;">📌 Next Steps</h3>
            <div id="next-steps-list">
              <p style="color:#888;font-size:14px;">Your checklist is loading...</p>
            </div>
          </div>
        </div>

        <!-- CHECKLIST -->
        <div class="dash-panel" id="panel-checklist">
          <div class="dash-panel-title">Document Checklist</div>
          <div class="dash-panel-sub">Track, review, and upload your visa application documents. Click any item to mark it reviewed, then upload the file.</div>

          <div id="checklist-content"></div>
        </div>

        <!-- UPLOADS -->
        <div class="dash-panel" id="panel-uploads">
          <div class="dash-panel-title">My Uploaded Files</div>
          <div class="dash-panel-sub">All files you have submitted. You can replace any document at any time.</div>
          <div id="uploads-list"></div>
        </div>

        <!-- NOTIFICATIONS -->
        <div class="dash-panel" id="panel-notifications">
          <div class="dash-panel-title">Notifications</div>
          <div class="dash-panel-sub">Updates from CJC about your application.</div>
          <ul class="notify-list" id="notify-list"></ul>
        </div>

        <!-- ADMIN -->
        <div class="dash-panel" id="panel-admin">
          <div class="dash-panel-title">Admin Panel</div>
          <div class="dash-panel-sub">View and manage all applicant submissions.</div>
          <div id="admin-content"></div>
        </div>

      </div><!-- dash-main -->
    </div><!-- dash-body -->
  </div><!-- dashboard -->

</div><!-- page-portal -->


<!-- UPLOAD MODAL -->
<div class="modal-overlay" id="upload-modal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">✕</button>
    <h3>Upload Document</h3>
    <p class="modal-doc" id="modal-doc-name">Passport</p>

    <div class="drop-zone" id="drop-zone" onclick="document.getElementById('file-input').click()"
         ondragover="handleDragOver(event)" ondrop="handleDrop(event)" ondragleave="handleDragLeave(event)">
      <div class="dz-icon">📄</div>
      <p><strong>Click to browse</strong> or drag & drop your file here</p>
      <p style="margin-top:6px;font-size:12px;">PDF, JPG, PNG — Max 10MB</p>
    </div>
    <input type="file" id="file-input" accept=".pdf,.jpg,.jpeg,.png" onchange="handleFileSelect(event)" />

    <div class="file-preview" id="file-preview">
      <span class="file-icon">📎</span>
      <span id="file-preview-name"></span>
    </div>

    <div id="upload-alert"></div>

    <button class="btn-submit" onclick="confirmUpload()" style="margin-top:0">Upload Document</button>
  </div>
</div>


<script>
/* ══════════════════════════════════
   PAGE ROUTING
══════════════════════════════════ */
function showPage(pageId) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById(pageId).classList.add('active');
  window.scrollTo(0, 0);
}

function scrollToTop() {
  window.scrollTo(0,0);
}

function toggleMobileNav() {
  document.getElementById('mobile-nav').classList.toggle('open');
}
function closeMobileNav() {
  document.getElementById('mobile-nav').classList.remove('open');
}

/* ══════════════════════════════════
   INTERSECTION OBSERVER – fade in
══════════════════════════════════ */
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
}, { threshold: 0.12 });
document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

/* ══════════════════════════════════
   AUTH STATE (localStorage simulation)
══════════════════════════════════ */
const USERS_KEY = 'cjc_users';
const SESSION_KEY = 'cjc_session';
const DOCS_KEY = 'cjc_documents';

function getUsers() {
  return JSON.parse(localStorage.getItem(USERS_KEY) || '[]');
}
function saveUsers(users) {
  localStorage.setItem(USERS_KEY, JSON.stringify(users));
}
function getSession() {
  return JSON.parse(localStorage.getItem(SESSION_KEY) || 'null');
}
function setSession(user) {
  localStorage.setItem(SESSION_KEY, JSON.stringify(user));
}
function clearSession() {
  localStorage.removeItem(SESSION_KEY);
}
function getDocState(userEmail) {
  const all = JSON.parse(localStorage.getItem(DOCS_KEY) || '{}');
  return all[userEmail] || {};
}
function saveDocState(userEmail, state) {
  const all = JSON.parse(localStorage.getItem(DOCS_KEY) || '{}');
  all[userEmail] = state;
  localStorage.setItem(DOCS_KEY, JSON.stringify(all));
}

// Seed admin
(function seedAdmin() {
  let users = getUsers();
  if (!users.find(u => u.email === 'admin@cjc-edu.com')) {
    users.push({ email: 'admin@cjc-edu.com', password: 'admin123', name: 'CJC Admin', role: 'admin', destination: 'N/A' });
    saveUsers(users);
  }
})();

/* ══════════════════════════════════
   AUTH TABS
══════════════════════════════════ */
function switchTab(tab) {
  document.querySelectorAll('.auth-tab').forEach((t,i) => {
    t.classList.toggle('active', (i===0 && tab==='login') || (i===1 && tab==='register'));
  });
  document.getElementById('login-form').style.display = tab === 'login' ? 'block' : 'none';
  document.getElementById('register-form').style.display = tab === 'register' ? 'block' : 'none';
}

function showAlert(id, type, msg) {
  const el = document.getElementById(id);
  el.className = 'alert ' + type;
  el.textContent = msg;
}

function handleLogin() {
  const email = document.getElementById('login-email').value.trim();
  const pass  = document.getElementById('login-password').value;
  const role  = document.getElementById('login-role').value;

  if (!email || !pass) return showAlert('login-alert','error','Please fill in all fields.');

  const users = getUsers();
  const user = users.find(u => u.email === email && u.password === pass);

  if (!user) return showAlert('login-alert','error','Incorrect email or password.');
  if (role === 'admin' && user.role !== 'admin') return showAlert('login-alert','error','You do not have admin access.');

  setSession(user);
  loadDashboard(user);
}

function handleRegister() {
  const name  = document.getElementById('reg-name').value.trim();
  const email = document.getElementById('reg-email').value.trim();
  const dest  = document.getElementById('reg-dest').value;
  const pass  = document.getElementById('reg-password').value;

  if (!name || !email || !dest || !pass) return showAlert('register-alert','error','Please fill in all fields.');
  if (pass.length < 8) return showAlert('register-alert','error','Password must be at least 8 characters.');

  const users = getUsers();
  if (users.find(u => u.email === email)) return showAlert('register-alert','error','An account with this email already exists.');

  const newUser = { email, password: pass, name, role: 'applicant', destination: dest };
  users.push(newUser);
  saveUsers(users);
  setSession(newUser);
  showAlert('register-alert','success','Account created! Signing you in...');
  setTimeout(() => loadDashboard(newUser), 800);
}

function handleLogout() {
  clearSession();
  document.getElementById('dashboard').style.display = 'none';
  document.getElementById('portal-login').style.display = 'flex';
  document.getElementById('login-email').value = '';
  document.getElementById('login-password').value = '';
}

/* ══════════════════════════════════
   CHECKLIST DATA
══════════════════════════════════ */
const CHECKLIST = [
  {
    section: '📚 Academic Documents', items: [
      'High School Diploma or SHS Diploma & F138',
      'College Diploma (if applicable)',
      'Transcript of Records (TOR) or True Copy of Grades (TCG)',
      'IELTS / PTE Academic Test Results',
      'Certificate of Enrollment or Attendance (if currently enrolled)',
      'Curriculum Vitae (CV) — latest and updated',
    ]
  },
  {
    section: '🪪 Personal Documents', items: [
      'Valid Passport (all pages, including signature page)',
      'PSA Birth Certificate',
      'Marriage Certificate (if applicable)',
      'Passport Photos (recent, white background)',
    ]
  },
  {
    section: '💰 Financial Documents', items: [
      'Bank Certificate (original, bank-stamped)',
      'Bank Statement / Statement of Account (3–6 months)',
      'Time Deposit Certificate (if applicable)',
      'Sponsorship / Affidavit of Support (if with sponsor)',
      'Sponsor\'s Bank Certificate and Statement',
      'Income Tax Return (ITR) or Certificate of Employment',
    ]
  },
  {
    section: '🏥 Health Documents', items: [
      'Medical Examination Results',
      'Chest X-Ray Results',
      'OSHC / Health Insurance Certificate (Australia)',
      'Health Insurance Coverage (New Zealand)',
    ]
  },
  {
    section: '📝 Visa & Application Documents', items: [
      'Confirmation of Enrolment (CoE) — Australia',
      'Offer of Place — New Zealand',
      'Genuine Student (GS) Statement — Australia',
      'Statement of Purpose (SOP)',
      'Police Clearance Certificate (NZ / if required)',
      'Proof of Accommodation Arrangements',
      'Return Travel Evidence or Funds for Onward Travel',
      'Biometrics Receipt',
    ]
  },
];

const ALL_ITEMS = CHECKLIST.flatMap(s => s.items);

/* ══════════════════════════════════
   DASHBOARD LOADER
══════════════════════════════════ */
function loadDashboard(user) {
  document.getElementById('portal-login').style.display = 'none';
  document.getElementById('dashboard').style.display = 'block';

  const initials = user.name.split(' ').map(n=>n[0]).join('').slice(0,2).toUpperCase();
  document.getElementById('avatar-initials').textContent = initials;
  document.getElementById('user-display-name').textContent = user.name;
  document.getElementById('user-display-role').textContent = user.role === 'admin' ? 'CJC Staff / Admin' : `Applicant — ${user.destination}`;
  document.getElementById('overview-name').textContent = user.name.split(' ')[0];

  if (user.role === 'admin') {
    document.getElementById('admin-nav-item').style.display = 'block';
    loadAdminPanel();
  }

  renderChecklist(user.email);
  renderUploads(user.email);
  renderNotifications(user.role);
  updateProgress(user.email);
  renderOverview(user.email);

  switchPanel('overview');
}

/* ══════════════════════════════════
   CHECKLIST RENDER
══════════════════════════════════ */
let currentDocName = '';
let currentUserEmail = '';

function renderChecklist(email) {
  currentUserEmail = email;
  const docState = getDocState(email);
  let html = '';

  CHECKLIST.forEach(section => {
    html += `<div class="checklist-section">
      <div class="checklist-section-title">${section.section}</div>`;
    section.items.forEach(item => {
      const key = btoa(item);
      const state = docState[key] || { checked: false, uploaded: false, fileName: '' };
      const completedClass = state.uploaded ? 'completed' : '';
      const statusLabel = state.uploaded
        ? `<span class="item-status status-uploaded">✓ Uploaded</span>`
        : state.checked
          ? `<span class="item-status status-pending">Reviewed</span>`
          : `<span class="item-status status-required">Required</span>`;
      const uploadLabel = state.uploaded
        ? `<button class="upload-btn replace" onclick="openModal('${key}', '${item.replace(/'/g,"\\'")}')">Replace</button>`
        : `<button class="upload-btn" onclick="openModal('${key}', '${item.replace(/'/g,"\\'")}')">Upload</button>`;
      const checkedClass = state.checked || state.uploaded ? 'checked' : '';

      html += `<div class="checklist-item ${completedClass}" id="item-${key}">
        <div class="check-box ${checkedClass}" onclick="toggleCheck('${key}', '${email}')"></div>
        <span class="item-name">${item}</span>
        ${statusLabel}
        ${uploadLabel}
      </div>`;
    });
    html += `</div>`;
  });

  document.getElementById('checklist-content').innerHTML = html;
}

function toggleCheck(key, email) {
  const docState = getDocState(email);
  if (!docState[key]) docState[key] = { checked: false, uploaded: false, fileName: '' };
  if (!docState[key].uploaded) {
    docState[key].checked = !docState[key].checked;
    saveDocState(email, docState);
    renderChecklist(email);
    updateProgress(email);
    renderOverview(email);
  }
}

/* ══════════════════════════════════
   UPLOAD MODAL
══════════════════════════════════ */
let pendingUploadKey = '';

function openModal(key, docName) {
  pendingUploadKey = key;
  document.getElementById('modal-doc-name').textContent = docName;
  document.getElementById('file-preview').className = 'file-preview';
  document.getElementById('upload-alert').innerHTML = '';
  document.getElementById('file-input').value = '';
  document.getElementById('upload-modal').classList.add('open');
}

function closeModal() {
  document.getElementById('upload-modal').classList.remove('open');
  pendingUploadKey = '';
}

function handleDragOver(e) {
  e.preventDefault();
  document.getElementById('drop-zone').classList.add('drag-over');
}
function handleDragLeave() {
  document.getElementById('drop-zone').classList.remove('drag-over');
}
function handleDrop(e) {
  e.preventDefault();
  document.getElementById('drop-zone').classList.remove('drag-over');
  const file = e.dataTransfer.files[0];
  if (file) showFilePreview(file);
}
function handleFileSelect(e) {
  const file = e.target.files[0];
  if (file) showFilePreview(file);
}
function showFilePreview(file) {
  const preview = document.getElementById('file-preview');
  document.getElementById('file-preview-name').textContent = `${file.name} (${(file.size/1024).toFixed(1)} KB)`;
  preview.className = 'file-preview show';
}

function confirmUpload() {
  const fileInput = document.getElementById('file-input');
  const fileName = fileInput.files[0] ? fileInput.files[0].name : '';

  if (!fileName) {
    document.getElementById('upload-alert').innerHTML = '<div class="alert error">Please select a file to upload.</div>';
    return;
  }

  const docState = getDocState(currentUserEmail);
  if (!docState[pendingUploadKey]) docState[pendingUploadKey] = {};
  docState[pendingUploadKey].uploaded = true;
  docState[pendingUploadKey].checked = true;
  docState[pendingUploadKey].fileName = fileName;
  docState[pendingUploadKey].uploadedAt = new Date().toLocaleString();
  saveDocState(currentUserEmail, docState);

  closeModal();
  renderChecklist(currentUserEmail);
  renderUploads(currentUserEmail);
  updateProgress(currentUserEmail);
  renderOverview(currentUserEmail);
}

/* ══════════════════════════════════
   UPLOADS LIST
══════════════════════════════════ */
function renderUploads(email) {
  const docState = getDocState(email);
  const uploaded = ALL_ITEMS.filter(item => {
    const key = btoa(item);
    return docState[key] && docState[key].uploaded;
  });

  if (uploaded.length === 0) {
    document.getElementById('uploads-list').innerHTML = '<p style="color:#888;font-size:14px;padding:20px 0">No documents uploaded yet. Go to Document Checklist to get started.</p>';
    return;
  }

  let html = '';
  uploaded.forEach(item => {
    const key = btoa(item);
    const state = docState[key];
    html += `<div style="background:var(--white);border:1.5px solid var(--mist);border-radius:var(--r-sm);padding:16px 20px;margin-bottom:8px;display:flex;align-items:center;gap:16px;">
      <span style="font-size:24px;">📄</span>
      <div style="flex:1">
        <div style="font-size:14px;font-weight:500;color:var(--navy)">${item}</div>
        <div style="font-size:12px;color:#888;margin-top:2px;">📎 ${state.fileName} &nbsp;·&nbsp; Uploaded ${state.uploadedAt}</div>
      </div>
      <button class="upload-btn replace" onclick="openModal('${key}', '${item.replace(/'/g,"\\'")}')">Replace</button>
    </div>`;
  });
  document.getElementById('uploads-list').innerHTML = html;
}

/* ══════════════════════════════════
   PROGRESS & OVERVIEW
══════════════════════════════════ */
function updateProgress(email) {
  const docState = getDocState(email);
  const total = ALL_ITEMS.length;
  const uploaded = ALL_ITEMS.filter(item => {
    const key = btoa(item);
    return docState[key] && docState[key].uploaded;
  }).length;
  const pct = Math.round((uploaded / total) * 100);
  document.getElementById('prog-fill').style.width = pct + '%';
  document.getElementById('prog-pct').textContent = pct + '%';
}

function renderOverview(email) {
  const docState = getDocState(email);
  const total = ALL_ITEMS.length;
  const uploadedItems = ALL_ITEMS.filter(item => docState[btoa(item)]?.uploaded);
  const pending = total - uploadedItems.length;

  document.getElementById('ov-uploaded').textContent = uploadedItems.length;
  document.getElementById('ov-pending').textContent = pending;
  document.getElementById('ov-progress').textContent = Math.round((uploadedItems.length / total) * 100) + '%';

  // Next steps
  const missing = ALL_ITEMS.filter(item => !docState[btoa(item)]?.uploaded).slice(0, 4);
  const html = missing.length === 0
    ? '<div style="color:var(--success);font-weight:500;font-size:15px;">🎉 All documents uploaded! CJC will review your application shortly.</div>'
    : missing.map(m => `<div style="padding:10px 0;border-bottom:1px solid var(--mist);font-size:14px;color:#555">📌 Upload: <strong>${m}</strong></div>`).join('');
  document.getElementById('next-steps-list').innerHTML = html;
}

/* ══════════════════════════════════
   NOTIFICATIONS
══════════════════════════════════ */
function renderNotifications(role) {
  const notices = role === 'admin' ? [
    { type:'info', icon:'📬', title:'New applicant registered', text:'Juan Dela Cruz has created an account.', time:'Just now' },
    { type:'success', icon:'✅', title:'Document received', text:'Maria Santos uploaded her Bank Certificate.', time:'2 hrs ago' },
    { type:'warn', icon:'⚠️', title:'Missing documents', text:'Pedro Reyes still has 6 pending requirements.', time:'Yesterday' },
  ] : [
    { type:'info', icon:'👋', title:'Welcome to your CJC portal!', text:'Start by uploading your documents using the checklist.', time:'Just now' },
    { type:'warn', icon:'📋', title:'Action required', text:'Please upload all required documents before your intake date.', time:'Today' },
    { type:'success', icon:'🎯', title:'Account verified', text:'Your CJC applicant account has been verified. Our team will be in touch.', time:'Today' },
  ];

  document.getElementById('notify-list').innerHTML = notices.map(n => `
    <li class="notify-item ${n.type}">
      <span class="notify-icon">${n.icon}</span>
      <div class="notify-text">
        <h4>${n.title}</h4>
        <p>${n.text}</p>
      </div>
      <span class="notify-time">${n.time}</span>
    </li>`).join('');
}

/* ══════════════════════════════════
   ADMIN PANEL
══════════════════════════════════ */
function loadAdminPanel() {
  const users = getUsers().filter(u => u.role !== 'admin');
  if (users.length === 0) {
    document.getElementById('admin-content').innerHTML = '<p style="color:#888;font-size:14px">No applicants have registered yet.</p>';
    return;
  }

  let html = `<div style="margin-bottom:24px"><input type="text" placeholder="🔍 Search applicants..." style="padding:10px 16px;border:1.5px solid var(--mist);border-radius:var(--r-sm);font-size:14px;width:100%;max-width:360px;font-family:var(--body);outline:none" oninput="filterApplicants(this.value)"></div><div id="applicants-list">`;

  users.forEach(u => {
    const docState = getDocState(u.email);
    const uploaded = ALL_ITEMS.filter(item => docState[btoa(item)]?.uploaded).length;
    const pct = Math.round((uploaded / ALL_ITEMS.length) * 100);
    html += `<div class="admin-applicant-card" data-name="${u.name.toLowerCase()}">
      <div>
        <div class="appl-name">${u.name}</div>
        <div class="appl-meta">📧 ${u.email} &nbsp;·&nbsp; 🌏 ${u.destination}</div>
        <div class="appl-progress">
          <div class="mini-bar"><div class="mini-fill" style="width:${pct}%"></div></div>
          <span class="appl-pct">${pct}% complete</span>
          <span style="font-size:12px;color:#aaa">(${uploaded}/${ALL_ITEMS.length} docs)</span>
        </div>
      </div>
      <button class="btn-view" onclick="viewApplicantDocs('${u.email}', '${u.name}')">View Docs</button>
    </div>`;
  });
  html += '</div>';
  document.getElementById('admin-content').innerHTML = html;
}

function filterApplicants(q) {
  document.querySelectorAll('.admin-applicant-card').forEach(card => {
    card.style.display = card.dataset.name.includes(q.toLowerCase()) ? '' : 'none';
  });
}

function viewApplicantDocs(email, name) {
  const docState = getDocState(email);
  let html = `<div style="margin-bottom:20px"><button onclick="loadAdminPanel();switchPanel('admin')" style="background:none;border:1.5px solid var(--mist);padding:8px 16px;border-radius:var(--r-sm);cursor:pointer;font-family:var(--body);font-size:13px">← Back to applicants</button></div>
    <h3 style="font-family:var(--display);font-size:24px;color:var(--navy);margin-bottom:6px">${name}'s Documents</h3>
    <p style="color:#888;font-size:13px;margin-bottom:24px">${email}</p>`;

  CHECKLIST.forEach(section => {
    html += `<div style="margin-bottom:28px"><h4 style="font-family:var(--display);font-size:18px;color:var(--navy);border-bottom:2px solid var(--mist);padding-bottom:8px;margin-bottom:12px">${section.section}</h4>`;
    section.items.forEach(item => {
      const key = btoa(item);
      const state = docState[key] || {};
      const badge = state.uploaded
        ? `<span class="item-status status-uploaded">✓ ${state.fileName}</span>`
        : `<span class="item-status status-required">Not uploaded</span>`;
      html += `<div style="display:flex;align-items:center;gap:12px;padding:10px 0;border-bottom:1px solid var(--mist)">
        <span style="font-size:13px;flex:1;color:#444">${item}</span>
        ${badge}
      </div>`;
    });
    html += '</div>';
  });

  document.getElementById('admin-content').innerHTML = html;
}

/* ══════════════════════════════════
   PANEL SWITCHER
══════════════════════════════════ */
function switchPanel(id) {
  document.querySelectorAll('.dash-panel').forEach(p => p.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  document.querySelectorAll('.dash-nav li a').forEach(a => {
    a.classList.toggle('active', a.getAttribute('onclick') && a.getAttribute('onclick').includes(`'${id}'`));
  });
  if (id === 'admin') loadAdminPanel();
}

/* ══════════════════════════════════
   AUTO-RESTORE SESSION
══════════════════════════════════ */
window.addEventListener('DOMContentLoaded', () => {
  const session = getSession();
  if (session) {
    showPage('page-portal');
    loadDashboard(session);
  }
});
</script>

</body>
</html>
