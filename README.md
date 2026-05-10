# Companion site: *Can we see hints of dictation in the language of Cicero's letters?*

A static one-page companion to the talk given at *Writing from the Margins*,
Durham University, 15 May 2026.

## Contents

```
.
├── index.html                          ← the page (single file, embedded CSS)
├── assets/
│   ├── handout.pdf                     ← the printed conference handout
│   ├── letter-metadata.pdf             ← all three metadata tables (printable)
│   ├── methodological-appendix.pdf     ← Tables 4–8 of the paper (Appendix A)
│   ├── replication.zip                 ← Python pipeline + CSV data + guide
│   ├── figure1.pdf                     ← density plot, vector
│   └── figure1-1.png                   ← density plot, raster (used inline)
└── README.md
```

## Design notes

- Set in **Cardo** by David Perry, a Bembo-revival typeface designed
  specifically for classicists, Biblical scholars, and medievalists. Loaded
  from Google Fonts.
- Layout uses **Tufte-style asymmetric sidenotes** — the body column anchors
  on the left; commentary, dramatis personae, and methodological notes float
  in the right margin. On screens narrower than ~880px the sidenotes
  automatically stack underneath the body content.
- Manuscript palette throughout: warm cream paper, ink-brown links, a single
  rubric red as accent.
- Letter metadata is shown as flowing entries (not tables), with the “Notes”
  column lifted out and turned into the sidenote for each entry.

## Deploy on GitHub Pages

1. Create a new GitHub repository, e.g. `tomkelly/dictation`.
2. Copy this folder’s contents into the repository root and push.
3. Settings → Pages → Source: **Deploy from a branch**, branch **`main` /
   `(root)`**.
4. Wait ~1 minute. Live at `https://<user>.github.io/<repo>/`.

That’s the URL the conference QR code should point at.

## What still needs your eye before going live

1. **Cite-block URL.** In `index.html` find the `@unpublished` BibTeX entry
   and replace `https://[your-github-username].github.io/[repo-name]/` with
   the actual GitHub Pages URL once you know it.

2. **Suffix-letter URLs.** Two letters in the metadata
   (`Att. 7.13A`, `Att. 10.3A`) are linked using lowercase suffixes
   (`7.13a`, `10.3a`). If those don’t resolve on Scaife, try uppercase —
   I’ve seen both conventions in CTS URN.

3. **OSF anonymisation.** The OSF link is currently the view-only/anonymised
   form taken from footnote 1 of the paper. When peer review concludes and
   you make the project public, replace the anonymised URL with the canonical
   `https://osf.io/vjtmz/` and remove the “Anonymous” caveat in the OSF
   notice block.

## Swapping Cardo → Brill

If you ever fetch the Brill font files (free for non-commercial use from
[brill.com/page/typefont](https://brill.com/page/typefont/the-brill-typeface)),
drop the `.woff2` files into `assets/fonts/` and replace the Google Fonts
`<link>` in `<head>` with:

```html
<style>
  @font-face {
    font-family: 'Brill';
    src: url('assets/fonts/Brill-Regular.woff2') format('woff2');
    font-weight: 400; font-style: normal; font-display: swap;
  }
  @font-face {
    font-family: 'Brill';
    src: url('assets/fonts/Brill-Italic.woff2') format('woff2');
    font-weight: 400; font-style: italic; font-display: swap;
  }
  @font-face {
    font-family: 'Brill';
    src: url('assets/fonts/Brill-Bold.woff2') format('woff2');
    font-weight: 700; font-style: normal; font-display: swap;
  }
</style>
```

Then change the body `font-family` from `'Cardo', …` to `'Brill', 'Cardo', …`.
Cardo stays as the fallback in case the font files fail to load.

## Updating

`git push`. GitHub rebuilds the site automatically.
