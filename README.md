# Corporate Finance Working Group — website

Jekyll site on GitHub Pages, built to match the structure of the sister site
[booth-ap/booth-ap.github.io](https://github.com/booth-ap/booth-ap.github.io).
GitHub builds it on every push, so a push is a deploy. Nothing to install
locally.

## Files

| File | What it is |
| --- | --- |
| `_config.yml` | Theme and site title. Three lines. |
| `index.md` | Landing page: description, advisors, coordinators, quarter index |
| `2026_Autumn.md` | One file per quarter, holding that quarter's table |
| `assets/css/style.scss` | The only styling override — link color |

There is deliberately no `.nojekyll` file. Adding one would switch Jekyll off
and make GitHub serve the raw Markdown instead of rendered pages.

## Adding a new quarter

1. Create `2027_Winter.md` (copy `2026_Autumn.md` as a starting point).
2. Add a section to the top of the `## Schedule & Topics` list in `index.md`:

   ```markdown
   ### Winter 2027
   - Topics: Preliminary Project Ideas
   - [Schedule](2027_Winter)
   ```

3. Commit and push. Live in about a minute.

Link to the schedule **without** the `.md` extension, as shown. Jekyll renders
`2027_Winter.md` to `2027_Winter.html`, and the extension-less form is the one
that stays correct.

## Editing a quarter

The tables are ordinary Markdown. Keep the `| :--- |` separator row — it sets
left alignment. Column widths do not need to line up; Markdown ignores the
whitespace.

## Changing the look

The theme is `jekyll-theme-minimal`, one of the themes GitHub Pages supports
natively. `assets/css/style.scss` imports it and then overrides the link color
to maroon (`#800000`). The asset-pricing group uses teal (`#345053`) in the same
two places if you would rather match them exactly.

Swapping themes is a one-line change to `theme:` in `_config.yml`. The supported
set is listed at <https://pages.github.com/themes/>.

## Still placeholders

- `FACULTY-ADVISOR`, `PAST-YEAR`, `PAST-COORDINATOR` in `index.md`
- `PRESENTER` and `ROOM` in `2026_Autumn.md`

Find them with:

```bash
grep -rn "FACULTY-ADVISOR\|PAST-YEAR\|PAST-COORDINATOR\|PRESENTER\|ROOM" *.md
```

Already set: the group contact address, `cfwg.booth@gmail.com`, on the landing page.
