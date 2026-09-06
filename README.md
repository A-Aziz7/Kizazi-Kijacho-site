# Kizazi Kijacho website

A static implementation of the Kizazi Kijacho site mockup — plain HTML, CSS,
and no build step, so it can be deployed with GitHub Pages as-is.

## Pages

| File | Page |
|---|---|
| `index.html` | Overview (landing page) |
| `about.html` | About |
| `research.html` | Research |
| `people.html` | People |
| `partners.html` | Partners |
| `outputs.html` | Outputs |
| `legal.html` | Privacy policy, legal notice, accessibility statement (footer-only, not in the nav) |

`styles.css` holds the whole design system (colour, type, layout). Real logos now
live under `assets/`:

- `assets/kizazi-logo-horizontal.png` — the Kizazi Kijacho lockup, used in the
  header, hero, and footer on every page.
- `assets/logos/funders/` — SERI, ERC, the Swedish Research Council, FCDO, the
  Conrad N. Hilton Foundation, SNSF, and the Research Council of Norway.
- `assets/logos/partners/` — EDI Global, d.tree, EGPAF, Ifakara Health
  Institute, and Thrive.

Any institution not yet in those folders (University of Zurich, IIES, Yale,
FAIR/NHH, University of Chile, Chr. Michelsen Institute, Government of
Tanzania) still shows as a dashed placeholder on the Partners page, under
"Other partners — logos pending confirmation," until a logo file is supplied.

## Deploy on GitHub Pages

1. Create a new repository on GitHub (e.g. `kizazi-kijacho-site`) and push these
   files to it:
   ```bash
   cd kizazi-kijacho
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
2. On GitHub, go to the repo's **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch",
   branch `main`, folder `/ (root)`. Save.
4. GitHub publishes the site at `https://<your-username>.github.io/<repo-name>/`
   within a minute or two.
5. Optional custom domain (e.g. `kizazikijacho.org`): add a `CNAME` file to the
   repo root containing just the domain name, and point the domain's DNS at
   GitHub Pages (an `A` record set or a `CNAME` record, per GitHub's docs) —
   then set the domain under Settings → Pages too.

No other build tooling, package manager, or server is required — it's plain
static files.

## Open items carried over from the mockup

These are called out in the site content itself (as placeholders or italic
notes) so they're easy to find, but flagging them here too:

- Privacy policy, legal notice and accessibility statement text needs drafting
  and sign-off from UZH Legal Services and the data protection officer.
- Leadership bios and collaborator bios/affiliations need confirming.
- The real research project list and facts (design, sample, location, years)
  need confirming — the entries here are illustrative, copied from the mockup.
- Past partner and past funder names, and what each funder's grant covers.
- 18 real photographs are needed (see the mockup's "Photos and alternative
  text" note) — each placeholder box states what should go there. Every photo
  needs alt text written at upload time; this is required for WCAG 2.1 AA and
  can't be automated.
- A decision on whether to run analytics at all (the draft privacy policy
  currently assumes none are run).
- Whether the "longitudinal survey" entry on the Research page belongs under
  Longitudinal surveys or Field experiments (flagged inline, unresolved in the
  original mockup too).

## Notes on fidelity to the mockup

- The Google Sites-specific caveats in the mockup (no custom footer per page,
  no cookie consent banner, collapsible elements can't hold images, etc.) don't
  apply here — this is hand-built, so those workarounds were dropped in favour
  of the more direct version (e.g. collaborator rows use `<details>` with a
  small circular photo slot inline, rather than the accordion-without-photos
  compromise the mockup describes).
- Motion is limited to the browser's native `<details>` expand/collapse
  (respects `prefers-reduced-motion`) — nothing else animates.
- Contact is a `mailto:` link in the nav/footer, since the mockup lists
  "Contact" in the nav but doesn't define a dedicated Contact page.
