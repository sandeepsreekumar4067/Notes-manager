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

MIT — free to use, share, and modify.
