# Customization Cheat-Sheet

Everything visible on your profile lives in one file: `README.md`. Each part is
marked with a `<!-- SECTION: ... -->` comment so you can find it fast. Edit,
commit, push — the profile updates within seconds.

## Change your name / tagline (header banner)

Find `SECTION: HEADER BANNER`. The banner is a URL — edit these parameters:

| Parameter | What it changes |
|-----------|-----------------|
| `text=Mahinoor` | The big name text |
| `desc=Full-Stack%20Developer...` | The subtitle (use `%20` for spaces) |
| `color=0:667eea,50:764ba2,100:6B8DD6` | Gradient colors (hex, no `#`) |
| `height=200` | Banner height |

## Change the typing animation lines

Find `SECTION: TYPING TAGLINE`. Edit the `lines=` parameter — separate lines
with `;`, use `+` for spaces, and URL-encode special characters (`&` is `%26`).

## Add LinkedIn / email buttons

Find `SECTION: SOCIAL / CONTACT BADGES`. There is a commented-out block —
replace `YOUR_LINKEDIN` and `YOUR_EMAIL@example.com` with your real links,
then remove the `<!--` and `-->` around the block.

More badges: browse [shields.io](https://shields.io) and copy the pattern
`https://img.shields.io/badge/LABEL-VALUE-COLOR?style=for-the-badge&logo=LOGO`.

## Edit the About section

Find `SECTION: ABOUT ME`. Plain markdown — just edit the bullet points.

## Add or remove skill icons

Find `SECTION: TECH STACK`. Icons come from [skillicons.dev](https://skillicons.dev).
Add or remove icon names in the `i=` list, e.g. `i=python,ts,docker,aws`.
The full list of supported icons is on their homepage.

## Change the color theme of the stats cards

Find `SECTION: GITHUB STATS`. Each card URL has a `theme=` parameter.
There are two copies of every card: one ending in `#gh-dark-mode-only`
(shown to dark-mode visitors) and one ending in `#gh-light-mode-only`.
Popular themes: `github_dark`, `tokyonight`, `dracula`, `radical`, `default`.
All themes: [github-readme-stats themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md).

## Change featured projects

Find `SECTION: FEATURED PROJECTS`. Each card is a link + image pair; just
change the `repo=` parameter (and the `href`) to any of your repositories.
Remember to update both the dark-mode and light-mode copies.

## Auto-updating parts (do not edit by hand)

- **Recent Activity** — the text between `<!--START_SECTION:activity-->` and
  `<!--END_SECTION:activity-->` is rewritten daily by the
  `update-activity.yml` workflow. Edit anything outside the markers freely.
- **Contribution snake** — regenerated daily by `snake.yml` and stored on the
  `output` branch. Nothing to maintain.
- You can trigger either one manually: GitHub repo -> Actions tab -> pick the
  workflow -> "Run workflow".

## Publishing changes

```bash
git add .
git commit -m "update profile"
git push
```
