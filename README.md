<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Srimathi K | MasterPortfolio</title>

  <!-- Google Fonts: Montserrat & Google Sans / Inter style -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link
    href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800;900&family=Open+Sans:wght@400;600;700&display=swap"
    rel="stylesheet">

  <!-- Lucide Icons & FontAwesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />

  <style>
    /* -------------------------------------------------------------
       MasterPortfolio Signature Theme Variables (Blue Theme)
       Reference: github.com/ashutosh1919/masterPortfolio
    -------------------------------------------------------------- */
    :root {
      --body-bg: #EDF9FE;
      --card-bg: #FFFFFF;
      --text: #001C55;
      --sub-text: #7F8DAA;
      --highlight: #A6E22E;
      --dark-blue: #001C55;
      --theme-blue: #0A66C2;
      --theme-cyan: #00B4D8;
      --badge-bg: #E3F2FD;
      --border-color: #D3E0EA;
      --shadow-light: 0 10px 30px rgba(0, 28, 85, 0.08);
      --shadow-hover: 0 16px 40px rgba(10, 102, 194, 0.16);
      --font-title: 'Montserrat', sans-serif;
      --font-body: 'Open Sans', sans-serif;
      --transition: all 0.3s ease-in-out;
    }

    [data-theme="dark"] {
      --body-bg: #171C28;
      --card-bg: #1F2839;
      --text: #F4F5F6;
      --sub-text: #868E96;
      --badge-bg: #273449;
      --border-color: #2F3E55;
      --shadow-light: 0 10px 30px rgba(0, 0, 0, 0.3);
      --shadow-hover: 0 16px 40px rgba(0, 180, 216, 0.2);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--body-bg);
      color: var(--text);
      font-family: var(--font-body);
      line-height: 1.6;
      transition: background-color 0.4s ease, color 0.4s ease;
      overflow-x: hidden;
    }

    h1,
    h2,
    h3,
    h4,
    h5,
    .logo-font {
      font-family: var(--font-title);
      font-weight: 700;
      color: var(--text);
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* -------------------------------------------------------------
       SPLASH SCREEN (MasterPortfolio signature animated loader)
    -------------------------------------------------------------- */
    #splash-screen {
      position: fixed;
      inset: 0;
      background: var(--body-bg);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      z-index: 99999;
      transition: opacity 0.8s ease, visibility 0.8s ease;
    }

    #splash-screen.fade-out {
      opacity: 0;
      visibility: hidden;
      pointer-events: none;
    }

    .splash-logo-box {
      width: 150px;
      height: 150px;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .splash-svg {
      width: 120px;
      height: 120px;
      filter: drop-shadow(0 8px 24px rgba(10, 102, 194, 0.3));
    }

    .splash-path {
      stroke: var(--theme-blue);
      stroke-width: 5;
      fill: transparent;
      stroke-dasharray: 600;
      stroke-dashoffset: 600;
      animation: drawStroke 2.2s cubic-bezier(0.77, 0, 0.175, 1) forwards;
    }

    .splash-inner-text {
      font-family: var(--font-title);
      font-size: 42px;
      font-weight: 800;
      fill: var(--theme-cyan);
      opacity: 0;
      animation: textAppear 1.2s ease 1s forwards;
    }

    .splash-name {
      margin-top: 24px;
      font-family: var(--font-title);
      font-size: 26px;
      font-weight: 800;
      color: var(--text);
      letter-spacing: 1px;
      opacity: 0;
      transform: translateY(12px);
      animation: splashUp 1s ease 1.2s forwards;
    }

    .splash-role {
      font-size: 14px;
      color: var(--sub-text);
      margin-top: 6px;
      text-transform: uppercase;
      letter-spacing: 3px;
      opacity: 0;
      animation: splashUp 1s ease 1.4s forwards;
    }

    @keyframes drawStroke {
      to {
        stroke-dashoffset: 0;
      }
    }

    @keyframes textAppear {
      to {
        opacity: 1;
      }
    }

    @keyframes splashUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* -------------------------------------------------------------
       NAVBAR (Ashutosh Hathidara masterPortfolio header style)
    -------------------------------------------------------------- */
    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      height: 80px;
      background: var(--body-bg);
      display: flex;
      align-items: center;
      z-index: 1000;
      transition: var(--transition);
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.03);
    }

    .nav-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
    }

    .logo-brand {
      font-family: 'Agustina', 'Montserrat', cursive, sans-serif;
      font-size: 24px;
      font-weight: 700;
      color: var(--text);
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .logo-bracket {
      color: var(--theme-blue);
      font-weight: 800;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 32px;
      list-style: none;
    }

    .nav-links a {
      font-family: var(--font-title);
      font-size: 15px;
      font-weight: 600;
      color: var(--text);
      transition: var(--transition);
      position: relative;
    }

    .nav-links a:hover {
      color: var(--theme-blue);
    }

    .theme-toggle-btn {
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      width: 42px;
      height: 42px;
      border-radius: 50%;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text);
      font-size: 16px;
      transition: var(--transition);
    }

    .theme-toggle-btn:hover {
      transform: rotate(20deg);
      background: var(--theme-blue);
      color: #fff;
    }

    /* -------------------------------------------------------------
       HERO / GREETING SECTION
    -------------------------------------------------------------- */
    .hero-section {
      min-height: calc(100vh - 80px);
      margin-top: 80px;
      display: flex;
      align-items: center;
      padding: 60px 0;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      gap: 40px;
      align-items: center;
    }

    .greeting-sub {
      font-size: 15px;
      letter-spacing: 2px;
      text-transform: uppercase;
      font-weight: 700;
      color: var(--theme-blue);
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .hero-title {
      font-size: 52px;
      line-height: 1.15;
      margin-bottom: 20px;
      font-weight: 800;
    }

    .hero-title .wave {
      display: inline-block;
      animation: wave 2.2s infinite;
      transform-origin: 70% 70%;
    }

    @keyframes wave {

      0%,
      100% {
        transform: rotate(0deg);
      }

      20%,
      60% {
        transform: rotate(14deg);
      }

      40%,
      80% {
        transform: rotate(-14deg);
      }
    }

    .hero-bio {
      font-size: 18px;
      color: var(--sub-text);
      line-height: 1.8;
      margin-bottom: 30px;
    }

    .social-media-div {
      display: flex;
      gap: 16px;
      margin-bottom: 34px;
    }

    .icon-button {
      width: 46px;
      height: 46px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      color: #fff;
      transition: var(--transition);
      box-shadow: 0 4px 14px rgba(0, 0, 0, 0.1);
    }

    .icon-button.github {
      background: #333;
    }

    .icon-button.linkedin {
      background: #0077b5;
    }

    .icon-button.mail {
      background: #ea4335;
    }

    .icon-button.phone {
      background: #25d366;
    }

    .icon-button:hover {
      transform: translateY(-4px) scale(1.08);
      box-shadow: var(--shadow-hover);
    }

    .hero-actions {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .btn-main {
      background-color: var(--theme-blue);
      color: #fff;
      padding: 14px 28px;
      font-family: var(--font-title);
      font-weight: 700;
      font-size: 14px;
      text-transform: uppercase;
      letter-spacing: 1px;
      border-radius: 8px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      transition: var(--transition);
      box-shadow: 0 8px 20px rgba(10, 102, 194, 0.3);
    }

    .btn-main:hover {
      background-color: #001C55;
      transform: translateY(-2px);
      box-shadow: var(--shadow-hover);
    }

    .btn-outline {
      border: 2px solid var(--theme-blue);
      color: var(--theme-blue);
      padding: 12px 26px;
      font-family: var(--font-title);
      font-weight: 700;
      font-size: 14px;
      border-radius: 8px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      transition: var(--transition);
      background: transparent;
    }

    .btn-outline:hover {
      background: var(--theme-blue);
      color: #fff;
      transform: translateY(-2px);
    }

    /* MasterPortfolio Illustrative Vector Hero Badge */
    .hero-art-container {
      position: relative;
      display: flex;
      justify-content: center;
    }

    .vector-dev-card {
      background: var(--card-bg);
      border-radius: 20px;
      padding: 36px;
      border: 1px solid var(--border-color);
      box-shadow: var(--shadow-light);
      position: relative;
      width: 100%;
      max-width: 440px;
    }

    .code-editor-header {
      display: flex;
      gap: 8px;
      margin-bottom: 20px;
      padding-bottom: 12px;
      border-bottom: 1px solid var(--border-color);
    }

    .dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
    }

    .dot.red {
      background: #ff5f56;
    }

    .dot.yellow {
      background: #ffbd2e;
    }

    .dot.green {
      background: #27c93f;
    }

    .code-preview {
      font-family: 'Courier New', Courier, monospace;
      font-size: 13px;
      line-height: 1.7;
      color: var(--text);
    }

    .code-keyword {
      color: #d73a49;
      font-weight: bold;
    }

    .code-var {
      color: #6f42c1;
    }

    .code-string {
      color: #032f62;
    }

    .code-comment {
      color: var(--sub-text);
      font-style: italic;
    }

    /* -------------------------------------------------------------
       WHAT I DO SECTION
    -------------------------------------------------------------- */
    .section-title {
      font-size: 40px;
      text-align: center;
      margin-bottom: 12px;
      position: relative;
    }

    .section-subtitle {
      text-align: center;
      color: var(--sub-text);
      font-size: 16px;
      max-width: 650px;
      margin: 0 auto 50px auto;
    }

    .skills-pillar-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 28px;
      margin-bottom: 60px;
    }

    .pillar-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 32px 28px;
      border: 1px solid var(--border-color);
      box-shadow: var(--shadow-light);
      transition: var(--transition);
      position: relative;
      overflow: hidden;
    }

    .pillar-card:hover {
      transform: translateY(-6px);
      box-shadow: var(--shadow-hover);
      border-color: var(--theme-blue);
    }

    .pillar-icon-box {
      width: 60px;
      height: 60px;
      border-radius: 12px;
      background: var(--badge-bg);
      color: var(--theme-blue);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 26px;
      margin-bottom: 22px;
    }

    .pillar-card h3 {
      font-size: 21px;
      margin-bottom: 14px;
    }

    .pillar-card ul {
      list-style: none;
      padding: 0;
    }

    .pillar-card li {
      font-size: 14px;
      color: var(--sub-text);
      margin-bottom: 10px;
      display: flex;
      align-items: flex-start;
      gap: 10px;
    }

    .pillar-card li i {
      color: var(--theme-cyan);
      margin-top: 4px;
    }

    /* -------------------------------------------------------------
       SKILLS LOGO CLOUD (MasterPortfolio iconify style)
    -------------------------------------------------------------- */
    .skills-tech-box {
      background: var(--card-bg);
      border-radius: 20px;
      padding: 40px;
      border: 1px solid var(--border-color);
      box-shadow: var(--shadow-light);
      text-align: center;
      margin-bottom: 80px;
    }

    .skills-tech-box h3 {
      margin-bottom: 24px;
      font-size: 22px;
    }

    .tech-icons-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 28px;
    }

    .tech-badge {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      transition: var(--transition);
    }

    .tech-badge:hover {
      transform: translateY(-6px) scale(1.08);
    }

    .tech-badge i {
      font-size: 40px;
      color: var(--sub-text);
      transition: var(--transition);
    }

    .tech-badge:hover i {
      color: var(--theme-blue);
    }

    .tech-badge span {
      font-family: var(--font-title);
      font-size: 12px;
      font-weight: 700;
      color: var(--sub-text);
    }

    /* -------------------------------------------------------------
       EXPERIENCE SECTION (Tap Academy & IT Expert Training)
    -------------------------------------------------------------- */
    .exp-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 28px;
      margin-bottom: 80px;
    }

    .exp-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 32px;
      border: 1px solid var(--border-color);
      box-shadow: var(--shadow-light);
      position: relative;
      transition: var(--transition);
    }

    .exp-card:hover {
      box-shadow: var(--shadow-hover);
      transform: translateY(-4px);
    }

    .exp-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 16px;
    }

    .exp-company {
      font-size: 20px;
      font-weight: 800;
      color: var(--text);
    }

    .exp-role {
      font-size: 15px;
      font-weight: 600;
      color: var(--theme-blue);
      margin-top: 4px;
    }

    .exp-date-pill {
      background: var(--badge-bg);
      color: var(--theme-blue);
      padding: 6px 14px;
      border-radius: 20px;
      font-size: 12px;
      font-weight: 700;
      font-family: var(--font-title);
      white-space: nowrap;
    }

    .exp-card ul {
      margin-top: 18px;
      padding-left: 20px;
    }

    .exp-card li {
      font-size: 14px;
      color: var(--sub-text);
      margin-bottom: 10px;
      line-height: 1.6;
    }

    .exp-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 20px;
    }

    .chip {
      background: var(--badge-bg);
      color: var(--theme-blue);
      font-size: 11px;
      font-weight: 700;
      padding: 4px 10px;
      border-radius: 6px;
    }

    /* -------------------------------------------------------------
       FEATURED PROJECT SECTION (Women Safety Monitoring)
    -------------------------------------------------------------- */
    .project-hero-card {
      background: var(--card-bg);
      border-radius: 20px;
      border: 1px solid var(--border-color);
      box-shadow: var(--shadow-light);
      padding: 40px;
      margin-bottom: 80px;
      transition: var(--transition);
    }

    .project-hero-card:hover {
      box-shadow: var(--shadow-hover);
    }

    .project-header-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 16px;
      margin-bottom: 20px;
    }

    .project-title {
      font-size: 28px;
      font-weight: 800;
    }

    .project-date {
      color: var(--sub-text);
      font-size: 14px;
      font-weight: 600;
    }

    .project-desc {
      font-size: 16px;
      color: var(--sub-text);
      line-height: 1.8;
      margin-bottom: 24px;
    }

    .project-features-list {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 16px;
      margin-bottom: 28px;
    }

    .p-feat-item {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 14px;
      color: var(--text);
      font-weight: 600;
    }

    .p-feat-item i {
      color: #27c93f;
    }

    /* -------------------------------------------------------------
       EDUCATION SECTION
    -------------------------------------------------------------- */
    .edu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 24px;
      margin-bottom: 80px;
    }

    .edu-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 28px;
      border: 1px solid var(--border-color);
      box-shadow: var(--shadow-light);
      display: flex;
      gap: 20px;
      align-items: flex-start;
      transition: var(--transition);
    }

    .edu-card:hover {
      transform: translateY(-4px);
      box-shadow: var(--shadow-hover);
    }

    .edu-icon {
      font-size: 32px;
      color: var(--theme-blue);
      background: var(--badge-bg);
      width: 56px;
      height: 56px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    .edu-degree {
      font-size: 18px;
      font-weight: 800;
      margin-bottom: 4px;
    }

    .edu-school {
      font-size: 14px;
      color: var(--sub-text);
      margin-bottom: 8px;
    }

    .edu-score {
      font-family: var(--font-title);
      font-size: 13px;
      font-weight: 700;
      color: var(--theme-cyan);
    }

    /* -------------------------------------------------------------
       FOOTER & REACH OUT (MasterPortfolio style)
    -------------------------------------------------------------- */
    .footer-reach {
      background: var(--card-bg);
      border-top: 1px solid var(--border-color);
      padding: 60px 0 30px 0;
      text-align: center;
    }

    .footer-reach h2 {
      font-size: 36px;
      margin-bottom: 12px;
    }

    .footer-reach p {
      color: var(--sub-text);
      max-width: 500px;
      margin: 0 auto 30px auto;
      font-size: 16px;
    }

    .contact-details-row {
      display: flex;
      justify-content: center;
      gap: 36px;
      margin-bottom: 34px;
      flex-wrap: wrap;
    }

    .contact-link-item {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 600;
      color: var(--text);
      transition: var(--transition);
    }

    .contact-link-item:hover {
      color: var(--theme-blue);
    }

    .copy-claim {
      font-size: 13px;
      color: var(--sub-text);
      margin-top: 40px;
      border-top: 1px solid var(--border-color);
      padding-top: 24px;
    }

    /* Responsive */
    @media (max-width: 900px) {
      .hero-grid {
        grid-template-columns: 1fr;
      }

      .exp-grid {
        grid-template-columns: 1fr;
      }

      .hero-title {
        font-size: 38px;
      }

      .nav-links {
        display: none;
      }
    }
  </style>
</head>

<body data-theme="light">

  <!-- =============================================================
       MASTERPORTFOLIO ANIMATED SPLASH SCREEN
  ============================================================== -->
  <div id="splash-screen">
    <div class="splash-logo-box">
      <svg class="splash-svg" viewBox="0 0 100 100">
        <!-- Outer Animated Hexagon -->
        <polygon class="splash-path" points="50 5, 90 27.5, 90 72.5, 50 95, 10 72.5, 10 27.5" />
        <!-- Monogram Letter K / S -->
        <text x="50%" y="62%" text-anchor="middle" class="splash-inner-text">SK</text>
      </svg>
    </div>
    <div class="splash-name">SRIMATHI K</div>
    <div class="splash-role">Data Analytics & Embedded IoT</div>
  </div>

  <!-- =============================================================
       NAVIGATION BAR
  ============================================================== -->
  <header>
    <div class="container nav-container">
      <a href="#home" class="logo-brand">
        <span class="logo-bracket">&lt;</span> Srimathi K <span class="logo-bracket">/&gt;</span>
      </a>

      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#contact">Contact</a></li>
        <li>
          <button class="theme-toggle-btn" id="themeToggle" title="Toggle Theme">
            <i class="fa-solid fa-moon"></i>
          </button>
        </li>
        <li>
          <button class="theme-toggle-btn" id="replaySplash" title="Replay Splash Screen">
            <i class="fa-solid fa-rotate-right"></i>
          </button>
        </li>
      </ul>
    </div>
  </header>

  <!-- =============================================================
       HERO / GREETING SECTION
  ============================================================== -->
  <section class="hero-section" id="home">
    <div class="container">
      <div class="hero-grid">
        <div class="hero-text-col">
          <div class="greeting-sub">
            <i class="fa-solid fa-terminal"></i> Data Analytics & Embedded Engineer
          </div>
          <h1 class="hero-title">
            Hi all, I'm Srimathi <span class="wave">👋</span>
          </h1>
          <p class="hero-bio">
            A passionate Electronics & Communication Engineering graduate focused on <strong>Data Analytics</strong>,
            statistical modelling, and <strong>Embedded Systems / IoT</strong> solutions. Experienced in transforming
            raw datasets into actionable intelligence using Python & SQL while engineering connected real-time hardware
            systems.
          </p>

          <div class="social-media-div">
            <a href="https://linkedin.com" target="_blank" class="icon-button linkedin" title="LinkedIn Profile">
              <i class="fa-brands fa-linkedin-in"></i>
            </a>
            <a href="mailto:srimathiece157@gmail.com" class="icon-button mail" title="Send Email">
              <i class="fa-solid fa-envelope"></i>
            </a>
            <a href="tel:+917200428978" class="icon-button phone" title="Call Me">
              <i class="fa-solid fa-phone"></i>
            </a>
            <a href="https://github.com" target="_blank" class="icon-button github" title="GitHub Repository">
              <i class="fa-brands fa-github"></i>
            </a>
          </div>

          <div class="hero-actions">
            <a href="#contact" class="btn-main">
              Contact Me <i class="fa-solid fa-arrow-right"></i>
            </a>
            <a href="#projects" class="btn-outline">
              View Work <i class="fa-solid fa-code"></i>
            </a>
          </div>
        </div>

        <!-- MasterPortfolio Code Style Card -->
        <div class="hero-art-container">
          <div class="vector-dev-card">
            <div class="code-editor-header">
              <div class="dot red"></div>
              <div class="dot yellow"></div>
              <div class="dot green"></div>
            </div>
            <pre class="code-preview">
<span class="code-keyword">const</span> <span class="code-var">developer</span> = {
  <span class="code-var">name</span>: <span class="code-string">"Srimathi K"</span>,
  <span class="code-var">degree</span>: <span class="code-string">"B.E. ECE"</span>,
  <span class="code-var">cgpa</span>: <span class="code-string">"8.28"</span>,
  <span class="code-var">domains</span>: [
    <span class="code-string">"Data Analytics"</span>,
    <span class="code-string">"Embedded Systems"</span>,
    <span class="code-string">"IoT Automation"</span>
  ],
  <span class="code-var">coreSkills</span>: [
    <span class="code-string">"Python"</span>, <span class="code-string">"SQL"</span>,
    <span class="code-string">"Power BI"</span>, <span class="code-string">"ESP32"</span>
  ],
  <span class="code-var">hardWorker</span>: <span class="code-keyword">true</span>,
  <span class="code-var">quickLearner</span>: <span class="code-keyword">true</span>
};
<span class="code-comment">// Ready to solve problems!</span></pre>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- =============================================================
       WHAT I DO (Skills Pillars)
  ============================================================== -->
  <section class="skills-section" id="skills" style="padding: 80px 0;">
    <div class="container">
      <h2 class="section-title">What I Do?</h2>
      <p class="section-subtitle">
        Bridging analytical insights with low-level hardware intelligence to build end-to-end, data-driven systems.
      </p>

      <div class="skills-pillar-grid">
        <!-- Pillar 1 -->
        <div class="pillar-card">
          <div class="pillar-icon-box">
            <i class="fa-solid fa-chart-line"></i>
          </div>
          <h3>Data Analytics</h3>
          <ul>
            <li><i class="fa-solid fa-circle-check"></i> Cleaned, validated, and transformed raw datasets using Pandas &
              NumPy</li>
            <li><i class="fa-solid fa-circle-check"></i> Executed Exploratory Data Analysis (EDA) on multi-dimensional
              data</li>
            <li><i class="fa-solid fa-circle-check"></i> Built robust SQL queries and managed schemas using MySQL</li>
            <li><i class="fa-solid fa-circle-check"></i> Applied statistical methods to draw business and engineering
              conclusions</li>
          </ul>
        </div>

        <!-- Pillar 2 -->
        <div class="pillar-card">
          <div class="pillar-icon-box">
            <i class="fa-solid fa-chart-pie"></i>
          </div>
          <h3>Data Visualization & BI</h3>
          <ul>
            <li><i class="fa-solid fa-circle-check"></i> Crafted interactive KPI dashboards and reports in Microsoft
              Power BI</li>
            <li><i class="fa-solid fa-circle-check"></i> Designed visual worksheets and visual aggregations with Tableau
            </li>
            <li><i class="fa-solid fa-circle-check"></i> Programmed distribution & trend plots via Python Matplotlib
            </li>
            <li><i class="fa-solid fa-circle-check"></i> Built complex spreadsheets and pivot charts with Microsoft
              Excel</li>
          </ul>
        </div>

        <!-- Pillar 3 -->
        <div class="pillar-card">
          <div class="pillar-icon-box">
            <i class="fa-solid fa-microchip"></i>
          </div>
          <h3>Embedded Systems & IoT</h3>
          <ul>
            <li><i class="fa-solid fa-circle-check"></i> Microcontroller programming on ESP32 & Arduino platforms</li>
            <li><i class="fa-solid fa-circle-check"></i> Sensor interfacing, analog circuit breadboarding, and signal
              routing</li>
            <li><i class="fa-solid fa-circle-check"></i> Real-time GPS & GSM alert modules for emergency telematics</li>
            <li><i class="fa-solid fa-circle-check"></i> Integrated live hardware telemetry to Firebase & Cloud
              datastores</li>
          </ul>
        </div>
      </div>

      <!-- Icon Cloud in MasterPortfolio style -->
      <div class="skills-tech-box">
        <h3>Technologies & Environments</h3>
        <div class="tech-icons-row">
          <div class="tech-badge">
            <i class="fa-brands fa-python" style="color: #3776AB;"></i>
            <span>Python</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-database" style="color: #4479A1;"></i>
            <span>MySQL</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-table" style="color: #1D6F42;"></i>
            <span>Pandas</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-square-poll-vertical" style="color: #F2C811;"></i>
            <span>Power BI</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-chart-simple" style="color: #E97627;"></i>
            <span>Tableau</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-file-excel" style="color: #217346;"></i>
            <span>Excel</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-microchip" style="color: #00979D;"></i>
            <span>ESP32 / Arduino</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-fire" style="color: #FFA611;"></i>
            <span>Firebase</span>
          </div>
          <div class="tech-badge">
            <i class="fa-solid fa-book-open" style="color: #F37626;"></i>
            <span>Jupyter</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- =============================================================
       EXPERIENCE SECTION
  ============================================================== -->
  <section class="exp-section" id="experience" style="padding: 20px 0 80px 0;">
    <div class="container">
      <h2 class="section-title">Experiences</h2>
      <p class="section-subtitle">Internships and hands-on industrial practice.</p>

      <div class="exp-grid">
        <!-- Tap Academy -->
        <div class="exp-card">
          <div class="exp-top">
            <div>
              <div class="exp-company">Tap Academy</div>
              <div class="exp-role">Data Analytics Intern</div>
            </div>
            <span class="exp-date-pill">Jan 2026 – Present</span>
          </div>
          <ul>
            <li>Currently analyzing, cleaning, and preprocessing structured datasets using Python, SQL, and Microsoft
              Excel.</li>
            <li>Executing Exploratory Data Analysis (EDA) to extract meaningful business patterns and correlations.</li>
            <li>Conducting rigorous data validation, handling missing records, and formatting pipelines for reporting.
            </li>
          </ul>
          <div class="exp-tags">
            <span class="chip">Python</span>
            <span class="chip">SQL</span>
            <span class="chip">Pandas</span>
            <span class="chip">EDA</span>
            <span class="chip">Excel</span>
          </div>
        </div>

        <!-- IT Expert Training -->
        <div class="exp-card">
          <div class="exp-top">
            <div>
              <div class="exp-company">IT Expert Training, Chennai</div>
              <div class="exp-role">Embedded Systems Intern</div>
            </div>
            <span class="exp-date-pill">Jan 2026 – Apr 2026</span>
          </div>
          <ul>
            <li>Gained hands-on experience in Embedded Systems development, microcontroller programming, and pin
              routing.</li>
            <li>Assisted in multiple sensor interfacings, circuit design implementation, and real-time firmware
              execution.</li>
            <li>Tested and debugged embedded modules to improve transmission latency, system stability, and reliability.
            </li>
          </ul>
          <div class="exp-tags">
            <span class="chip">Microcontrollers</span>
            <span class="chip">C/Embedded</span>
            <span class="chip">Sensors</span>
            <span class="chip">Debugging</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- =============================================================
       PROJECTS SECTION
  ============================================================== -->
  <section class="project-section" id="projects" style="padding: 20px 0 80px 0;">
    <div class="container">
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-subtitle">Real-world systems integrating IoT telematics and cloud sync.</p>

      <div class="project-hero-card">
        <div class="project-header-row">
          <h3 class="project-title">Women Safety Monitoring System using IoT</h3>
          <span class="exp-date-pill">Jan 2026 – Mar 2026</span>
        </div>

        <p class="project-desc">
          Developed an end-to-end Women Safety Monitoring system utilizing IoT and cloud architecture for instantaneous
          emergency assistance. Designed specifically to enhance personal protection through fast-acting SOS
          notifications, satellite geolocation tracking, and persistent cloud sync.
        </p>

        <div class="project-features-list">
          <div class="p-feat-item">
            <i class="fa-solid fa-circle-check"></i> ESP32 & Arduino Core Processing
          </div>
          <div class="p-feat-item">
            <i class="fa-solid fa-circle-check"></i> GPS Module Live Telemetry Coordinates
          </div>
          <div class="p-feat-item">
            <i class="fa-solid fa-circle-check"></i> GSM Module Instant SMS to Contacts
          </div>
          <div class="p-feat-item">
            <i class="fa-solid fa-circle-check"></i> Firebase Real-Time Cloud Synchronization
          </div>
          <div class="p-feat-item">
            <i class="fa-solid fa-circle-check"></i> Rapid SOS Trigger & Location Monitoring
          </div>
          <div class="p-feat-item">
            <i class="fa-solid fa-circle-check"></i> Tested and Validated Fast Response Loop
          </div>
        </div>

        <div class="exp-tags">
          <span class="chip">IoT</span>
          <span class="chip">ESP32</span>
          <span class="chip">Arduino</span>
          <span class="chip">GPS</span>
          <span class="chip">GSM</span>
          <span class="chip">Firebase Cloud</span>
          <span class="chip">Hardware Interfacing</span>
        </div>
      </div>
    </div>
  </section>

  <!-- =============================================================
       EDUCATION SECTION
  ============================================================== -->
  <section class="edu-section" id="education" style="padding: 20px 0 80px 0;">
    <div class="container">
      <h2 class="section-title">Education</h2>
      <p class="section-subtitle">Academic qualifications and educational milestones.</p>

      <div class="edu-grid">
        <!-- B.E. -->
        <div class="edu-card">
          <div class="edu-icon">
            <i class="fa-solid fa-graduation-cap"></i>
          </div>
          <div>
            <div class="edu-degree">B.E. in Electronics & Communication</div>
            <div class="edu-school">Muthayammal Engineering College, India</div>
            <div class="edu-score">2022 – 2026 | CGPA: 8.28</div>
          </div>
        </div>

        <!-- HSC -->
        <div class="edu-card">
          <div class="edu-icon">
            <i class="fa-solid fa-school"></i>
          </div>
          <div>
            <div class="edu-degree">Higher Secondary Certificate (HSC)</div>
            <div class="edu-school">Kalaimagal Matric Higher Sec School</div>
            <div class="edu-score">2020 – 2022 | Percentage: 72.3%</div>
          </div>
        </div>

        <!-- SSLC -->
        <div class="edu-card">
          <div class="edu-icon">
            <i class="fa-solid fa-certificate"></i>
          </div>
          <div>
            <div class="edu-degree">Secondary School Leaving (SSLC)</div>
            <div class="edu-school">Kalaimagal Matric Higher Sec School</div>
            <div class="edu-score">2018 – 2020 | Percentage: 87.0%</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- =============================================================
       REACH OUT / FOOTER (MasterPortfolio style)
  ============================================================== -->
  <footer class="footer-reach" id="contact">
    <div class="container">
      <h2>Reach Out to Me!</h2>
      <p>
        DISCUSS A PROJECT OR JUST WANT TO SAY HI? MY INBOX IS OPEN FOR ALL.
      </p>

      <div class="contact-details-row">
        <a href="tel:+917200428978" class="contact-link-item">
          <i class="fa-solid fa-phone" style="color: #25d366;"></i> +91 7200428978
        </a>
        <a href="mailto:srimathiece157@gmail.com" class="contact-link-item">
          <i class="fa-solid fa-envelope" style="color: #ea4335;"></i> srimathiece157@gmail.com
        </a>
        <a href="https://linkedin.com" target="_blank" class="contact-link-item">
          <i class="fa-brands fa-linkedin" style="color: #0077b5;"></i> LinkedIn Profile
        </a>
      </div>

      <div class="social-media-div" style="justify-content: center;">
        <a href="https://linkedin.com" target="_blank" class="icon-button linkedin"><i
            class="fa-brands fa-linkedin-in"></i></a>
        <a href="mailto:srimathiece157@gmail.com" class="icon-button mail"><i class="fa-solid fa-envelope"></i></a>
        <a href="tel:+917200428978" class="icon-button phone"><i class="fa-solid fa-phone"></i></a>
      </div>

      <div class="copy-claim">
        Adapted with inspiration from <strong>Ashutosh Hathidara's masterPortfolio</strong> &bull; Crafted for
        <strong>Srimathi K</strong>
      </div>
    </div>
  </footer>

  <!-- =============================================================
       INTERACTION SCRIPTS
  ============================================================== -->
  <script>
    // Splash screen dismissal after initial animation
    window.addEventListener('load', () => {
      setTimeout(() => {
        const splash = document.getElementById('splash-screen');
        if (splash) {
          splash.classList.add('fade-out');
        }
      }, 2500);
    });

    // Replay splash screen trigger
    const replayBtn = document.getElementById('replaySplash');
    if (replayBtn) {
      replayBtn.addEventListener('click', () => {
        const splash = document.getElementById('splash-screen');
        splash.classList.remove('fade-out');
        setTimeout(() => {
          splash.classList.add('fade-out');
        }, 2500);
      });
    }

    // Light / Dark Theme toggle
    const themeBtn = document.getElementById('themeToggle');
    themeBtn.addEventListener('click', () => {
      const currentTheme = document.body.getAttribute('data-theme');
      const newTheme = currentTheme === 'light' ? 'dark' : 'light';
      document.body.setAttribute('data-theme', newTheme);

      const icon = themeBtn.querySelector('i');
      if (newTheme === 'dark') {
        icon.classList.remove('fa-moon');
        icon.classList.add('fa-sun');
      } else {
        icon.classList.remove('fa-sun');
        icon.classList.add('fa-moon');
      }
    });
  </script>
</body>

</html>
