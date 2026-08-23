# Setup — subha279 profile README

Everything here goes into your **special repo**: `github.com/subha279/subha279`
(the repo whose name matches your username — that's what makes it show on your profile).

## 1. Drop the files in

```
subha279/
├── README.md                     ← the profile page
├── subha.svg                     ← animated banner (replaces your old one)
├── divider.svg                   ← gradient section divider
└── .github/
    └── workflows/
        └── snake.yml             ← builds the contribution snake
```

Commit to the **main** branch. If your default branch is `master`, either rename it to
`main` or find/replace `/main/` with `/master/` inside `README.md`.

## 2. Why the banner changed under the hood

Your old `subha.svg` used `<foreignObject>` with HTML + CSS keyframes inside. Two problems:

| Old | New |
| :-- | :-- |
| `<foreignObject>` HTML content is **not rendered** when an SVG is loaded as an image — which is exactly how GitHub serves it. Chrome and Safari show nothing. | Pure SVG (`<text>`, gradients, SMIL `<animate>`) — renders and animates everywhere, including GitHub's camo image proxy. |
| Linked to `github.com/.../blob/main/subha.svg` — that's an **HTML page**, not an image, so it can render as a broken image. | Links to `raw.githubusercontent.com/.../main/subha.svg`. |
| Fixed-position snowflakes escaping the 800×100 box. | Everything clipped inside a rounded card, no overflow. |

The animation you liked is still there: the gradient sweeps across `SUBHA279` forever,
the cursor blinks, and the accent dots twinkle.

## 3. Turn on the contribution snake

1. Push `.github/workflows/snake.yml`.
2. Go to **Actions** tab → accept running workflows if prompted.
3. Settings → Actions → General → Workflow permissions → **Read and write permissions** → Save.
4. Actions → *Generate contribution snake* → **Run workflow**.

It creates an `output` branch holding `snake.svg`. Until that first run finishes, the
snake image in the README will be broken — that's expected.

## 4. Personalise (search the README for `EDIT ME`)

- **Socials** — replace `YOUR-HANDLE` / `YOUR-EMAIL@example.com` in the *ping me* section, and delete any badge you don't use.
- **Project cards** — the pinned cards use exact, case-sensitive repo names. `Steganography` is correct; confirm your file-organizer repo's real name and update both the card URL (`&repo=...`) and the table link.
- **About block** — the IBM SkillsBuild / Edunet line came from your repo description; reword it if you'd like.
- **Tech badges** — delete anything you don't actually use. An honest short list beats a wall of logos.

## 5. Colour reference (Tokyo Night)

| Role | Hex |
| :-- | :-- |
| Background | `#1a1b26` |
| Surface / bars | `#16161e` |
| Border | `#2a2e42` |
| Blue | `#7aa2f7` |
| Purple | `#bb9af7` |
| Cyan | `#7dcfff` |
| Green | `#9ece6a` |
| Red | `#f7768e` |
| Yellow | `#e0af68` |
| Text | `#c0caf5` / `#a9b1d6` |
| Muted text | `#8b94b8` |

Every badge and stats card in the README is already pinned to these values, so if you
swap a colour, swap it everywhere for a consistent look.

## 6. Third-party services used

All free, no account needed — but they're external, so they can occasionally rate-limit or go down:

- `readme-typing-svg.demolab.com` — typing headline
- `img.shields.io` — badges
- `komarev.com/ghpvc` — profile view counter
- `github-readme-stats.vercel.app` — stats, top languages, repo pins
- `streak-stats.demolab.com` — streak card
- `github-profile-trophy.vercel.app` — trophies
- `github-readme-activity-graph.vercel.app` — activity graph
- `capsule-render.vercel.app` — footer wave

The banner and divider are yours and self-hosted in the repo, so the top of your profile
never depends on someone else's uptime.
