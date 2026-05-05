# every tap — site

Static site for the NFC sharing kiosk project. Plain HTML/CSS/JS, no build step.

## Structure

```
.
├── index.html       # home
├── about.html       # project background + design values + build
├── deck.html        # iframe-embedded slide deck
├── contact.html     # contact channels
├── css/
│   └── style.css
├── js/              # (empty — reserved for later)
└── assets/          # drop images, PDFs, etc. here
```

## Things to fill in before deploying

Search the repo for `REPLACE` — there are placeholders in:

- **`contact.html`** — email, GitHub, LinkedIn URLs.

The slide deck and kiosk prototype are bundled in `assets/deck/` and already
wired up. Replace those files in place when you have updated versions — keep
the filenames `NFCSlideDeck.html` and `Kiosk Prototype v5.html` (the deck's
own iframe references the kiosk file by that exact name).

## Deploying to GitHub Pages

1. Create a new GitHub repo (public).
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "initial site"
   git branch -M main
   git remote add origin git@github.com:USERNAME/REPO.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a
   branch → `main` / `(root)`** → Save.
4. Wait ~30 seconds. Site will be at `https://USERNAME.github.io/REPO/`
   (or `https://USERNAME.github.io/` for a user-page repo).

When the domain situation gets sorted, you can point a custom domain at it via
**Settings → Pages → Custom domain**.

## Local preview

Any static server works. Easiest:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.
