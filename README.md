Absolutely — here is a complete single-page personal portfolio website in HTML, CSS, and a little JavaScript. Save it as index.html and open it in your browser.

HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>saad khochikar| Portfolio</title>
  <meta name="description" content="Personal portfolio website for Your Name" />
  <style>
    :root {
      --bg: #0f172a;
      --bg-soft: #111827;
      --card: #1f2937;
      --card-2: #0b1220;
      --primary: #7c3aed;
      --secondary: #22c55e;
      --text: #e5e7eb;
      --muted: #94a3b8;
      --line: rgba(255,255,255,0.08);
      --white: #ffffff;
      --shadow: 0 20px 40px rgba(0,0,0,0.25);
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: linear-gradient(180deg, var(--bg) 0%, #0b1120 100%);
      color: var(--text);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(1120px, calc(100% - 32px));
      margin: 0 auto;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 50;
      background: rgba(15, 23, 42, 0.7);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--line);
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      min-height: 72px;
    }

    .logo {
      font-size: 1.2rem;
      font-weight: 700;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }

    .logo span {
      color: var(--primary);
    }

    .nav-links {
      display: flex;
      gap: 28px;
      align-items: center;
    }

    .nav-links a {
      color: var(--muted);
      transition: color 0.3s ease;
    }

    .nav-links a:hover {
      color: var(--white);
    }

    .nav-buttons {
      display: flex;
      gap: 12px;
      align-items: center;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      padding: 12px 22px;
      border: 1px solid var(--line);
      border-radius: 10px;
      background: transparent;
      color: var(--white);
      font-weight: 600;
      cursor: pointer;
      transition: 0.3s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
      box-shadow: var(--shadow);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--primary), #8b5cf6);
      border: none;
    }

    .btn-secondary {
      background: rgba(255,255,255,0.03);
    }

    section {
      padding: 90px 0;
    }

    .hero {
      padding-top: 80px;
      min-height: 80vh;
      display: flex;
      align-items: center;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 40px;
      align-items: center;
    }

    .tag {
      display: inline-block;
      padding: 8px 14px;
      border-radius: 999px;
      background: rgba(124, 58, 237, 0.12);
      color: #d8c5ff;
      border: 1px solid rgba(124, 58, 237, 0.35);
      font-size: 0.85rem;
      margin-bottom: 18px;
    }

    h1 {
      font-size: clamp(2.8rem, 5vw, 5rem);
      line-height: 1.05;
      margin: 0 0 18px;
      letter-spacing: -0.04em;
    }

    .gradient-text {
      background: linear-gradient(135deg, #f8fafc 0%, #a78bfa 50%, #34d399 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .lead {
      color: var(--muted);
      font-size: 1.08rem;
      max-width: 600px;
      margin-bottom: 26px;
    }

    .actions {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
      margin-bottom: 34px;
    }

    .stats {
      display: flex;
      gap: 32px;
      flex-wrap: wrap;
    }

    .stat strong {
      display: block;
      font-size: 1.6rem;
      margin-bottom: 4px;
    }

    .stat span {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .hero-card {
      background: linear-gradient(180deg, rgba(31,41,55,0.9), rgba(15,23,42,0.7));
      border: 1px solid var(--line);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 22px;
      position: relative;
      overflow: hidden;
    }

    .profile-box {
      background: linear-gradient(135deg, rgba(124,58,237,0.25), rgba(34,197,94,0.15));
      border-radius: 18px;
      padding: 18px;
      border: 1px solid rgba(255,255,255,0.08);
      margin-bottom: 20px;
    }

    .profile-art {
      height: 250px;
      border-radius: 16px;
      background:
        radial-gradient(circle at 30% 30%, rgba(255,255,255,0.25), transparent 20%),
        linear-gradient(135deg, #1e293b, #0f172a 60%, #111827);
      border: 1px solid rgba(255,255,255,0.08);
      position: relative;
      overflow: hidden;
    }

    .profile-art::before {
      content: "";
      position: absolute;
      width: 120px;
      height: 120px;
      background: linear-gradient(135deg, #a78bfa, #34d399);
      border-radius: 50%;
      right: 28px;
      top: 28px;
      box-shadow: 0 0 50px rgba(124,58,237,0.7);
    }

    .profile-art::after {
      content: "";
      position: absolute;
      width: 180px;
      height: 180px;
      border: 1px solid rgba(255,255,255,0.15);
      border-radius: 18px;
      left: 28px;
      bottom: 18px;
      transform: rotate(12deg);
    }

    .mini-card {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 12px 14px;
      background: rgba(15,23,42,0.8);
      border-radius: 12px;
      border: 1px solid var(--line);
      margin-top: 14px;
    }

    .mini-card strong {
      display: block;
      font-size: 1rem;
    }

    .mini-card span {
      color: var(--muted);
      font-size: 0.82rem;
    }

    .badge {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: var(--secondary);
      box-shadow: 0 0 12px rgba(34,197,94,0.8);
    }

    .section-head {
      margin-bottom: 36px;
    }

    .section-head h2 {
      font-size: clamp(2rem, 3vw, 3rem);
      margin: 0 0 10px;
      letter-spacing: -0.04em;
    }

    .section-head p {
      color: var(--muted);
      margin: 0;
      font-size: 1.04rem;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }

    .about-card, .skill-card, .project-card, .contact-card {
      background: rgba(17, 24, 39, 0.75);
      border: 1px solid var(--line);
      border-radius: 20px;
      padding: 28px;
      box-shadow: var(--shadow);
    }

    .about-card p {
      color: var(--muted);
      margin: 0 0 18px;
      font-size: 1.02rem;
    }

    .info-list {
      list-style: none;
      padding: 0;
      margin: 0;
      display: grid;
      gap: 12px;
    }

    .info-list li {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      padding-bottom: 10px;
      border-bottom: 1px solid var(--line);
      color: var(--muted);
    }

    .info-list strong {
      color: var(--white);
    }

    .skills-wrap {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 18px;
    }

    .skill-pill {
      padding: 10px 14px;
      border-radius: 999px;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--line);
      color: #dbeafe;
      font-size: 0.95rem;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 22px;
    }

    .project-card {
      padding: 0;
      overflow: hidden;
    }

    .project-thumb {
      height: 200px;
      background: linear-gradient(135deg, rgba(124,58,237,0.35), rgba(34,197,94,0.2));
      border-bottom: 1px solid var(--line);
      position: relative;
    }

    .project-thumb::before {
      content: "";
      position: absolute;
      inset: 20px;
      border-radius: 16px;
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(15,23,42,0.4);
    }

    .project-content {
      padding: 22px 22px 26px;
    }

    .project-content h3 {
      margin: 0 0 10px;
      font-size: 1.35rem;
    }

    .project-content p {
      color: var(--muted);
      margin: 0 0 18px;
    }

    .project-links {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .project-links a {
      color: #dbeafe;
      font-weight: 600;
    }

    .contact-wrap {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 24px;
      align-items: stretch;
    }

    .contact-card {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .contact-card p {
      color: var(--muted);
      margin-top: 0;
    }

    .contact-list {
      display: grid;
      gap: 14px;
      margin-top: 16px;
    }

    .contact-item {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 12px 14px;
      background: rgba(255,255,255,0.02);
      border: 1px solid var(--line);
      border-radius: 12px;
    }

    .contact-icon {
      width: 40px;
      height: 40px;
      border-radius: 10px;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--primary), #8b5cf6);
      font-weight: 700;
    }

    form {
      display: grid;
      gap: 14px;
    }

    input, textarea {
      width: 100%;
      padding: 14px 16px;
      border-radius: 12px;
      border: 1px solid var(--line);
      background: rgba(15, 23, 42, 0.7);
      color: var(--white);
      font: inherit;
    }

    input::placeholder, textarea::placeholder {
      color: var(--muted);
    }

    textarea {
      min-height: 140px;
      resize: vertical;
    }

    footer {
      border-top: 1px solid var(--line);
      padding: 24px 0 40px;
      color: var(--muted);
      text-align: center;
    }

    @media (max-width: 900px) {
      .hero-grid,
      .about-grid,
      .contact-wrap,
      .projects-grid {
        grid-template-columns: 1fr;
      }

      .nav-links {
        display: none;
      }

      .hero {
        padding-top: 40px;
      }
    }

    @media (max-width: 600px) {
      .nav {
        padding: 10px 0;
      }

      .nav-buttons .btn {
        padding: 10px 14px;
      }

      h1 {
        font-size: 2.6rem;
      }

      section {
        padding: 70px 0;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <a href="#home" class="logo"><span>Your</span> Name</a>

      <nav class="nav-links" aria-label="Main navigation">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </nav>

      <div class="nav-buttons">
        <a href="#projects" class="btn btn-secondary">View Work</a>
        <a href="#contact" class="btn btn-primary">Hire Me</a>
      </div>
    </div>
  </header>

  <main>
    <section id="home" class="hero">
      <div class="container hero-grid">
        <div>
          <div class="tag">Available for freelance & full-time roles</div>
          <h1>
            I build <span class="gradient-text">digital experiences</span><br />
            that people love.
          </h1>
          <p class="lead">
            I’m a <strong>Front-End Developer</strong> focused on creating modern, responsive, and user-friendly websites and web apps.
            I turn ideas into polished products that feel smooth, fast, and memorable.
          </p>

          <div class="actions">
            <a class="btn btn-primary" href="#projects">See My Work</a>
            <a class="btn btn-secondary" href="#contact">Contact Me</a>
          </div>

          <div class="stats">
            <div class="stat">
              <strong>4+</strong>
              <span>Years Experience</span>
            </div>
            <div class="stat">
              <strong>20+</strong>
              <span>Projects Delivered</span>
            </div>
            <div class="stat">
              <strong>8+</strong>
              <span>Clients Served</span>
            </div>
          </div>
        </div>

        <div class="hero-card">
          <div class="profile-box">
            <div class="profile-art" aria-label="Profile illustration"></div>
          </div>

          <div class="mini-card">
            <div>
              <strong>Currently working on</strong>
              <span>Portfolio redesign & SaaS UI</span>
            </div>
            <div class="badge" aria-label="Available"></div>
          </div>

          <div class="mini-card">
            <div>
              <strong>Based in</strong>
              <span>New York, USA</span>
            </div>
            <div class="badge" aria-label="Location"></div>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-head">
          <h2>About Me</h2>
          <p>I design and build high-quality digital products with a strong focus on usability and performance.</p>
        </div>

        <div class="about-grid">
          <div class="about-card">
            <p>
              Hello! I’m <strong>Your Name</strong>, a creative developer and problem-solver passionate about building clean,
              intuitive, and modern web experiences. My work blends design thinking with technical execution to deliver products
              that are both visually appealing and functionally effective.
            </p>

            <p>
              I enjoy collaborating with teams, learning new tools, and turning ideas into strong user experiences. Whether it’s a landing page,
              business website, or full web application, I focus on clarity, responsiveness, and meaningful results.
            </p>
          </div>

          <div class="about-card">
            <ul class="info-list">
              <li><span>Name</span> <strong>Your Name</strong></li>
              <li><span>Email</span> <strong>you@example.com</strong></li>
              <li><span>Phone</span> <strong>+1 (234) 567-890</strong></li>
              <li><span>Experience</span> <strong>4+ Years</strong></li>
              <li><span>Focus</span> <strong>Web Design / Front-End</strong></li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="container">
        <div class="section-head">
          <h2>Skills</h2>
          <p>Tools and technologies I work with to bring ideas to life.</p>
        </div>

        <div class="skills-wrap">
          <span class="skill-pill">HTML5</span>
          <span class="skill-pill">CSS3</span>
          <span class="skill-pill">JavaScript</span>
          <span class="skill-pill">React</span>
          <span class="skill-pill">TypeScript</span>
          <span class="skill-pill">Bootstrap</span>
          <span class="skill-pill">Tailwind CSS</span>
          <span class="skill-pill">Node.js</span>
          <span class="skill-pill">Git & GitHub</span>
          <span class="skill-pill">UI/UX Design</span>
          <span class="skill-pill">Responsive Design</span>
          <span class="skill-pill">Figma</span>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="container">
        <div class="section-head">
          <h2>Featured Projects</h2>
          <p>A few examples of my recent work and experiments.</p>
        </div>

        <div class="projects-grid">
          <article class="project-card">
            <div class="project-thumb"></div>
            <div class="project-content">
              <h3>Project One</h3>
              <p>A modern business website designed to improve credibility, conversions, and digital presence.</p>
              <div class="project-links">
                <a href="#">Live Demo</a>
                <a href="#">Source Code</a>
              </div>
            </div>
          </article>

          <article class="project-card">
            <div class="project-thumb"></div>
            <div class="project-content">
              <h3>Project Two</h3>
              <p>A clean and responsive portfolio platform built for a client looking to showcase services and case studies.</p>
              <div class="project-links">
                <a href="#">Live Demo</a>
                <a href="#">Source Code</a>
              </div>
            </div>
          </article>

          <article class="project-card">
            <div class="project-thumb"></div>
            <div class="project-content">
              <h3>Project Three</h3>
              <p>An interactive dashboard interface focused on data visualization, clarity, and productivity.</p>
              <div class="project-links">
                <a href="#">Live Demo</a>
                <a href="#">Source Code</a>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="section-head">
          <h2>Let’s Work Together</h2>
          <p>Have a project in mind? I’d love to hear about it.</p>
        </div>

        <div class="contact-wrap">
          <div class="contact-card">
            <p>
              I’m available for freelance work, collaborations, and full-time opportunities.
              Reach out and let’s build something great together.
            </p>

            <div class="contact-list">
              <div class="contact-item">
                <div class="contact-icon">E</div>
                <div><strong>Email</strong><br />you@example.com</div>
              </div>

              <div class="contact-item">
                <div class="contact-icon">L</div>
                <div><strong>Location</strong><br />New York, USA</div>
              </div>

              <div class="contact-item">
                <div class="contact-icon">G</div>
                <div><strong>GitHub</strong><br />github.com/yourusername</div>
              </div>
            </div>
          </div>

          <div class="contact-card">
            <form>
              <input type="text" placeholder="Your Name" aria-label="Your Name" />
              <input type="email" placeholder="Your Email" aria-label="Your Email" />
              <input type="text" placeholder="Subject" aria-label="Subject" />
              <textarea placeholder="Your Message" aria-label="Your Message"></textarea>
              <button class="btn btn-primary" type="submit">Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      © <span id="year"></span> Your Name. All rights reserved.
    </div>
  </footer>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
If you want, I can also give you:

a version with a dark/light theme toggle
a version using only HTML + CSS (no JavaScript)
a more modern portfolio with animations
a portfolio tailored to your name, profession, and projects
