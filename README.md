<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Best Website — Modern Single File Demo</title>
  <meta name="description" content="A polished, responsive single-file website (HTML/CSS/JS) with accessibility, animations, dark mode, contact form validation, and small JS utilities." />
  <style>
    :root{
      --bg:#0f1724; /* dark blue-gray */
      --card:#0b1220;
      --muted:#94a3b8;
      --accent:#06b6d4;
      --glass: rgba(255,255,255,0.04);
      --radius:14px;
      color-scheme: dark;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#071120 0%,var(--bg) 60%);color:#e6eef8}
    a{color:var(--accent);text-decoration:none}
    header{backdrop-filter: blur(6px);position:sticky;top:12px;margin:12px;display:flex;align-items:center;justify-content:space-between;padding:10px 16px;border-radius:14px;background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));box-shadow:0 6px 20px rgba(2,6,23,0.6)}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:44px;height:44px;border-radius:10px;display:grid;place-items:center;background:linear-gradient(135deg,var(--accent),#7c3aed);font-weight:800}
    nav{display:flex;gap:12px;align-items:center}
    nav a{padding:8px 10px;border-radius:10px;font-weight:600;color:var(--muted)}
    nav a:hover{color:#fff;background:rgba(255,255,255,0.03)}
    .hero{display:grid;grid-template-columns:1fr 420px;gap:36px;align-items:center;padding:48px;max-width:1200px;margin:40px auto}
    .hero-card{background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));padding:28px;border-radius:18px;box-shadow:0 10px 40px rgba(2,6,23,0.6)}
    h1{font-size:clamp(28px,4.6vw,44px);margin:0 0 12px}
    p.lead{color:var(--muted);line-height:1.6;margin:0 0 20px}
    .cta{display:flex;gap:12px}
    .btn{padding:12px 16px;border-radius:12px;font-weight:700;border:0;cursor:pointer}
    .btn-primary{background:linear-gradient(90deg,var(--accent),#7c3aed);color:#021124}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.04);color:var(--muted)}
    .features{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:18px}
    .card{background:var(--card);padding:14px;border-radius:12px}
    .visual{border-radius:12px;overflow:hidden;height:100%;display:flex;align-items:center;justify-content:center;background:linear-gradient(180deg,rgba(255,255,255,0.01),rgba(255,255,255,0.02));min-height:240px}
    /* Testimonials / carousel */
    .carousel{position:relative;padding:18px}
    .slides{display:flex;gap:12px;transition:transform .45s cubic-bezier(.22,.9,.32,1)}
    .testimonial{min-width:320px;background:linear-gradient(180deg,rgba(255,255,255,0.015),rgba(255,255,255,0.01));padding:18px;border-radius:12px}
    footer{max-width:1200px;margin:40px auto;padding:20px;color:var(--muted)}
    /* responsive */
    @media (max-width:900px){
      .hero{grid-template-columns:1fr;gap:20px;padding:20px}
      .features{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width:560px){
      nav{display:none}
      .features{grid-template-columns:1fr}
      header{padding:12px}
    }
    /* subtle focus ring for keyboard nav */
    :focus{outline:2px solid rgba(6,182,212,0.18);outline-offset:3px}
    /* small helpers */
    .muted{color:var(--muted)}
    .pill{display:inline-block;padding:6px 10px;border-radius:999px;background:var(--glass);font-weight:700}
  </style>
</head>
<body>
  <header role="banner">
    <div class="brand">
      <div class="logo" aria-hidden>BW</div>
      <div>
        <div style="font-weight:800">Best Website</div>
        <div class="muted" style="font-size:12px">Fast — Accessible — Modern</div>
      </div>
    </div><nav role="navigation" aria-label="Primary navigation">
  <a href="#features">Features</a>
  <a href="#testimonials">Testimonials</a>
  <a href="#contact">Contact</a>
  <button id="themeToggle" class="btn btn-ghost" aria-pressed="false" title="Toggle dark/light">Toggle</button>
</nav>

  </header>  <main>
    <section class="hero" aria-labelledby="hero-title">
      <div class="hero-card">
        <h1 id="hero-title">A fast, accessible website starter — built with JavaScript</h1>
        <p class="lead">This single-file demo showcases modern UI patterns: smooth navigation, accessible controls, form validation, a tiny carousel, lazy-loading images, and a color theme toggle — all without external libraries.</p>
        <div class="cta">
          <button id="scrollFeatures" class="btn btn-primary">See Features</button>
          <a href="#contact" class="btn btn-ghost">Get in Touch</a>
        </div><div class="features" style="margin-top:20px">
      <div class="card">
        <strong>Performance</strong>
        <div class="muted" style="font-size:13px;margin-top:6px">Tiny JS, lazy images, and minimal layout shifts.</div>
      </div>
      <div class="card">
        <strong>Accessibility</strong>
        <div class="muted" style="font-size:13px;margin-top:6px">Keyboard-first, semantic markup, and proper ARIA where needed.</div>
      </div>
      <div class="card">
        <strong>Progressive</strong>
        <div class="muted" style="font-size:13px;margin-top:6px">Works on low-end devices and scales beautifully.</div>
      </div>
    </div>
  </div>

  <aside class="visual" aria-hidden>
    <!-- simple animated SVG / placeholder -->
    <svg width="320" height="220" viewBox="0 0 320 220" fill="none" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="illustration">
      <defs>
        <linearGradient id="g" x1="0" x2="1">
          <stop offset="0" stop-color="#06b6d4" stop-opacity="0.95"/>
          <stop offset="1" stop-color="#7c3aed" stop-opacity="0.95"/>
        </linearGradient>
      </defs>
      <rect x="8" y="8" rx="16" width="304" height="204" fill="url(#g)"></rect>
      <g transform="translate(26,30)" fill="#021124" opacity="0.95">
        <rect x="0" y="0" width="260" height="140" rx="12" fill="#021124"/>
      </g>
    </svg>
  </aside>
</section>

<section id="features" class="hero-card" style="max-width:1200px;margin:12px auto;padding:28px;border-radius:16px">
  <h2>Feature highlights</h2>
  <ul>
    <li>Responsive layout + CSS-first theming</li>
    <li>Tiny modular JavaScript (no external bundles)</li>
    <li>Contact form with client-side validation and accessibility</li>
    <li>Testimonials carousel with keyboard controls</li>
    <li>Progressive enhancement: works without JS for core content</li>
  </ul>
</section>

<section id="testimonials" class="hero-card" style="max-width:1200px;margin:24px auto;padding:18px">
  <h2>What people say</h2>
  <div class="carousel" aria-roledescription="carousel" aria-label="Testimonials">
    <div class="slides" id="slides">
      <figure class="testimonial" tabindex="0">
        <blockquote>"Blazingly fast and easy to extend — shipped within a day."</blockquote>
        <figcaption class="muted">— A. Developer, Frontend</figcaption>
      </figure>
      <figure class="testimonial" tabindex="0">
        <blockquote>"Great accessible defaults and the form validation saved time."</blockquote>
        <figcaption class="muted">— S. Product Manager</figcaption>
      </figure>
      <figure class="testimonial" tabindex="0">
        <blockquote>"Lovely visuals and tiny JS footprint."</blockquote>
        <figcaption class="muted">— K. Designer</figcaption>
      </figure>
    </div>
  </div>
  <div style="display:flex;gap:8px;align-items:center;margin-top:12px">
    <button id="prev" class="btn btn-ghost" aria-label="Previous testimonial">◀</button>
    <button id="next" class="btn btn-ghost" aria-label="Next testimonial">▶</button>
    <div class="muted" style="margin-left:auto;font-size:13px">Use arrow keys ← → when focused inside testimonials</div>
  </div>
</section>

<section id="contact" class="hero-card" style="max-width:900px;margin:24px auto;padding:20px">
  <h2>Contact — try the form</h2>
  <form id="contactForm" novalidate>
    <label for="name">Name</label><br>
    <input id="name" name="name" required placeholder="Your name" style="width:100%;padding:10px;margin:6px 0;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit" />
    <label for="email">Email</label><br>
    <input id="email" name="email" type="email" required placeholder="you@example.com" style="width:100%;padding:10px;margin:6px 0;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit" />
    <label for="message">Message</label><br>
    <textarea id="message" name="message" rows="5" required placeholder="Tell us what you need" style="width:100%;padding:10px;margin:6px 0;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit"></textarea>
    <div style="display:flex;gap:10px;align-items:center;margin-top:10px">
      <button type="submit" class="btn btn-primary">Send</button>
      <div id="formStatus" class="muted" aria-live="polite"></div>
    </div>
  </form>
</section>

  </main>  <footer>
    <div style="display:flex;justify-content:space-between;align-items:center">
      <div class="muted">© Best Website — Built with small JS • Accessible • Lightweight</div>
      <div class="muted">Made with ♥</div>
    </div>
  </footer>  <script>
    /* Small, focused JS for interactivity and progressive enhancement */
    (function(){
      // Utilities
      const $ = sel => document.querySelector(sel);
      const $$ = sel => Array.from(document.querySelectorAll(sel));

      // Smooth scroll to features
      $('#scrollFeatures').addEventListener('click', e => {
        e.preventDefault();
        document.querySelector('#features').scrollIntoView({behavior:'smooth', block:'start'});
      });

      // Theme toggle (persists in localStorage)
      const themeToggle = $('#themeToggle');
      const applyTheme = (theme) => {
        if(theme === 'light'){
          document.documentElement.style.setProperty('--bg','#f8fafc');
          document.documentElement.style.setProperty('--card','#ffffff');
          document.documentElement.style.setProperty('--muted','#475569');
          document.documentElement.style.setProperty('--accent','#2563eb');
          document.documentElement.style.setProperty('color-scheme','light');
          themeToggle.textContent = 'Dark';
          themeToggle.setAttribute('aria-pressed','true');
        } else {
          document.documentElement.style.removeProperty('--bg');
          document.documentElement.style.removeProperty('--card');
          document.documentElement.style.removeProperty('--muted');
          document.documentElement.style.removeProperty('--accent');
          document.documentElement.style.setProperty('color-scheme','dark');
          themeToggle.textContent = 'Light';
          themeToggle.setAttribute('aria-pressed','false');
        }
      };
      const saved = localStorage.getItem('bw:theme');
      applyTheme(saved || 'dark');
      themeToggle.addEventListener('click', () => {
        const next = (localStorage.getItem('bw:theme') === 'light') ? 'dark' : 'light';
        localStorage.setItem('bw:theme', next);
        applyTheme(next);
      });

      // Tiny carousel logic
      const slides = $('#slides');
      let index = 0;
      const total = slides.children.length;
      const updateCarousel = () => {
        const w = slides.children[0].getBoundingClientRect().width + 12; // card width + gap
        slides.style.transform = `translateX(${ -index * w }px)`;
      };
      $('#prev').addEventListener('click', ()=>{ index = (index - 1 + total) % total; updateCarousel(); });
      $('#next').addEventListener('click', ()=>{ index = (index + 1) % total; updateCarousel(); });
      // keyboard support for carousel
      $('#slides').addEventListener('keydown', (e) => {
        if(e.key === 'ArrowLeft') { index = (index -1 + total) % total; updateCarousel(); }
        if(e.key === 'ArrowRight') { index = (index +1) % total; updateCarousel(); }
      });
      // handle resize
      window.addEventListener('resize', () => requestAnimationFrame(updateCarousel));
      // initial layout
      requestAnimationFrame(updateCarousel);

      // Contact form validation & fake submit
      const form = $('#contactForm');
      const status = $('#formStatus');
      form.addEventListener('submit', (e) => {
        e.preventDefault();
        const fm = new FormData(form);
        const name = fm.get('name').trim();
        const email = fm.get('email').trim();
        const message = fm.get('message').trim();
        if(!name || !email || !message){
          status.textContent = 'Please fill all required fields.';
          return;
        }
        // simple email pattern
        const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        if(!emailPattern.test(email)){
          status.textContent = 'Enter a valid email address.';
          return;
        }
        status.textContent = 'Sending...';
        // Simulate network delay and graceful success message
        setTimeout(()=>{
          status.textContent = 'Thanks! Your message was sent (demo).';
          form.reset();
        },700);
      });

      // Small accessibility helpers: add visible focus when using keyboard
      (function keyboardFocusHelper(){
        let usingKeyboard = false;
        window.addEventListener('keydown', e => { if(e.key === 'Tab') { usingKeyboard = true; document.documentElement.classList.add('show-focus'); }});
        window.addEventListener('mousedown', ()=>{ if(usingKeyboard) { usingKeyboard = false; document.documentElement.classList.remove('show-focus'); }});
      })();

      // Lazy-load images (progressive enhancement)
      if('loading' in HTMLImageElement.prototype){
        // native lazy loading supported — nothing needed
      } else {
        // fallback: simple intersection observer for images with data-src
        const imgObserver = new IntersectionObserver((entries, obs) => {
          entries.forEach(e => {
            if(e.isIntersecting){
              const img = e.target;
              img.src = img.dataset.src;
              obs.unobserve(img);
            }
          });
        },{rootMargin:'200px'});
        $$('img[data-src]').forEach(img => imgObserver.observe(img));
      }

      // Small progressive enhancement: ensure core content visible if JS disabled
      document.documentElement.classList.remove('no-js');

      // Performance note: keep JS small and defer non-critical bits
    })();
  </script></body>
</html>
