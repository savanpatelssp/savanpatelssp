# SP NET — Repository & Visibility Strategy

This document defines the complete GitHub repository plan for `savanpatelssp`.
It records every project identified on the local machine, whether it should be public or
private, the rationale, and the recommended name / description / topics.

> **Usernames note:** existing remotes use `SavanPatelSP` / `savanpatelsp` (GitHub treats
> these case-insensitively and they resolve to the same account). The account is managed
> as `savanpatelssp`.

> **Branding (distinct entities):**
> - **SP NET** ([sp-net.in](https://sp-net.in)) — the **parent organization**.
> - **SP NET INC** ([spnetinc.com](https://spnetinc.com)) — a **child company operating
>   within / under the broader SP NET organization**. Not independent of SP NET.
> - The GitHub identity is **"Founder & Engineer · SP NET INC"**, but the profile materials
>   must keep SP NET as the parent and never describe sp-net.in as the "SP NET INC website"
>   or SP NET INC as an independent company.

---

## Positioning

The GitHub presence is anchored on **three pillars** consistent with the company:

| Pillar | Product | Public anchor |
|---|---|---|
| Communication | SP NET GRAM | `spnetgram-website` |
| Ownership | SP NET ADMIN OS / Platform | `spnet-admin`, `SPNET-API` (private) |
| Community | Community infrastructure | future |

The **flagship technical project** is **SavaroX** — a Layer-1 blockchain built from first
principles. It is the deepest signal of engineering capability on the profile.

---

## Public repositories

Public repos are the professional face of the account. Each must have a **real, maintained
README**; a default `create-next-app` README is not acceptable for a public repo.

| # | Repo | Description (recommended) | Topics | Purpose | README status |
|---|---|---|---|---|---|
| 1 | `savarox` | Layer-1 blockchain built from first principles — consensus, nodes, wallets, SDK, and block explorer. Native currency SRX. | `blockchain`, `layer1`, `consensus`, `typescript`, `cryptocurrency`, `distributed-systems` | Flagship technical showcase | Maintain existing |
| 2 | `savan-portfolio` | Personal portfolio & product hub — engineering, design, and founder story. | `portfolio`, `nextjs`, `typescript`, `tailwindcss`, `react` | Design + craft showcase | Already polished |
| 3 | `spnet-website` | Website for the SP NET parent organization (sp-net.in). | `nextjs`, `react`, `typescript`, `tailwindcss`, `company-site` | Brand face | **Rewrite needed** |
| 4 | `spnet-admin` | SP NET ADMIN OS — enterprise administration platform with RBAC, audit logs, analytics, moderation. | `admin`, `dashboard`, `rbac`, `nextjs`, `enterprise` | Engineering depth | **Rewrite needed** |
| 5 | `spnetgram-website` | Official website for SP NET GRAM — messaging platform. | `messaging`, `nextjs`, `typescript`, `product-site` | Communication pillar | Maintain existing |
| 6 | `spng-helpdesk` | Enterprise helpdesk — multi-channel (email, WhatsApp, chat) business communication. | `helpdesk`, `support`, `nextjs`, `multichannel` | Breadth signal | **Rewrite needed** |

### Recommended final 6 pinned repositories

Excluding the profile repo (auto-displayed), the strongest final six, evaluated against
actual repo state (value, credibility, uniqueness, readiness):

1. `savarox` — flagship, uniquely technical, ready
2. `savan-portfolio` — premium craft, ready
3. `spnet-website` — brand anchor for the SP NET parent organization
4. `spnet-admin` — enterprise engineering depth
5. `spnetgram-website` — communication pillar product site
6. `spng-helpdesk` — breadth across business communication

Rationale: this set shows **blockchain depth** (SavaroX), **design craft** (portfolio),
**brand** (spnet-website), **enterprise rigor** (admin), **a flagship product** (GRAM site),
and **platform breadth** (helpdesk) — a balanced representation of who you are and what
you build, without exposing the private backend.

---

## Private repositories

Private repos are kept off the public profile. They are internal, commercially sensitive,
or not representative of the current stack.

| Repo | Why private |
|---|---|
| `SPNET-API` | Private backend powering the whole ecosystem (24 modules, 57 controllers, internal architecture). Commercially sensitive. **Reference publicly, do not expose source.** |
| `SPNETGRAM-ADMINBOT` | Internal ops tool (Telegraf admin bot). Operational, not showcase. |
| `SP-NET-GRAMS` | Fork of Telegram Android source. Licensing concerns with upstream. |
| `SPNETTOOLS` | PHP Telegram bot — legacy stack, not representative of current TypeScript engineering. |
| `spnet-submit` | Internal workspace/content submission tool. |
| `spnet-submit-studio` | Internal studio platform (SQLite, in-progress). |
| `spnet-diagnostics-service` | Internal monitoring/diagnostics. |
| `spnet-community` | No commits yet; infrastructure not released. Keep local until it matures. |
| `SPNET-CC` (Control Center) | No git repo; unified internal admin. |
| `sp-net-in` | Superseded by `spnet-website`. Do not publish. |
| `spnetgram` assets, `spnet-icons` | Brand assets, not code repos. |
| `savarox_wallet` | Flutter wallet, not yet git-initialized/ready. |
| `Documents/spnet-backend` | Python game backend (stdlib/SQLite), research-stage. |
| `stable-diffusion-webui-forge` | Third-party tool, not your code. |
| `Documents/GitHub/test sp`, `desktop-tutorial` | Scaffolding, not representative. |
| `StudioProjects/*` | Android Studio test projects, not representative. |

---

## Organization structure

**Recommendation: keep the personal `savanpatelssp` account as the primary namespace for now.**
You have no collaborators requiring org-level teams or billing. A GitHub **organization**
(`github.com/sp-net`) becomes valuable once there is a second contributor, a need for
team/role management, or when migrating repos as a formal company account.

**When to create the org:** when SP NET has ≥1 additional collaborator or your first
team-level repo. At that point, transfer the flagship public repos into it and keep the
profile repo + `savan-portfolio` on the personal account.

---

## Suggested repository creation order

1. Push public repos that already exist and have real content (`savarox`, `savan-portfolio`,
   `spnetgram-website`).
2. Rewrite and push the brand/engineering repos (`spnet-website`, `spnet-admin`,
   `spng-helpdesk`).
3. Pin the final six.
4. Keep `SPNET-API` private and link it from the profile text as the platform foundation.

---

## README templates & verboten list

For every public repo, follow the consistent structure (see per-repo drafts):

1. One-line description
2. What it does (2–3 sentences)
3. Architecture / how it works (if complex)
4. Tech stack (inline, no badge images)
5. Getting started
6. Status
7. License

**Verboten for this profile (all repos + profile):**
- No badge-image spam (shields.io walls)
- No fake/meaningless GitHub statistics cards
- No rainbow emoji filler
- No flashy animations
- No generic "portfolio template" copy

---

## Icon system & assets

### Approach

The profile README uses a **premium SVG asset system in the SP NET brand palette** — real
brand-colour logos, brand-navy Lucide concept icons, and a self-contained navy hero banner.
No emoji, no inline `<svg>`, no JavaScript, no runtime dependencies. Everything is stored
**locally** in the profile repo and referenced by **relative path** through `<img>` tags.
This is the reliable pattern for GitHub's README renderer:

- GitHub **sanitizes Markdown READMEs and blocks raw inline `<svg>`**, but it renders
  `<img src="relative/path.svg">` via its camo image proxy. Keep every icon as a file, not
  inline markup.
- Result: fast, self-contained (no external CDN at render time), degrades to alt text if
  an asset is ever missing, and does not break when third-party services go down.

### Directory layout

```
assets/
  hero/       — full-width navy banner (genuine ring + plane mark, brand navy #1E3D4D)
  brands/     — Simple Icons (recognized tech/brand logos), native brand colours
  icons/ui/   — Lucide-style stroke icons (concepts & navigation), navy stroke #1E3D4D
  marks/      — SP NET family marks (ring + paper-plane), navy/blue derivations
  motion/     — subtle SMIL breathing-glow mark (see animation note below)
  dividers/   — hairline vs. lead gradient separators + ecosystem-flow brand diagram
```

### Sources & licensing

- **Brand logos** (`assets/brands/`) — sourced from [Simple Icons](https://simpleicons.org)
  (CC0), fetched via `cdn.simpleicons.org/<slug>` and **kept at their native brand colour**
  for recognisability on the white README background.
- **Concept/navigation icons** (`assets/icons/ui/`) — sourced from
  [Lucide](https://lucide.dev) (ISC/MIT), fetched from `lucide-static` and normalized to
  `stroke="#1E3D4D"` (brand navy), 2px stroke, `viewBox 0 0 24 24`.
- **Family marks** (`assets/marks/`) — derived from **existing real assets** in the
  workspace (not invented logos):
  - `spnet-ring.svg` / `spnet-ring-navy.svg` — SP NET hexagonal ring (navy stroke).
  - `spnet-gram.svg` / `spnet-gram-navy.svg` — ring + paper-plane mark (blue accent plane).
  - `spnet-badge.svg` — the complete ring + inner blue badge + white plane mark (the full
    genuine SPGRAM treatment). Used for GRAM and the hero/motion/ecosystem visuals.

### Owned product marks (`assets/projects/`)

Custom profile marks for **owned brands** (not official logos, but consistent ring+core
family marks): `savarox.svg`, `gram.svg` (genuine SPGRAM badge), `admin-os.svg`,
`platform.svg`. Rule: an owned brand uses its owned mark; only genuinely generic UI
concepts (e.g. Portfolio, Helpdesk) fall back to a Lucide `icons/ui/` icon.
- **Hero** (`assets/hero/spnet-hero.svg`) — self-contained banner composing the genuine
  ring + plane geometry on navy `#1E3D4D` with `#35A9E6` accent and `<text>` (valid because
  it lives inside an SVG *file*, not inline in the README).

> Rule: do **not** invent official logos that don't exist. Owned brands use their owned
> `assets/projects/` mark; only genuinely generic UI concepts (e.g. a personal portfolio)
> use a neutral Lucide icon instead of fabricating one.

### Animation note

CSS `@keyframes` and JavaScript are stripped by GitHub, but **SMIL** (`<animate>`,
`<animateTransform>`) survives GitHub's sanitizer and animates in modern browsers.
`assets/motion/spnet-footer.svg` (footer) and `assets/hero/spnet-hero-v4.svg` use a slow
(7–8s) breathing opacity/radius pulse on a halo behind the mark — subtle, not flashing
or spinning. **Honest caveat:** some GitHub renderers and the camo image proxy flatten
SMIL to the static first frame (a fully drawn mark), so the motion is progressive
enhancement over an always-visible static mark.

### Motion hierarchy

- **Hero** → ambient halo (SMIL in `spnet-hero-v4.svg`)
- **Ecosystem** → signal/pulse (`ecosystem-flow.gif`, 60f 700×400)
- **Currently Building** → breathing signal (`signal-glow.gif`, 36f 240×240)
- **Footer** → subtle ambient halo (SMIL in `spnet-footer.svg`)

Combined animated GIF payload is well under 500 KB.

### Conventions

- **Colour:** brand navy `#1E3D4D` + electric blue `#35A9E6` + white/off-white. Real brand
  colours only for logos; concept icons use navy stroke. No rainbow, no badge walls.
- **Sizes:** 14px inline/nav · 16px inline emphasis · 16px technology grid · 22px selected-work
  cards · 26px building cards · hero is full-width.
- **Mark ownership:** an owned brand uses its owned mark (`assets/projects/` or
  `assets/marks/`); a technology uses a real brand logo (`assets/brands/`); only genuinely
  generic UI concepts use a Lucide `icons/ui/` icon. Never a generic icon as a product identity.
- **Never** use `<svg>` inline in the README; always `<img src="assets/...">`.
- Keep icons minimal — one per concept, no duplicate/competing marks for the same thing.

### Ecosystem diagram

`assets/dividers/ecosystem-flow-v5.svg` is **700×400** (1.75:1). The earlier `-v4` asset used
a 3.57:1 canvas whose product labels fell outside the `viewBox` bottom edge, so GitHub clipped
them. Rule for diagrams: the `viewBox` must contain 100% of content (labels included) with
matched `width`/`height`; verify with rasterization at both desktop and 360px width before use.

### How to add an icon

1. Download the SVG to the right folder (brand/`brands/`, concept/`icons/ui/`, family mark/`marks/`).
2. Brands: keep native Simple Icons colour. Concepts/Lucide: normalize `stroke` to `#1E3D4D`.
3. Reference via `<img src="assets/...svg" width="N" height="N" alt="...">`.
4. Confirm the path resolves (see the verify step in the build notes).

---

## GitHub profile cards / widgets — strategy

### Verified account state (checked live)

`public_repos: 0` · `public_gists: 0` · `followers: 1` · created 2026-07-04.

Every live/dynamic stats widget reads this public data, so on a brand-new account **all of
them render zero/empty**. The profile favours clean, honest, always-visible content, so
**no dynamic stats cards are included in the profile README right now** — this is the
selective, evidence-based call, consistent with the project guidance (cards only help when
they tell a true, current story; empty cards actively hurt a first impression).

### Evaluated options

| Card / service | Verdict for now | Why |
|---|---|---|
| GitHub stats card (`github-readme-stats` / `github-stats-extended`) | **Defer** | Would render 0 stars/0 repos. Add once there's real activity. |
| Top-languages card | **Defer** | 0 public repos → empty. Needs real repos; then `hide=HTML,CSS` + compact layout so it shows the true stack (TypeScript, Dart, Java). |
| Streak card (`DenverCoder1/github-readme-streak-stats`) | **Defer** | Current streak reads 0 days on a new account. |
| Trophy card (`github-profile-trophy`) | **Reject** | Rank B/C/UNKNOWN on a new account reads as gamified/junior; explicitly discouraged by hiring-focused guidance. |
| Activity graph (`github-readme-activity-graph`) | **Defer** | Empty on a new account; duplicates the native contribution squares. |
| Visitor / hit counter | **Reject** | Low number looks sad; no hiring signal. |
| SVG snake / typing animation / quote cards | **Reject** | Novelty embeds, load slow, push content down. |
| Static showcase (HTML table in README) | **Selected now** | Always renders, never empty, no third-party service, no load-time/rate-limit risk. Present in the current README. |

### When ready (activation plan)

Once the account has honest activity (recommended: after pushing the public repos and
~2–4+ weeks of commits), flip on exactly **two** cards, matching the README's clean style:

1. **Stats card** — count the current year, include private contributions (requires a
   fine-grained token via a self-hosted/`github-readme-stats-action` instance), keep a
   minimal theme, `hide_border=true`, no rank icon.
2. **Top-languages card** — `layout=compact`, `hide=HTML,CSS,Jupyter`, limited language
   count, so it reads "TypeScript, Dart, Java / …" rather than "HTML 78%".

Keep: no trophies, no streak pressure, no counters. Prefer a **self-hosted** instance
(Vercel + token) over the shared public endpoint, which is prone to rate-limit outages.

---

## Manual GitHub setup needed (not code)

Do these on github.com, not via commits:

1. **Profile README repo** — create `savanpatelssp/savanpatelssp` (exact account name) and
   push the profile `README.md`. GitHub requires the repo name to exactly match the
   username for it to display on the profile.
2. **Profile settings**
   - **Bio:** `Founder & Engineer · SP NET INC`
   - **Website:** `https://sp-net.in`
   - **Location:** optional city/country
   - Clear the current generic/coded bio and blog fields (they are placeholders today).
3. **Avatar & name** — set a professional avatar; confirm display name **"Savan Patel"**.
4. **Pin the six repos** after pushing them (see pin list above).
5. **Pinned-repo settings** — ensure descriptions + topics are set so pins look intentional.
6. (Optional, later) **Private contribution setting** — enable "Include private contributions
   on my profile" only once it is true and you want it reflected in the native graph.
