MD. Saif Islam — Portfolio Website

A single-page portfolio site for a WordPress Web Developer, built as one self-contained index.html (HTML + CSS + vanilla JS, no build step, no dependencies).

Features
Hero, services, work/projects, about, and contact sections
Client-side chat widget (stored in localStorage)
Admin Dashboard (demo): add/edit/delete projects, view messages
Gated behind a simple login screen (see Admin access below)
Auto-locks after 1 minute of inactivity
Project images are auto-resized/compressed on upload before saving
⚠️ Important: this is front-end only

There is no backend/server or database in this project. Everything — including projects and messages — is stored in the visitor's own browser via localStorage, and the admin login check runs entirely in client-side JavaScript.

That means:

Data added in the Admin Dashboard is only visible on that browser/device — it does not sync between visitors or persist on a shared server.
The admin password lives in the page's JavaScript and is visible to anyone who views the page source. It keeps casual visitors out of the admin panel, but it is not real security — don't rely on it to protect sensitive data.

To make this production-ready (real shared data + real security), it needs a proper backend — e.g. rebuilt as a WordPress theme with projects as a Custom Post Type and the REST API, or a small custom API with server-side auth.

Running locally

No build tools needed — just open index.html in a browser, or serve the folder with any static file server, e.g.:

bash
python3 -m http.server 8000

then visit http://localhost:8000.

Deploying with GitHub Pages
Push this repo to GitHub (make sure index.html is at the root of the repo, or inside a /docs folder).
Go to Settings → Pages in the repository.
Under Build and deployment → Source, choose Deploy from a branch.
Pick the branch (usually main) and the folder (/root or /docs, matching where index.html actually is).
Save — GitHub will give you a URL like https://<username>.github.io/<repo-name>/ within a minute or two.
Admin access

Open the site → click Admin Dashboard in the footer → log in. Credentials are set in the <script> section of index.html (ADMIN_EMAIL / ADMIN_PASSWORD) — change them there before sharing this repo publicly.
