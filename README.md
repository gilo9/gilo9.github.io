<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Giles Mwa — Portfolio</title>
  <meta name="description" content="Portfolio of Giles Mwa: blockchain, AI/ML, mobile, and backend development projects.">
  <meta name="author" content="Giles Mwa" />
  <meta name="color-scheme" content="light dark" />
  <style>
    /* Keep your original CSS — no major changes needed */
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
          <li><button id="themeToggle" class="btn" type="button">🌓 Theme</button></li>
        </ul>
      </nav>
    </div>
  </header>

  <main id="home" class="container">
    <!-- Hero -->
    <section class="hero">
      <div>
        <h1>Hi, I’m Giles Mwa 👋</h1>
        <p class="lead">Computer Science graduate with strong hands-on experience in <strong>blockchain</strong>, <strong>secure systems</strong>, and <strong>software development</strong>. I’m passionate about solving real-world problems through secure, scalable, and user-centric tech solutions.</p>
        <div style="margin:1rem 0 1.2rem;">
          <span class="chip">📍 London, UK</span>
          <span class="chip">🎯 Tech Consulting Track</span>
          <span class="chip">🔒 Security-first mindset</span>
        </div>
        <div style="display:flex; gap:.6rem; flex-wrap:wrap;">
          <a class="btn" href="#projects">View Projects</a>
          <a class="btn" href="./Giles-Mwa-CV.pdf" download>⬇️ Download CV</a>
          <a class="btn" href="https://github.com/gilesmwa" target="_blank" rel="noopener">GitHub</a>
          <a class="btn" href="https://www.linkedin.com/in/gilesmwa" target="_blank" rel="noopener">LinkedIn</a>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects">
      <h2>Key Projects</h2>
      <div class="grid grid-3">
        <article class="card project" data-tags="blockchain security frontend">
          <h3>Secure File Sharing Dapp</h3>
          <p>Built a decentralized file-sharing platform using Ethereum smart contracts (<strong>Solidity</strong>, <strong>Hardhat</strong>) and <strong>IPFS</strong>. Token-based access control with a React frontend and Node.js backend.</p>
          <div class="tags">
            <span class="tag">Solidity</span><span class="tag">IPFS</span><span class="tag">React</span><span class="tag">Node.js</span>
          </div>
          <p><a href="https://github.com/gilesmwa/secure-file-sharing" target="_blank">Repo</a></p>
        </article>
        <article class="card project" data-tags="ai ml chatbot">
          <h3>AI Chatbot with Image Classifier</h3>
          <p>Developed a football chatbot identifying club logos and player faces using CNNs in Python. Integrated into a web interface with a custom-trained dataset.</p>
          <div class="tags">
            <span class="tag">Python</span><span class="tag">PyTorch</span><span class="tag">OpenCV</span>
          </div>
        </article>
        <article class="card project" data-tags="mobile flutter security">
          <h3>Authentication App</h3>
          <p>Flutter-based app for secure hardware access with time-based tokens, real-time expiry logic, and Firebase integration.</p>
          <div class="tags"><span class="tag">Flutter</span><span class="tag">Dart</span><span class="tag">Firebase</span></div>
        </article>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills">
      <h2>Skills</h2>
      <div class="grid grid-3">
        <div class="card"><h3>Languages</h3><ul class="list"><li>Python, Java, JavaScript, C++, Dart, Solidity</li></ul></div>
        <div class="card"><h3>Frameworks/Tools</h3><ul class="list"><li>React, Flutter, Node.js, Hardhat, MongoDB, Docker</li></ul></div>
        <div class="card"><h3>Concepts</h3><ul class="list"><li>Blockchain, Smart Contracts, Web3, REST APIs, OOP, DSA</li></ul></div>
      </div>
    </section>

    <!-- Experience -->
    <section id="experience">
      <h2>Experience</h2>
      <div class="grid grid-2">
        <div class="card">
          <h3>Retail Team Leader — Nottingham Forest FC</h3>
          <p>Supervised match-day staff, optimized payment flows, and consistently surpassed sales targets.</p>
        </div>
        <div class="card">
          <h3>Catering & Events Staff — Constellation</h3>
          <p>Delivered high-standard service at major stadiums, trained junior staff, and ensured compliance.</p>
        </div>
        <div class="card">
          <h3>Engineering Intern — SPIE UK</h3>
          <p>Debugged building maintenance algorithms and contributed to software development teams.</p>
        </div>
      </div>
    </section>

    <!-- Education -->
    <section id="education">
      <h2>Education</h2>
      <div class="card">
        <p><strong>BSc (Hons) Computer Science</strong>, Nottingham Trent University — 2:1 Honours (2024–2025)</p>
        <p><strong>Diploma of Higher Education</strong>, University of Leicester (2021–2024)</p>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <h2>Contact</h2>
      <div class="grid grid-2">
        <div class="card">
          <p>Email: <a href="mailto:gilesmwa@gmail.com">gilesmwa@gmail.com</a></p>
          <p>GitHub: <a href="https://github.com/gilesmwa">@gilesmwa</a></p>
          <p>LinkedIn: <a href="https://www.linkedin.com/in/gilesmwa">/in/gilesmwa</a></p>
        </div>
      </div>
    </section>
  </main>
</body>
</html>
