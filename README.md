<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Giles Mwa — Portfolio</title>
  <meta name="description" content="Portfolio of Giles Mwa: computer science projects in blockchain, AI/ML, mobile, and backend." />
  <meta name="author" content="Giles Mwa" />
  <meta name="color-scheme" content="light dark" />
  <style>
    /* --------- Reset & base --------- */
    *, *::before, *::after { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { margin: 0; font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, sans-serif; line-height: 1.6; }

    :root {
      --bg: #ffffff;
      --text: #111827; /* slate-900 */
      --muted: #4b5563; /* gray-600 */
      --card: #f8fafc; /* slate-50 */
      --border: #e5e7eb; /* gray-200 */
      --brand: #2563eb; /* blue-600 */
      --brand-weak: #dbeafe; /* blue-100 */
    }
    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #0b1020;
        --text: #e5e7eb;
        --muted: #94a3b8;
        --card: #0f172a;
        --border: #1f2937;
        --brand: #60a5fa;
        --brand-weak: #0b294f;
      }
    }
    :root.theme-light {
      --bg: #ffffff; --text: #111827; --muted: #4b5563; --card: #f8fafc; --border: #e5e7eb; --brand: #2563eb; --brand-weak: #dbeafe;
    }
    :root.theme-dark {
      --bg: #0b1020; --text: #e5e7eb; --muted: #94a3b8; --card: #0f172a; --border: #1f2937; --brand: #60a5fa; --brand-weak: #0b294f;
    }

    body { background: radial-gradient(1200px 600px at 80% -10%, var(--brand-weak), transparent 40%) , var(--bg); color: var(--text); }

    a { color: var(--brand); text-decoration: none; }
    a:hover { text-decoration: underline; }

    /* Layout */
    .container { width: min(1100px, 92%); margin: 0 auto; }
    header { position: sticky; top: 0; backdrop-filter: saturate(180%) blur(6px); background: color-mix(in hsl, var(--bg) 75%, transparent); border-bottom: 1px solid var(--border); z-index: 50; }
    .nav { display: flex; align-items: center; justify-content: space-between; padding: 0.8rem 0; }
    .nav a.brand { font-weight: 700; letter-spacing: 0.2px; }
    .nav ul { list-style: none; display: flex; gap: 1rem; margin: 0; padding: 0; }
    .btn { display: inline-flex; align-items: center; gap: .5rem; padding: .6rem .9rem; border: 1px solid var(--border); border-radius: 999px; background: var(--card); color: var(--text); text-decoration: none; font-weight: 600; }
    .btn:hover { box-shadow: 0 2px 12px color-mix(in srgb, var(--brand) 15%, transparent); text-decoration: none; }

    /* Hero */
    .hero { display: grid; grid-template-columns: 1.2fr 1fr; gap: 2rem; align-items: center; padding: 3.5rem 0 2rem; }
    .hero h1 { font-size: clamp(1.8rem, 2.6vw + 1rem, 3rem); line-height: 1.2; margin: 0 0 .5rem; }
    .hero p.lead { color: var(--muted); font-size: 1.05rem; }
    .chip { display: inline-flex; align-items: center; gap: .5rem; padding: .35rem .6rem; background: var(--card); border: 1px solid var(--border); border-radius: 999px; font-size: .88rem; }
    .chip + .chip { margin-left: .5rem; }

    .card { background: var(--card); border: 1px solid var(--border); border-radius: 16px; padding: 1rem; }

    /* Sections */
    section { padding: 2.5rem 0; }
    section h2 { font-size: 1.6rem; margin: 0 0 1rem; }
    .grid { display: grid; gap: 1rem; }
    .grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
    .grid-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }

    /* Projects */
    .filters { display:flex; flex-wrap: wrap; gap:.5rem; margin-bottom: .75rem; }
    .filter { padding:.45rem .75rem; border: 1px solid var(--border); border-radius: 999px; background: transparent; color: var(--text); cursor: pointer; }
    .filter.active { background: var(--brand); border-color: var(--brand); color: white; }

    .project { display:flex; flex-direction: column; gap:.6rem; }
    .project h3 { margin:.2rem 0 0; font-size:1.1rem; }
    .tags { display:flex; flex-wrap:wrap; gap:.35rem; }
    .tag { font-size:.78rem; padding:.2rem .5rem; border:1px solid var(--border); border-radius:999px; color: var(--muted); }

    /* Resume & Contact */
    .list { list-style: none; padding: 0; margin: 0; display: grid; gap: .75rem; }
    .list li { padding: .75rem; border: 1px solid var(--border); border-radius: 12px; }

    footer { border-top: 1px solid var(--border); padding: 2rem 0; color: var(--muted); font-size: .95rem; }

    /* Responsive */
    @media (max-width: 900px) {
      .hero { grid-template-columns: 1fr; }
      .grid-3 { grid-template-columns: 1fr; }
      .grid-2 { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <a class="brand" href="#home">Giles Mwa</a>
      <nav aria-label="Primary">
        <ul>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#experience">Experience</a></li>
          <li><a href="#education">Education</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><button id="themeToggle" class="btn" type="button" aria-label="Toggle theme">🌓 Theme</button></li>
        </ul>
      </nav>
    </div>
  </header>

  <main id="home" class="container">
    <section class="hero">
      <div>
        <h1>Computer Science Portfolio</h1>
        <p class="lead">Aspiring Tech Consultant with hands-on projects across <strong>blockchain</strong>, <strong>AI/ML</strong>, <strong>mobile (Flutter)</strong>, and <strong>backend APIs</strong>. Focused on building secure, user-centric systems and measurable outcomes.</p>
        <div style="margin:1rem 0 1.2rem;">
          <span class="chip">📍 Based in the UK</span>
          <span class="chip">🎯 Tech Consulting track</span>
          <span class="chip">🔒 Security-first mindset</span>
        </div>
        <div style="display:flex; gap:.6rem; flex-wrap: wrap;">
          <a class="btn" href="#projects">View Projects</a>
          <a class="btn" href="./Giles-Mwa-CV.pdf" download>⬇️ Download CV</a>
          <a class="btn" href="https://github.com/your-github" target="_blank" rel="noopener">GitHub</a>
          <a class="btn" href="https://www.linkedin.com/in/your-linkedin" target="_blank" rel="noopener">LinkedIn</a>
        </div>
      </div>
      <div class="card" aria-hidden="true">
        <svg viewBox="0 0 600 400" style="width:100%; height:auto; display:block; border-radius:12px;" role="img" aria-label="Decorative graphic">
          <defs>
            <linearGradient id="g1" x1="0" x2="1">
              <stop offset="0%" stop-color="currentColor" stop-opacity="0.1" />
              <stop offset="100%" stop-color="currentColor" stop-opacity="0.3" />
            </linearGradient>
          </defs>
          <rect x="0" y="0" width="600" height="400" fill="none" stroke="currentColor" opacity=".15" />
          <g transform="translate(40,40)">
            <rect x="0" y="0" width="520" height="160" fill="url(#g1)" stroke="currentColor" opacity=".3" rx="12" />
            <text x="20" y="40" fill="currentColor" opacity=".9" font-size="20" font-weight="700">Featured Stack</text>
            <text x="20" y="75" fill="currentColor" opacity=".8" font-size="14">Solidity · Hardhat · Flutter · Dart · Java · JAX‑RS · MongoDB · Python</text>
            <text x="20" y="105" fill="currentColor" opacity=".8" font-size="14">OpenCV · PyTorch · JWT · Docker · Hyperledger · GitHub Actions</text>
          </g>
          <g transform="translate(40,220)">
            <rect x="0" y="0" width="520" height="140" fill="none" stroke="currentColor" opacity=".2" rx="12" />
            <text x="20" y="40" fill="currentColor" opacity=".9" font-size="18" font-weight="700">What I like building</text>
            <text x="20" y="80" fill="currentColor" opacity=".8" font-size="14">Secure data sharing · Smart‑contract systems · Real‑time mobile UX · Practical AI</text>
          </g>
        </svg>
      </div>
    </section>

    <section id="projects" aria-labelledby="projects-title">
      <h2 id="projects-title">Projects</h2>
      <div class="filters" role="toolbar" aria-label="Project filters">
        <button class="filter active" data-filter="all">All</button>
        <button class="filter" data-filter="blockchain">Blockchain</button>
        <button class="filter" data-filter="mobile">Mobile</button>
        <button class="filter" data-filter="aiml">AI/ML</button>
        <button class="filter" data-filter="backend">Backend</button>
      </div>

      <div class="grid grid-3" id="projectGrid">
        <!-- Project 1 -->
        <article class="card project" data-tags="blockchain backend security">
          <h3>Secure Data‑Sharing Platform (Blockchain)</h3>
          <p>General secure data‑sharing platform using <strong>Ethereum</strong> smart contracts (Hardhat). Implements access tokens and auditability with on‑chain events.</p>
          <div class="tags">
            <span class="tag">Solidity</span>
            <span class="tag">Hardhat</span>
            <span class="tag">JWT</span>
            <span class="tag">Docker</span>
          </div>
          <p>
            <a href="https://github.com/your-github/secure-data-sharing" target="_blank" rel="noopener">Repo</a>
            · <a href="#" aria-disabled="true" onclick="return false;">Live (coming soon)</a>
          </p>
        </article>

        <!-- Project 2 -->
        <article class="card project" data-tags="blockchain backend testing">
          <h3>ERC‑721 DataAccessToken + Tests</h3>
          <p>Mint/burn/transfer flows, token metadata, and ownership queries with <strong>Hardhat + Chai</strong> test suite for rigorous validation.</p>
          <div class="tags">
            <span class="tag">Solidity</span>
            <span class="tag">Hardhat</span>
            <span class="tag">Chai</span>
          </div>
          <p><a href="https://github.com/your-github/data-access-token" target="_blank" rel="noopener">Repo</a></p>
        </article>

        <!-- Project 3 -->
        <article class="card project" data-tags="mobile iot security">
          <h3>Flutter QR Token Access</h3>
          <p>Time‑limited QR tokens generated in a <strong>Flutter</strong> app to grant temporary access to external hardware; includes token refresh and invalidation.</p>
          <div class="tags">
            <span class="tag">Flutter</span>
            <span class="tag">Dart</span>
            <span class="tag">JWT</span>
          </div>
          <p><a href="https://github.com/your-github/flutter-qr-token" target="_blank" rel="noopener">Repo</a></p>
        </article>

        <!-- Project 4 -->
        <article class="card project" data-tags="aiml cv chatbot">
          <h3>AI Chatbot: Badge & Face Classifier</h3>
          <p>CNN‑based image classification for football team badges and player faces; integrates with a chatbot pipeline for fan queries.</p>
          <div class="tags">
            <span class="tag">Python</span>
            <span class="tag">PyTorch</span>
            <span class="tag">OpenCV</span>
          </div>
          <p><a href="https://github.com/your-github/cnn-badge-face-bot" target="_blank" rel="noopener">Repo</a></p>
        </article>

        <!-- Project 5 -->
        <article class="card project" data-tags="backend api java">
          <h3>RESTful API with JAX‑RS & MongoDB</h3>
          <p>CRUD + auth API in Java using JAX‑RS and Gson, backed by MongoDB; includes CI and containerized dev environment.</p>
          <div class="tags">
            <span class="tag">Java</span>
            <span class="tag">JAX‑RS</span>
            <span class="tag">MongoDB</span>
            <span class="tag">Docker</span>
          </div>
          <p><a href="https://github.com/your-github/jaxrs-mongo-api" target="_blank" rel="noopener">Repo</a></p>
        </article>

        <!-- Project 6 -->
        <article class="card project" data-tags="blockchain research hyperledger">
          <h3>Hyperledger Fabric Exploration</h3>
          <p>Dockerized local network and sample chaincode to evaluate permissioned ledgers for enterprise data sharing.</p>
          <div class="tags">
            <span class="tag">Hyperledger</span>
            <span class="tag">Docker</span>
            <span class="tag">Go/JS</span>
          </div>
          <p><a href="https://github.com/your-github/fabric-notes" target="_blank" rel="noopener">Notes/Repo</a></p>
        </article>
      </div>
    </section>

    <section id="skills">
      <h2>Skills</h2>
      <div class="grid grid-3">
        <div class="card">
          <h3>Languages & Frameworks</h3>
          <ul class="list">
            <li>Solidity, Java, Dart, Python, JavaScript</li>
            <li>Hardhat, JAX‑RS, Flutter, PyTorch, OpenCV</li>
            <li>REST APIs, JWT, OAuth</li>
          </ul>
        </div>
        <div class="card">
          <h3>Systems & Tools</h3>
          <ul class="list">
            <li>Docker, Git/GitHub, GitHub Actions</li>
            <li>MongoDB, basic SQL</li>
            <li>CI/CD, testing (Chai/Jest)</li>
          </ul>
        </div>
        <div class="card">
          <h3>Professional</h3>
          <ul class="list">
            <li>Leadership & stakeholder comms</li>
            <li>Requirements gathering & documentation</li>
            <li>Security-first design</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="experience">
      <h2>Experience</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Retail Team Leader (Kiosk Supervisor) — Nottingham Forest FC</h3>
          <p>Led up to 10 staff and oversaw match‑day kiosk operations: stock & cash control, queue reduction, and customer experience—regularly surpassing sales targets.</p>
          <ul class="list">
            <li>Streamlined payment flow & scheduling to cut queues</li>
            <li>Trusted with training and closing responsibilities</li>
          </ul>
        </div>
        <div class="card">
          <h3>Academic & Project Roles</h3>
          <p>Team projects focused on secure data sharing, mobile UX, and ML prototypes; roles spanned full‑stack development, testing, and deployment.</p>
          <ul class="list">
            <li>Smart‑contract architecture & test coverage</li>
            <li>Flutter prototyping and device access control</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="education">
      <h2>Education</h2>
      <div class="card">
        <p><strong>BSc (Hons) Computer Science</strong> — University (in progress). Diploma of Higher Education attained.</p>
        <p>Final Year Project: Blockchain‑based data‑sharing platform (submitted April 2025).</p>
      </div>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <div class="grid grid-2">
        <div class="card">
          <p>Email: <a href="mailto:hello@gilesmwa.dev">hello@gilesmwa.dev</a></p>
          <p>GitHub: <a href="https://github.com/your-github" target="_blank" rel="noopener">@your-github</a></p>
          <p>LinkedIn: <a href="https://www.linkedin.com/in/your-linkedin" target="_blank" rel="noopener">/in/your-linkedin</a></p>
        </div>
        <form class="card" onsubmit="event.preventDefault(); alert('Thanks! I\'ll be in touch.');">
          <label for="msg" style="display:block; margin-bottom:.35rem;">Quick message</label>
          <textarea id="msg" rows="4" style="width:100%; padding:.6rem; border:1px solid var(--border); border-radius:8px; background:transparent; color:inherit" placeholder="Say hi or propose a collaboration…"></textarea>
          <div style="margin-top:.6rem; display:flex; gap:.5rem;">
            <button class="btn" type="submit">Send</button>
            <a class="btn" href="mailto:hello@gilesmwa.dev?subject=Hello%20Giles">Open email</a>
          </div>
        </form>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div style="display:flex; align-items:center; justify-content:space-between; gap:1rem; flex-wrap:wrap;">
        <p>© <span id="year"></span> Giles Mwa. Built with simple HTML, CSS & JS. Deployed on GitHub Pages.</p>
        <a class="btn" href="#home" aria-label="Back to top">↑ Back to top</a>
      </div>
    </div>
  </footer>

  <script>
    // Theme toggle with localStorage
    const root = document.documentElement;
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme === 'light' || savedTheme === 'dark') {
      root.classList.add('theme-' + savedTheme);
    }
    document.getElementById('themeToggle').addEventListener('click', () => {
      const isDark = root.classList.toggle('theme-dark');
      if (!isDark) {
        root.classList.add('theme-light');
        localStorage.setItem('theme', 'light');
        root.classList.remove('theme-dark');
      } else {
        localStorage.setItem('theme', 'dark');
        root.classList.remove('theme-light');
      }
    });

    // Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Project filtering
    const filters = document.querySelectorAll('.filter');
    const projects = document.querySelectorAll('.project');
    filters.forEach(btn => btn.addEventListener('click', () => {
      filters.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      const key = btn.dataset.filter;
      projects.forEach(card => {
        if (key === 'all') { card.style.display = ''; return; }
        const tags = card.dataset.tags.toLowerCase();
        card.style.display = tags.includes(key) ? '' : 'none';
      });
    }));
  </script>
</body>
</html>
