# Deploying this site

This is a customized copy of the [AcademicPages](https://github.com/academicpages/academicpages.github.io)
template (Jekyll, built on Minimal Mistakes). It already has:

- A custom color theme ("signals" — indigo accent, light + dark mode) in
  `_sass/theme/_signals_light.scss` / `_signals_dark.scss`
- Custom typography (Newsreader for headings, Inter for body text, IBM Plex Mono
  for code) wired up in `_includes/head.html` and `_sass/_themes.scss`
- A **Teaching** entry already linking to your quantization/sampling lesson
  (`_teaching/2026-quantization-sampling-images.md`)
- Placeholder personal info marked with `[BRACKETS]` throughout

Unlike the Hugo-based template we tried first, **Jekyll builds natively on GitHub
Pages** — no build pipeline, no GitHub Actions, no local install required.

## 1. Create the repository

- For your **main personal site**: create a new GitHub repo named exactly
  `YOUR-GITHUB-USERNAME.github.io` — GitHub auto-recognizes this pattern and serves
  it at `https://YOUR-GITHUB-USERNAME.github.io/` (root URL, no extra path).
- For a **secondary/project site** instead: any repo name works, served at
  `https://YOUR-GITHUB-USERNAME.github.io/repo-name/`.

## 2. Upload these files

Upload the entire contents of this folder to the repo (GitHub's web UI: **Add file →
Upload files**, drag the whole folder in; or use git push from a clone).

## 3. Personalize (search for `[` to find every placeholder)

| What | File |
|---|---|
| Your name, title, bio, employer, email, social/Scholar/GitHub/LinkedIn links | `_config.yml` (the `author:` block near the top) |
| Site title & URL | `_config.yml` (`title`, `url`, `repository` near the very top) |
| Home page bio text | `_pages/about.md` |
| Profile photo | replace `images/profile.png` with your own (same filename, or update `author.avatar` in `_config.yml`) |
| Course list | `_teaching/2026-signals-systems.md` |
| Link to the quantization/sampling lesson | `_teaching/2026-quantization-sampling-images.md` — replace the placeholder URL with your published lesson site's real URL once it's live |
| Publications / Talks / Portfolio | `_publications/`, `_talks/`, `_portfolio/` — example entries are included as format references; edit or delete them |

## 4. Turn on GitHub Pages

Repo → **Settings → Pages** → under "Build and deployment", set **Source: Deploy
from a branch** → **Branch: main**, folder **/ (root)** → **Save**.

GitHub detects the `_config.yml`/Jekyll structure automatically and builds it with
no extra configuration. First build takes about a minute; watch progress under the
repo's **Actions** tab (GitHub runs its own internal Pages-build job even though you
didn't add a workflow file yourself).

## 5. Visit your site

The live URL appears on the Settings → Pages screen once the build finishes.

## Notes

- **Dark mode**: the theme includes a light/dark toggle (top right of the page) —
  both are already styled via the custom "signals" theme.
- **Local preview (optional)**: if you have Ruby installed, `bundle install && bundle
  exec jekyll serve` previews the site at `localhost:4000` before you push. Not
  required — GitHub Pages builds it for you regardless.
- Any future push to `main` automatically rebuilds the live site within about a
  minute.
