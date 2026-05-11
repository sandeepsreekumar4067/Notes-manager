# 📚 ClassNotes

A static note-sharing website for your class. Upload PDFs to GitHub and the site automatically reads your folder structure and displays everything — organized by subject and professor. No backend, no database, no cost.

Built with **Vue.js** · Hosted on **GitHub Pages** · Powered by the **GitHub Contents API**

---

## ✨ Features

- Zero backend — just one `index.html` file
- Auto-discovers subjects, professors, and PDFs from your repo folders
- Live search across subjects, professors, and note titles
- Direct PDF download via raw GitHub links
- Lazy loading — notes are fetched only when you click a subject
- Fully responsive, works on mobile

---

## 📁 Folder Structure

Your repo should look like this:

```
your-repo/
├── index.html
├── README.md
└── Notes/
    ├── Data Structures/
    │   ├── Dr. Ramesh Kumar/
    │   │   ├── Unit 1 - Arrays and Linked Lists.pdf
    │   │   └── Unit 2 - Stacks and Queues.pdf
    │   └── Prof. Anitha Nair/
    │       └── Module 1 - Introduction.pdf
    ├── Operating Systems/
    │   └── Dr. Suresh Pillai/
    │       ├── Process Management.pdf
    │       └── Memory Management.pdf
    └── Computer Networks/
        └── Dr. Meera Krishnan/
            └── OSI Model.pdf
```

> PDF filenames become the note titles on the site. Hyphens and underscores are replaced with spaces automatically.

---

## 🚀 Setup

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
```

### 2. Edit the config in `index.html`

Find the config block near the bottom of `index.html` and fill in your details:

```js
const GITHUB_USER   = "your_github_username";
const GITHUB_REPO   = "your_repo_name";
const GITHUB_BRANCH = "main";
const NOTES_ROOT    = "Notes";

const SEMESTER      = "Semester 4";
const DEPARTMENT    = "B.Tech CSE";
```

### 3. Add your notes

Create folders following the `Notes/Subject/Professor/` structure and drop your PDFs in.

### 4. Push to GitHub

```bash
git add .
git commit -m "initial setup"
git push
```

### 5. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Set source to your branch (e.g. `main`) and `/ (root)`
3. Click **Save**

Your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO/`

---

## ➕ Adding New Notes

Just drop a PDF in the right folder and push. No code changes needed.

```bash
cp "Lecture 5.pdf" "Notes/Data Structures/Dr. Ramesh Kumar/"
git add .
git commit -m "add DS lecture 5"
git push
```

---

## ⚠️ Requirements

- Repo must be **public** — the GitHub API used here is unauthenticated
- PDFs only — the site filters for `.pdf` files
- Folder depth must be exactly `Notes/Subject/Professor/file.pdf`

---

## 🛠 Tech Stack

- [Vue.js 3](https://vuejs.org/) — loaded via CDN, no build step needed
- [GitHub Contents API](https://docs.github.com/en/rest/repos/contents) — reads folder structure at runtime
- [GitHub Pages](https://pages.github.com/) — free static hosting

---

## 📝 Tips

- **Name PDFs clearly** — `Unit 1 - Linked Lists.pdf` is better than `u1.pdf`
- **Folder names = display names** — whatever you name the subject and professor folders is what shows on the site
- **Search is session-based** — only searches subjects you've already opened in that visit, since notes load lazily
- **Rate limits** — GitHub allows 60 API requests/hour for unauthenticated users. Each subject click uses 2–3 requests, so this won't be an issue for normal use

---

## 📄 License

MIT — free to use, share, and modify.      display: flex; align-items: center; justify-content: space-between;
    }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem; font-weight: 700; color: var(--text); text-decoration: none;
    }
    .nav-logo span { color: var(--accent); }

    .nav-links { display: flex; gap: 2rem; }
    .nav-links a {
      font-size: 0.85rem; color: var(--muted); text-decoration: none;
      transition: color 0.15s;
    }
    .nav-links a:hover { color: var(--text); }
    .nav-links a.active { color: var(--accent); }

    /* Hero */
    .hero {
      padding: 6rem 0 5rem;
      border-bottom: 1px solid var(--border);
    }

    .hero-badge {
      display: inline-flex; align-items: center; gap: 0.5rem;
      background: var(--pill-bg); border: 1px solid var(--pill-border);
      color: var(--accent); font-size: 0.75rem; font-weight: 500;
      padding: 0.3rem 0.9rem; border-radius: 20px;
      margin-bottom: 2rem; letter-spacing: 0.04em; text-transform: uppercase;
    }

    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.4rem, 5vw, 3.8rem);
      font-weight: 700; line-height: 1.1;
      margin-bottom: 1.5rem; max-width: 620px;
    }

    .hero h1 em { color: var(--accent); font-style: normal; }

    .hero p {
      font-size: 1.05rem; color: var(--muted);
      line-height: 1.8; max-width: 540px; margin-bottom: 2.5rem;
    }

    .hero-cta {
      display: inline-flex; align-items: center; gap: 0.6rem;
      background: var(--pill-bg); border: 1px solid var(--pill-border);
      color: var(--accent); font-family: 'DM Sans', sans-serif;
      font-size: 0.88rem; font-weight: 500; padding: 0.7rem 1.4rem;
      border-radius: 8px; text-decoration: none;
      transition: background 0.2s, border-color 0.2s;
    }
    .hero-cta:hover { background: rgba(200,169,110,0.2); border-color: rgba(200,169,110,0.5); }

    /* How it works */
    .section { padding: 5rem 0; border-bottom: 1px solid var(--border); }

    .section-label {
      font-size: 0.7rem; letter-spacing: 0.14em; text-transform: uppercase;
      color: var(--accent); margin-bottom: 1rem;
    }

    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: 2rem; font-weight: 700;
      margin-bottom: 1rem; line-height: 1.2;
    }

    .section-sub {
      font-size: 0.9rem; color: var(--muted);
      line-height: 1.75; max-width: 520px; margin-bottom: 3rem;
    }

    /* Steps */
    .steps { display: flex; flex-direction: column; gap: 0; }

    .step {
      display: grid; grid-template-columns: 56px 1fr;
      gap: 0 1.5rem; position: relative;
    }

    .step:not(:last-child)::before {
      content: ''; position: absolute;
      left: 27px; top: 56px; bottom: 0;
      width: 1px; background: var(--border);
    }

    .step-num-wrap {
      display: flex; flex-direction: column; align-items: center;
      padding-top: 0.2rem;
    }

    .step-num {
      width: 40px; height: 40px; border-radius: 50%;
      border: 1px solid var(--pill-border);
      background: var(--pill-bg);
      display: flex; align-items: center; justify-content: center;
      font-size: 0.82rem; font-weight: 500; color: var(--accent);
      flex-shrink: 0;
    }

    .step-body { padding: 0.1rem 0 3rem; }

    .step-body h3 {
      font-size: 1rem; font-weight: 500; margin-bottom: 0.4rem; color: var(--text);
    }

    .step-body p { font-size: 0.875rem; color: var(--muted); line-height: 1.7; }

    .step-body code {
      display: block; background: var(--surface); border: 1px solid var(--border);
      border-radius: 8px; padding: 0.9rem 1rem; margin-top: 0.75rem;
      font-size: 0.78rem; color: var(--accent); line-height: 1.7;
      font-family: 'Courier New', monospace; white-space: pre;
    }

    /* Architecture */
    .arch-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 1px; background: var(--border);
      border: 1px solid var(--border); border-radius: 12px; overflow: hidden;
    }

    .arch-card {
      background: var(--surface); padding: 1.5rem;
      display: flex; flex-direction: column; gap: 0.75rem;
    }

    .arch-icon {
      font-size: 1.4rem; width: 42px; height: 42px;
      background: var(--pill-bg); border: 1px solid var(--pill-border);
      border-radius: 10px; display: flex; align-items: center; justify-content: center;
    }

    .arch-card h3 { font-size: 0.92rem; font-weight: 500; color: var(--text); }
    .arch-card p { font-size: 0.8rem; color: var(--muted); line-height: 1.65; }

    /* Folder structure */
    .folder-tree {
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 12px; padding: 1.5rem 1.75rem;
      font-family: 'Courier New', monospace; font-size: 0.82rem;
      line-height: 2; color: var(--muted);
    }

    .folder-tree .folder { color: var(--text); }
    .folder-tree .accent { color: var(--accent); }
    .folder-tree .dim { opacity: 0.45; }

    /* FAQ */
    .faq-list { display: flex; flex-direction: column; gap: 0; }

    .faq-item {
      border-bottom: 1px solid var(--border); padding: 1.5rem 0;
    }
    .faq-item:first-child { border-top: 1px solid var(--border); }

    .faq-q {
      font-size: 0.95rem; font-weight: 500; color: var(--text);
      margin-bottom: 0.6rem;
    }

    .faq-a { font-size: 0.86rem; color: var(--muted); line-height: 1.75; }
    .faq-a code {
      font-size: 0.8rem; background: var(--surface2);
      padding: 0.1rem 0.4rem; border-radius: 4px; color: var(--accent);
      font-family: 'Courier New', monospace;
    }

    /* Tech stack */
    .stack-row { display: flex; flex-wrap: wrap; gap: 0.75rem; margin-top: 1.5rem; }

    .stack-chip {
      display: flex; align-items: center; gap: 0.5rem;
      background: var(--surface); border: 1px solid var(--border);
      border-radius: 8px; padding: 0.55rem 1rem;
      font-size: 0.82rem; color: var(--text);
    }

    .stack-chip .dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); }

    /* Footer */
    footer {
      padding: 3rem 0;
      text-align: center;
      font-size: 0.8rem; color: var(--muted);
      line-height: 1.8;
    }

    footer a { color: var(--accent); text-decoration: none; }
    footer a:hover { text-decoration: underline; }

    /* Responsive */
    @media (max-width: 640px) {
      .hero { padding: 4rem 0 3rem; }
      .section { padding: 3.5rem 0; }
      .nav-links { gap: 1.2rem; }
    }
  </style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <a class="nav-logo" href="index.html">Class<span>Notes</span></a>
    <div class="nav-links">
      <a href="index.html">Notes</a>
      <a href="about.html" class="active">About</a>
      <a href="https://github.com/YOUR_USERNAME/YOUR_REPO" target="_blank">GitHub ↗</a>
    </div>
  </div>
</nav>

<div class="wrap">

  <!-- Hero -->
  <section class="hero">
    <div class="hero-badge">📖 Documentation</div>
    <h1>Simple notes sharing,<br/><em>without the complexity.</em></h1>
    <p>ClassNotes is a static website that reads your GitHub folder structure and renders downloadable PDFs — organized by subject and professor. No backend, no database, no login.</p>
    <a class="hero-cta" href="https://github.com/YOUR_USERNAME/YOUR_REPO" target="_blank">View on GitHub ↗</a>
  </section>

  <!-- How it works -->
  <section class="section">
    <div class="section-label">How it works</div>
    <h2 class="section-title">Three steps, live in minutes</h2>
    <p class="section-sub">The site talks directly to the GitHub API at runtime. Your folder structure is your database.</p>

    <div class="steps">
      <div class="step">
        <div class="step-num-wrap"><div class="step-num">1</div></div>
        <div class="step-body">
          <h3>Organise your PDFs on GitHub</h3>
          <p>Create a <code style="display:inline; background:none; border:none; padding:0; font-size:inherit; color:var(--accent)">Notes/</code> folder in your repo. Inside it, create a subfolder for each subject, then a subfolder for each professor, and drop your PDFs in.</p>
          <code>Notes/
├── Data Structures/
│   ├── Dr. Ramesh Kumar/
│   │   └── Unit 1 - Arrays.pdf
│   └── Prof. Anitha Nair/
│       └── Module 1.pdf
└── Operating Systems/
    └── Dr. Suresh Pillai/
        └── Process Management.pdf</code>
        </div>
      </div>

      <div class="step">
        <div class="step-num-wrap"><div class="step-num">2</div></div>
        <div class="step-body">
          <h3>Set your username and repo</h3>
          <p>Open <code style="display:inline; background:none; border:none; padding:0; font-size:inherit; color:var(--accent)">index.html</code> and fill in just two lines in the config block at the bottom of the file.</p>
          <code>const GITHUB_USER = "your_username";
const GITHUB_REPO = "your_repo_name";</code>
        </div>
      </div>

      <div class="step">
        <div class="step-num-wrap"><div class="step-num">3</div></div>
        <div class="step-body">
          <h3>Enable GitHub Pages</h3>
          <p>Push everything to GitHub, go to Settings → Pages, select your branch and root, and save. Your site is live at <code style="display:inline; background:none; border:none; padding:0; font-size:inherit; color:var(--accent)">username.github.io/repo</code> — for free.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Architecture -->
  <section class="section">
    <div class="section-label">Architecture</div>
    <h2 class="section-title">No backend, ever</h2>
    <p class="section-sub">Everything runs in the browser. The GitHub Contents API is the only data source — no server, no database, no costs.</p>

    <div class="arch-grid">
      <div class="arch-card">
        <div class="arch-icon">🌐</div>
        <h3>GitHub Contents API</h3>
        <p>Reads your folder structure at runtime — subjects, professor names, and PDF files discovered automatically.</p>
      </div>
      <div class="arch-card">
        <div class="arch-icon">⚡</div>
        <h3>Lazy loading</h3>
        <p>Only the subject sidebar loads upfront. Professor folders and notes are fetched when you click a subject.</p>
      </div>
      <div class="arch-card">
        <div class="arch-icon">💾</div>
        <h3>Session cache</h3>
        <p>Once a subject is loaded it's cached in memory, so switching back is instant without re-fetching.</p>
      </div>
      <div class="arch-card">
        <div class="arch-icon">📥</div>
        <h3>Direct download</h3>
        <p>Download links point straight to raw GitHub URLs — no redirect, no middleman, no tracking.</p>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="section">
    <div class="section-label">FAQ</div>
    <h2 class="section-title">Common questions</h2>

    <div class="faq-list">
      <div class="faq-item">
        <div class="faq-q">Does the repo have to be public?</div>
        <div class="faq-a">Yes. The GitHub Contents API used here is unauthenticated, so it only works on public repositories. Private repos would require a personal access token, which is not safe to embed in a static file.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q">Will there be rate limit issues?</div>
        <div class="faq-a">Unlikely for normal use. GitHub allows 60 unauthenticated API requests per hour per IP. Each subject click uses roughly 2–3 requests. You'd need dozens of simultaneous users opening new subjects to hit the limit.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q">How do I add new notes?</div>
        <div class="faq-a">Just drop a PDF into the right folder and push to GitHub — no code changes needed. The site picks it up automatically on the next load. File name becomes the note title (<code>-</code> and <code>_</code> are replaced with spaces).</div>
      </div>
      <div class="faq-item">
        <div class="faq-q">Can I have multiple professors per subject?</div>
        <div class="faq-a">Yes — just create multiple professor subfolders inside the subject folder. Each one gets its own section with an avatar and note cards.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q">Why does search only work for subjects I've already opened?</div>
        <div class="faq-a">Notes are loaded lazily to keep the site fast — fetching all subjects upfront would make dozens of API calls on every page load. Search works on everything already in memory from your current session.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q">Can I host this somewhere other than GitHub Pages?</div>
        <div class="faq-a">Yes. It's a single <code>index.html</code> file — it works on Netlify, Vercel, Cloudflare Pages, or any static host. The notes still come from your GitHub repo via the API regardless of where the site itself is hosted.</div>
      </div>
    </div>
  </section>

  <!-- Stack -->
  <section class="section" style="border-bottom: none;">
    <div class="section-label">Tech stack</div>
    <h2 class="section-title">Built with boring, reliable tools</h2>
    <p class="section-sub">No build step, no npm, no bundler. Just a browser and a GitHub account.</p>
    <div class="stack-row">
      <div class="stack-chip"><span class="dot"></span>Vue.js 3 (CDN)</div>
      <div class="stack-chip"><span class="dot"></span>GitHub Contents API</div>
      <div class="stack-chip"><span class="dot"></span>GitHub Pages</div>
      <div class="stack-chip"><span class="dot"></span>Playfair Display</div>
      <div class="stack-chip"><span class="dot"></span>DM Sans</div>
      <div class="stack-chip"><span class="dot"></span>Vanilla CSS</div>
    </div>
  </section>

</div>

<footer>
  Made for classmates, by a classmate.<br/>
  <a href="https://github.com/YOUR_USERNAME/YOUR_REPO" target="_blank">GitHub</a> · MIT License
</footer>

</body>
</html>
## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
