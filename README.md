# weft-loom-theme-ip-paris

`ip-paris` brand theme for weft-loom compile tooling.

**Signature** : Institut Polytechnique de Paris — navy #002554 + steel-blue accent.

## Usage (Marp slides)

```yaml
---
marp: true
theme: ip-paris
---

# Slide title
```

The theme is published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-ip-paris:<tag>` and consumed by
the tool images via a multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-ip-parisatest /marp/ /opt/marp/themes/
```

## Layout

| Path                  | Contents                                  |
| --------------------- | ----------------------------------------- |
| `marp/ip-paris.css`   | Marp slide stylesheet                     |
| `pandoc/ip-paris.tex` | pandoc XeLaTeX template (V0.2)            |
| `latex/ip-paris.sty`  | raw LaTeX style package (V0.2)            |

## Brand integrity

The CSS commits to the institution's published visual identity
guide. Re-brand drift → open a PR with the citation. Logos +
wordmarks remain the property of their owners and are referenced
only by colour + typography, never bundled as image assets.

## License

BSD-3-Clause (openweft).
