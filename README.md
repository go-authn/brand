# go-authn brand assets

The org mark is a **key** on the cyan systems-family gradient
(`#22CCE2 → #0079A8`), the same family `go-attest`, `go-volumes`,
`go-filesystems` and forty other sibling orgs use. The colour was not invented
for this org: the family grammar says pick the siblings' colour.

Per-repo marks are **the org glyph declined** — the same key, shrunk into the
top region, over a white name plate. They are not custom glyphs, deliberately:
a distinct mark per repo breaks the family at a glance.

| | |
|---|---|
| `svg/color/go-authn.svg` | the org mark, 256×256, `rx=56` |
| `svg/color/go-authn-fido.svg` | `fido`, declined |
| `svg/color/go-authn-mfa.svg` | `mfa`, declined |
| `avatar/*.png` | 400×400, for org and repo avatars |
| `social/go-authn.png` | 1280×640 social preview |

Rasterised with macOS `qlmanage` and `sips` rather than the fleet's Python
generators, which need Pillow — the same SVG sources, a different oven.
