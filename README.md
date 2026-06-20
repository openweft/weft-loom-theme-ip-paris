<p align="center"><img src="https://raw.githubusercontent.com/openweft/brand/main/social/weft-loom-theme-ip-paris.png" alt="weft-loom-theme-ip-paris" width="720"></p>

# weft-loom-theme-ip-paris

`ip-paris` brand theme for weft-loom compile tooling.

**Signature** : `#008BD2` primary cyan-blue with brand-secondary
`#8DBE23` green and brand-tertiary `#E9500E` orange. The earlier
"navy-only" draft was wrong ; IP Paris's web identity is
unambiguously bright + multicolour.

## Source

Colour frequency-counted across the IP Paris theme stylesheet
(`www.ip-paris.fr/sites/default/files/css/...`, 2026-06 audit) :

| Token              | Hex       | Occurrences in CSS |
| ------------------ | --------- | ------------------ |
| Primary blue       | `#008BD2` | 204                |
| Secondary green    | `#8DBE23` | 96                 |
| Tertiary orange    | `#E9500E` | 73                 |
| Body text          | `#212529` | 64                 |
| Muted text         | `#6c757d` | 124                |
| Paper surface      | `#f8f9fa` | 81                 |

## Typography

The institution's brand serif is **Alverata** (Type Together,
licensed via Adobe Typekit on `use.typekit.net/gda5mpa.css`).
Alverata is not freely redistributable, so this theme falls back
to **Source Serif Pro** / **Cardo** / Georgia for the serif
display ; the system font stack is used for body.

If you have an Alverata licence and want to use it locally, add
the font CSS to the slide preamble — the theme already requests
"Alverata" first in the font-family stack.

## Wordmark

The official wording is **"Institut Polytechnique de Paris"**
(capital I, capital P, capital P, lowercase remainder). The CSS
prints it in the footer.

## Usage (Marp slides)

```yaml
---
marp: true
theme: ip-paris
---

# Slide title
```

The top banner shows the brand triad (blue / green / orange) in
proportional widths — kept subtle to avoid overwhelming the
content.

## Distribution

Published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-ip-paris:<tag>`. Tool images
consume it via multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-ip-paris:latest /marp/ip-paris.css /opt/marp/themes/ip-paris.css
```

## License

BSD-3-Clause (openweft). Institutional name + logo remain the
property of Institut Polytechnique de Paris ; this repo references
the brand only by colour and typography.

## Cover slide / logo

The theme renders a brand-typography wordmark on `section.lead`
slides ; no institutional logo file is bundled (trademarks remain
the institution's property and aren't redistributable under
BSD-3-Clause).

If you have the right to use the official logotype in your deck,
supply your own image via the `--ipp-logo` CSS variable :

```markdown
<!-- _class: lead -->
<!-- _style: "--ipp-logo: url(/path/to/your/logo.svg)" -->

# Title here
## Subtitle here
```

Official logo source : https://www.ip-paris.fr/communiques-et-dossiers-de-presse.
