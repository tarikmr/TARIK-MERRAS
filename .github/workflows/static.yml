<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Tarik Merras · Ingénieur Infrastructure IT | Portfolio Cyber</title>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #01010c;
      color: #edf2ff;
      font-family: 'Plus Jakarta Sans', sans-serif;
      line-height: 1.5;
      min-height: 100vh;
    }

    /* canvas pour fond dynamique */
    #canvas-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
      pointer-events: none;
    }

    .container {
      position: relative;
      z-index: 10;
      max-width: 1200px;
      margin: 0 auto;
      padding: 30px 24px 70px;
    }

    /* animations globales */
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-8px); }
    }
    @keyframes glowPulse {
      0%, 100% { box-shadow: 0 0 5px rgba(0, 212, 255, 0.3), 0 0 10px rgba(0, 212, 255, 0.1); }
      50% { box-shadow: 0 0 20px rgba(0, 212, 255, 0.6), 0 0 30px rgba(0, 212, 255, 0.2); }
    }
    @keyframes borderFlow {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    @keyframes slideUp {
      from { opacity: 0; transform: translateY(40px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .animate-in {
      animation: slideUp 0.7s cubic-bezier(0.2, 0.9, 0.4, 1.1) forwards;
      opacity: 0;
    }

    /* cartes glassmorphiques */
    .card {
      background: rgba(10, 16, 32, 0.55);
      backdrop-filter: blur(12px);
      border-radius: 32px;
      padding: 1.8rem;
      border: 1px solid rgba(0, 212, 255, 0.15);
      transition: all 0.35s ease;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
    }
    .card:hover {
      border-color: rgba(0, 212, 255, 0.5);
      box-shadow: 0 15px 40px rgba(0, 212, 255, 0.15);
      transform: translateY(-3px);
    }

    /* hero section avec gradient animé */
    .hero {
      background: linear-gradient(135deg, #0a1020, #030617);
      border-radius: 40px;
      padding: 2.8rem;
      margin-bottom: 35px;
      border: 1px solid rgba(0, 255, 255, 0.2);
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -20%;
      width: 140%;
      height: 140%;
      background: radial-gradient(circle, rgba(0,212,255,0.08), transparent 60%);
      animation: rotateHero 18s linear infinite;
    }
    @keyframes rotateHero {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    .hero h1 {
      font-size: 3.8rem;
      font-weight: 800;
      font-family: 'Space Grotesk', monospace;
      background: linear-gradient(135deg, #ffffff, #5ee0fa, #a855f7, #00d4ff);
      background-size: 300% 300%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: borderFlow 6s ease infinite;
    }
    .status-ring {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 18px;
      background: rgba(0, 229, 160, 0.08);
      border-radius: 100px;
      border: 1px solid rgba(0, 229, 160, 0.3);
      font-size: 0.75rem;
      font-weight: 600;
      color: #2ef0b0;
    }
    .contact-pill {
      background: rgba(255,255,255,0.04);
      border-radius: 60px;
      padding: 10px 20px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      text-decoration: none;
      color: #cfdfee;
      transition: all 0.25s;
      border: 1px solid rgba(255,255,255,0.05);
    }
    .contact-pill:hover {
      background: rgba(0,212,255,0.12);
      border-color: #00d4ff;
      color: white;
      transform: scale(1.02);
    }

    /* layout principal */
    .two-col {
      display: grid;
      grid-template-columns: 300px 1fr;
      gap: 28px;
    }

    /* skill tags 3D */
    .skill-item {
      background: rgba(0, 212, 255, 0.05);
      border-radius: 20px;
      padding: 6px 14px;
      font-size: 0.75rem;
      font-weight: 500;
      transition: 0.2s;
      cursor: default;
      border: 1px solid rgba(0,212,255,0.2);
    }
    .skill-item:hover {
      background: rgba(0,212,255,0.15);
      transform: translateX(5px);
      border-color: #00d4ff;
    }

    /* timeline modern */
    .tl-item {
      border-left: 2px solid #00d4ff;
      padding-left: 22px;
      margin-bottom: 28px;
      position: relative;
    }
    .tl-item::before {
      content: '';
      position: absolute;
      left: -8px;
      top: 0;
      width: 14px;
      height: 14px;
      background: #00d4ff;
      border-radius: 50%;
      animation: glowPulse 2s infinite;
    }
    .tl-title {
      font-weight: 700;
      font-size: 1rem;
      font-family: 'Space Grotesk', monospace;
    }

    /* CERTIFICATIONS : cartes néon ultra interactives */
    .cert-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(210px, 1fr));
      gap: 16px;
    }
    .cert-card-new {
      background: linear-gradient(135deg, #0f172a, #090e1a);
      border-radius: 24px;
      padding: 14px 16px;
      display: flex;
      align-items: center;
      gap: 14px;
      text-decoration: none;
      transition: all 0.3s cubic-bezier(0.2, 0.95, 0.4, 1.1);
      border: 1px solid #1e2a44;
      position: relative;
      overflow: hidden;
    }
    .cert-card-new i {
      font-size: 2rem;
      transition: all 0.3s;
    }
    .cert-card-new .cert-text {
      flex: 1;
    }
    .cert-card-new .cert-name {
      font-weight: 700;
      font-size: 0.85rem;
      color: #eef2ff;
    }
    .cert-card-new .cert-from {
      font-size: 0.65rem;
      color: #7f8ea3;
    }
    .cert-card-new::after {
      content: '⇢';
      position: absolute;
      right: 16px;
      top: 50%;
      transform: translateY(-50%);
      opacity: 0;
      transition: 0.25s;
      color: #00d4ff;
      font-size: 1.2rem;
    }
    .cert-card-new:hover {
      transform: translateY(-8px) scale(1.02);
      border-color: #00d4ff;
      box-shadow: 0 12px 28px -10px rgba(0,212,255,0.4);
      background: #0f182e;
    }
    .cert-card-new:hover i {
      transform: scale(1.1) rotate(2deg);
      filter: drop-shadow(0 0 6px #00d4ff);
    }
    .cert-card-new:hover::after {
      opacity: 1;
      right: 12px;
    }

    /* projet cards animées */
    .proj-card {
      background: rgba(0,0,0,0.3);
      border-radius: 20px;
      padding: 1rem;
      margin-bottom: 12px;
      border-left: 3px solid #00d4ff;
      transition: 0.25s;
    }
    .proj-card:hover {
      transform: translateX(8px);
      background: rgba(0,212,255,0.05);
    }

    @media (max-width: 780px) {
      .two-col { grid-template-columns: 1fr; }
      .hero h1 { font-size: 2.2rem; }
      .container { padding: 20px 16px; }
    }
  </style>
</head>
<body>

<canvas id="canvas-bg"></canvas>

<div class="container">
  <!-- HERO SECTION -->
  <div class="hero animate-in" style="animation-delay: 0.05s;">
    <div style="display: flex; justify-content: space-between; flex-wrap: wrap; gap: 20px; align-items: center;">
      <div>
        <div class="status-ring"><i class="fas fa-circle" style="font-size: 0.55rem; color:#0fba8b;"></i> Disponible · IT Infrastructure</div>
        <h1 style="margin: 16px 0 6px;">Tarik Merras</h1>
        <div style="font-size: 1.1rem; color: #b4c6f0; margin-bottom: 20px;">Technicien Supérieur · Systèmes & Réseaux</div>
        <div style="display: flex; flex-wrap: wrap; gap: 12px;">
          <a href="mailto:tarikmerras20@gmail.com" class="contact-pill"><i class="fas fa-envelope"></i> tarikmerras20@gmail.com</a>
          <a href="tel:+212693044430" class="contact-pill"><i class="fas fa-phone-alt"></i> +212 693 044 430</a>
          <span class="contact-pill"><i class="fas fa-map-marker-alt"></i> Meknès / Tanger</span>
        </div>
      </div>
      <div class="status-ring"><i class="fas fa-shield-haltered"></i> 30+ sites supportés</div>
    </div>
  </div>

  <!-- MAIN 2 COLONNES -->
  <div class="two-col">
    <!-- SIDEBAR -->
    <div class="animate-in" style="animation-delay: 0.1s;">
      <div class="card" style="margin-bottom: 24px;">
        <h3 style="font-family: 'Space Grotesk'; margin-bottom: 12px;"><i class="fas fa-user-astronaut" style="color:#00d4ff;"></i> À propos</h3>
        <p style="font-size: 0.85rem; color: #cbd5f0;">Spécialiste IT avec expérience terrain multi-sites (Tanger, Meknès). Expert Proxmox, pfSense, Active Directory, supervision GLPI/Zabbix. Passionné par l'optimisation et la cybersécurité des infrastructures critiques.</p>
      </div>
      <div class="card" style="margin-bottom: 24px;">
        <h3 style="margin-bottom: 14px;"><i class="fas fa-cogs"></i> Compétences</h3>
        <div style="display: flex; flex-wrap: wrap; gap: 8px;">
          <span class="skill-item">pfSense / FortiGate</span>
          <span class="skill-item">Proxmox / VMware</span>
          <span class="skill-item">Windows Server / AD</span>
          <span class="skill-item">VLANs / VPN / NAT</span>
          <span class="skill-item">Aruba Central / Cisco</span>
          <span class="skill-item">Linux / Scripting</span>
          <span class="skill-item">GLPI / Jira / Zabbix</span>
        </div>
      </div>
      <div class="card">
        <h3><i class="fas fa-globe"></i> Langues</h3>
        <div style="margin-top: 12px;">🇲🇦 Arabe (natif)</div>
        <div style="margin-top: 8px;">🇫🇷 Français (courant technique)</div>
        <div style="margin-top: 8px;">🇬🇧 Anglais (B2 - docs, support)</div>
      </div>
    </div>

    <!-- MAIN RIGHT -->
    <div>
      <!-- EXPERIENCE -->
      <div class="card animate-in" style="animation-delay: 0.15s; margin-bottom: 28px;">
        <h3 style="margin-bottom: 20px;"><i class="fas fa-briefcase"></i> Parcours professionnel</h3>
        <div class="tl-item"><div class="tl-title">Technicien IT · Eurostyle Systems</div><div style="color:#5ee0fa;">Mars 2026 – Présent</div><div style="font-size:0.8rem;">GLPI, Active Directory, inventaire, déploiement, serveur d'impression, vidéosurveillance.</div></div>
        <div class="tl-item"><div class="tl-title">Technicien support multi-sites · STM Tanger</div><div style="color:#5ee0fa;">Nov 2025 – Présent</div><div style="font-size:0.8rem;">30+ entreprises, support O365, déploiements, missions industrielles BAMESA / Intl Paper.<br><span class="status-ring" style="margin-top:6px;"><i class="fas fa-network-wired"></i> Mission Calsina Carré : Aruba switches + Aruba Central</span></div></div>
        <div class="tl-item"><div class="tl-title">Stage Systèmes & Réseaux · Commune Boufkrane</div><div style="color:#5ee0fa;">Avril–Mai 2025</div><div style="font-size:0.8rem;">Proxmox VE, pfSense, réseau sécurisé Wi-Fi/câblé, filtrage web.</div></div>
        <div class="tl-item"><div class="tl-title">Stage Technicien IT · Intelcia Meknès</div><div style="color:#5ee0fa;">Juillet–Août 2025</div><div style="font-size:0.8rem;">Windows Server / AD, support Jira, gestion parc informatique.</div></div>
      </div>

      <!-- CERTIFICATIONS SECTION (TOUS LIENS OPÉRATIONNELS) -->
      <div class="card animate-in" style="animation-delay: 0.2s; margin-bottom: 28px;">
        <h3 style="margin-bottom: 18px; display: flex; gap: 12px;"><i class="fas fa-certificate" style="color:#00d4ff;"></i> Certifications officielles <span class="status-ring"><i class="fas fa-hand-pointer"></i> Cliquez sur une carte</span></h3>
        <div class="cert-grid">
          <!-- CISCO -->
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/NetworkingBasics20250517-27-zfswbm.pdf" target="_blank" class="cert-card-new"><i class="fab fa-cisco" style="color:#00a0dc;"></i><div class="cert-text"><div class="cert-name">Networking Basics</div><div class="cert-from">Cisco Networking Academy</div></div></a>
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/NetworkDefense20250517-27-qe0r9e.pdf" target="_blank" class="cert-card-new"><i class="fab fa-cisco" style="color:#00a0dc;"></i><div><div class="cert-name">Network Defense</div><div class="cert-from">Cisco</div></div></a>
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/IntroductionToCybersecurity20250519-27-djgap4.pdf" target="_blank" class="cert-card-new"><i class="fas fa-shield-alt" style="color:#2dd4bf;"></i><div><div class="cert-name">Intro to Cybersecurity</div><div class="cert-from">Cisco</div></div></a>
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/EthicalHacker20250520-27-sxjvbg.pdf" target="_blank" class="cert-card-new"><i class="fas fa-user-secret" style="color:#a855f7;"></i><div><div class="cert-name">Ethical Hacker</div><div class="cert-from">Cisco</div></div></a>
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/IntrotoIoTUpdate20250620-27-2xhtad.pdf" target="_blank" class="cert-card-new"><i class="fas fa-microchip" style="color:#10b981;"></i><div><div class="cert-name">Introduction to IoT</div><div class="cert-from">Cisco</div></div></a>
          <!-- MICROSOFT -->
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/Achievements%20-%20tarikmerras-6925%20_%20Microsoft%20Learn.pdf" target="_blank" class="cert-card-new"><i class="fab fa-microsoft" style="color:#0078d4;"></i><div><div class="cert-name">Describe Cloud Computing</div><div class="cert-from">Microsoft Learn</div></div></a>
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/Succ%C3%A8s%20-%20tarikmerras-6925%20_%20Microsoft%20Learn.pdf" target="_blank" class="cert-card-new"><i class="fab fa-microsoft" style="color:#00a4ef;"></i><div><div class="cert-name">Composants Azure</div><div class="cert-from">Microsoft Learn</div></div></a>
          <!-- HP LIFE -->
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/certificate-1.pdf" target="_blank" class="cert-card-new"><i class="fas fa-brain" style="color:#ff8c00;"></i><div><div class="cert-name">AI for Beginners</div><div class="cert-from">HP LIFE</div></div></a>
          <a href="https://github.com/tarikmr/IDOSR/raw/7bd66ef527cf11b2bd9737386c9ff3e70581c542/certificate.pdf" target="_blank" class="cert-card-new"><i class="fas fa-envelope-open-text" style="color:#ffb347;"></i><div><div class="cert-name">Business Email</div><div class="cert-from">HP LIFE</div></div></a>
        </div>
      </div>

      <!-- PROJETS -->
      <div class="card animate-in" style="animation-delay: 0.25s;">
        <h3><i class="fas fa-rocket"></i> Réalisations techniques</h3>
        <div class="proj-card"><i class="fas fa-shield-haltered"></i> <strong>Boufkrane</strong> – Infrastructure Proxmox + pfSense + VLANs (100% sécurisée)</div>
        <div class="proj-card"><i class="fas fa-chart-line"></i> <strong>Supervision OFPPT</strong> – Zabbix/Nagios, réparation switches Cisco, backup serveurs</div>
        <div class="proj-card"><i class="fas fa-cloud-upload-alt"></i> <strong>Mission Aruba Central</strong> – Gestion cloud switches/APs, monitoring temps réel</div>
      </div>
    </div>
  </div>
</div>

<script>
  // canvas background animation (particules neuro)
  const canvas = document.getElementById('canvas-bg');
  const ctx = canvas.getContext('2d');
  let width, height;
  let particles = [];

  function resizeCanvas() {
    width = window.innerWidth;
    height = window.innerHeight;
    canvas.width = width;
    canvas.height = height;
  }

  class Particle {
    constructor() {
      this.x = Math.random() * width;
      this.y = Math.random() * height;
      this.size = Math.random() * 2 + 0.5;
      this.speedX = (Math.random() - 0.5) * 0.4;
      this.speedY = (Math.random() - 0.5) * 0.3;
      this.opacity = Math.random() * 0.3;
    }
    update() {
      this.x += this.speedX;
      this.y += this.speedY;
      if (this.x < 0) this.x = width;
      if (this.x > width) this.x = 0;
      if (this.y < 0) this.y = height;
      if (this.y > height) this.y = 0;
    }
    draw() {
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(0, 212, 255, ${this.opacity})`;
      ctx.fill();
    }
  }

  function initParticles() {
    particles = [];
    const count = Math.min(120, Math.floor(width / 15));
    for (let i = 0; i < count; i++) {
      particles.push(new Particle());
    }
  }

  function animateParticles() {
    ctx.clearRect(0, 0, width, height);
    for (let p of particles) {
      p.update();
      p.draw();
    }
    requestAnimationFrame(animateParticles);
  }

  window.addEventListener('resize', () => {
    resizeCanvas();
    initParticles();
  });
  resizeCanvas();
  initParticles();
  animateParticles();

  // déclencher animation d'apparition
  const toAnimate = document.querySelectorAll('.animate-in');
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  toAnimate.forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(40px)';
    el.style.transition = 'all 0.6s cubic-bezier(0.2, 0.9, 0.4, 1.1)';
    obs.observe(el);
  });
</script>
</body>
</html>
