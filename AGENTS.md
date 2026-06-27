# AGENTS.md

## Cursor Cloud specific instructions

This repository is the source for `csmangum.github.io`, a single-page personal
portfolio served by **GitHub Pages**. It is a static Jekyll site:

- `_config.yml` — Jekyll/GitHub Pages config.
- `index.html` — the entire page (plain HTML, no Liquid/front matter).
- `img/` — favicons and app icons.

There is no `Gemfile`, no `package.json`, and no automated test suite.

### Running locally (development mode)

Jekyll is the GitHub Pages dev tool and is preinstalled in the snapshot
(Ruby + the `jekyll` and `bundler` gems). To run the site in dev mode:

```bash
jekyll serve --host 0.0.0.0 --port 4000
```

Then open `http://localhost:4000/`. Use `jekyll build` for a one-off build into
`_site/`.

### Non-obvious caveats

- **Missing front-end assets are expected.** `index.html` references
  `css/*.css`, `js/*.js`, and a few images (`img/me.jpg`, `img/mylogowhite.png`,
  `img/site.webmanifest`) that are **not committed** to the repo. Locally these
  return 404 and the page renders unstyled. This is the repo's actual state, not
  an environment problem — do not "fix" it by adding assets unless asked. The
  HTML, in-page anchor navigation (`#about`, `#projects`, etc.), favicons, and
  Jekyll build all work correctly.
- `jekyll build`/`serve` writes a `_site/` directory (and `.jekyll-cache/`) into
  the repo root. These are build artifacts — do not commit them.
- No linting or test tooling is configured for this repo.
