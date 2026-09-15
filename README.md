# Corporate Finance Working Group — website

Plain HTML and CSS, no build step. GitHub Pages serves the files exactly as
they are in `main`, so a push is a deploy.

## Files

| File | What it is |
| --- | --- |
| `index.html` | About the group, meeting logistics, how to attend and present |
| `schedule.html` | Current quarter's talks |
| `archive.html` | Past talks, grouped by academic year |
| `people.html` | Organizers, faculty sponsors, former organizers |
| `assets/css/style.css` | All styling — colors and fonts are variables at the top |
| `.nojekyll` | Tells GitHub Pages to serve files as-is instead of running Jekyll |

## Editing

1. Open the `.html` file in any text editor.
2. Make the change. Comments marked `EDIT:` or `ADD A TALK:` show where.
3. Open the file in a browser to check it (double-click works — no server needed).
4. Commit and push. The live site updates in about a minute.

### Adding a talk

In `schedule.html`, copy an existing `<tr>` block, paste it in date order, and
edit the date, speaker and paper. Drop the `<a href>` if there is no draft link.

### Rolling over a quarter

Move the finished quarter's `<tr>` rows from `schedule.html` into a new table in
`archive.html`, above the existing ones. Then add the new quarter's dates to
`schedule.html`.

### Changing the look

Edit the variables at the top of `assets/css/style.css`. `--maroon` is the accent
color used for links, rules and headings; `--measure` and `--page` control width.

## A caveat about the header

There is no templating, so the header, nav and footer are copied into all four
pages. If you change one, change all four. It is four files — grep for the text
you are replacing:

```bash
grep -rn "cfwg.booth@gmail.com" *.html
```

## Before going live

Still placeholders:

- `Room XXX` in `index.html` and `schedule.html` — the meeting room
- example speakers in `schedule.html` and `archive.html`
- `COORGANIZER-NAME@uchicago.edu` and the faculty/former-organizer names in
  `people.html`

Find them all with:

```bash
grep -rn "Room XXX\|Example Presenter\|COORGANIZER-NAME\|Faculty Name\|Jane Doe\|Richard Roe\|A. N. Other" *.html
```

Already set: the group contact address (`cfwg.booth@gmail.com`) in every footer,
and the mailing-list link on the home page, which currently opens an email to
that address. If the group later gets a real listserv, replace that one `mailto:`
in `index.html` with its signup URL.
