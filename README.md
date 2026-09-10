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
| `svg/color/go-authn-keyfactor.svg` | `keyfactor`, declined |
| `svg/color/go-authn-totp.svg` | `totp`, declined |
| `svg/color/go-authn-directory.svg` | `directory`, declined |
| `svg/color/go-authn-oidc.svg` | `oidc`, declined |
| `svg/color/go-authn-authnd.svg` | `authnd`, declined |
| `avatar/*.png` | 400×400, for org and repo avatars |
| `social/go-authn.png` | 1280×640 social preview |

Every declination is the `mfa` file with two strings changed — the
`aria-label` and the `<text>`. Nothing else moves: same gradient, same key, same
plate at the same coordinates, same `font-size` of 26. The longest name so far,
`keyfactor`, still clears the plate by 28 pixels on the left and 30 on the right
at 400×400, so no name has needed a smaller size yet. A name that did would
get one — measured on the render, not guessed at.

Rasterised with macOS `qlmanage` and `sips` rather than the fleet's Python
generators, which need Pillow — the same SVG sources, a different oven:

```sh
qlmanage -t -s 400 -o avatar svg/color/go-authn-<name>.svg
sips -g pixelWidth -g pixelHeight avatar/go-authn-<name>.png
```

`qlmanage` already writes 400×400 for a square `viewBox`, so `sips` is here to
check the result rather than to resize it. Check it: a Quick Look thumbnail that
failed is still a file, and a blank one is a few hundred bytes where these are
about 133 KB.

## What CI checks

The marks are shown on somebody else's page — the profile README at 36 pixels,
the landing page at 88 — where a blank or mis-sized file reads as a broken
image and nothing here would say so. So three things are checked on every pull
request, with no image library installed: every avatar is 400×400 and large
enough not to be a failed thumbnail (dimensions come from the PNG's IHDR chunk,
which is the first 24 bytes); every per-repo SVG has an avatar and every avatar
an SVG; and every per-repo SVG is `go-authn-mfa.svg` with the name changed and
nothing else. The last one is the family rule, which was until now kept by
remembering it. `font-size` is exempt, because a long name is allowed to need a
smaller one.
