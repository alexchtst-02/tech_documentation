# Hardware Module Technical Documentation Template

A LaTeX template for documenting RTL hardware modules: engineering context, requirements, architecture, design reasoning, implementation, verification evidence, and limitations. But you can also use as you want.

## Color palettes

The template uses one repository branch. `palette.tex` is the active color setup loaded by `main.tex`; it defaults to BLUE PRINT. The files in `palette-options/` are presets, not separate branches, and have no effect until copied over `palette.tex`.

Copy one preset over the active palette file, then rebuild the PDF:

- BLUE PRINT: `cp palette-options/blueprint.tex palette.tex`
- Evergreen: `cp palette-options/evergreen.tex palette.tex`
- Graphite + Plum: `cp palette-options/graphite-plum.tex palette.tex`

The palette preview is in [`palette-preview.html`](palette-preview.html).

## Use

1. Copy this repository's template files into a module documentation folder, or use the repository as a starting point.
2. Edit the module identity in `main.tex` and fill in the files under `content/`.
3. Add figures to `assets/`, sources to `bib/references.bib`, and supporting artifacts to `appendix/` or a linked evidence repository.
4. Build from the template directory with `latexmk -pdf main.tex`.

The template uses TeX Gyre Pagella at 11 pt for body text, Lato for headings, and TeX Gyre Cursor for monospace text. Pages are A4 portrait, with a restrained cover background and a footer showing the module, revision, and page number.

## Figure layouts

All figures are constrained to printable page width. The only supported ratios are 1:1, 2:1, and 5:1 (paper width:image width). Side-by-side layouts always place the image on the left and text on the right. Copy-ready layouts appear in the relevant `content/` sections and `diagram_layout_snippets.tex`; verification sections include slots for waveforms and other evidence images.

## Design references

The first visual direction used a warm orange accent with a white background. It was replaced after review because it felt too warm and brand-like. BLUE PRINT, Evergreen, and Graphite + Plum are project-specific color choices, not copied from an external palette. Compare them in [`palette-preview.html`](palette-preview.html); the selected values are in `palette.tex`.

| Element | Reference | Use in this template |
| --- | --- | --- |
| Body typeface | [TeX Gyre Pagella on CTAN](https://ctan.org/pkg/tex-gyre-pagella?lang=en) | 11 pt serif body text |
| Headings | [Lato on Google Fonts](https://fonts.google.com/specimen/Lato) | Sans-serif headings and cover labels |
| Monospace | [TeX Gyre Cursor on CTAN](https://ctan.org/pkg/tex-gyre-cursor?lang=en) | RTL identifiers and code-like text |
| Text contrast | [W3C Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/wcag/) and [Understanding Success Criterion 1.4.3](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html) | Contrast target of at least 4.5:1 for normal-sized text |

WCAG is used here as a contrast reference, not as a claim that the generated PDF conforms to WCAG. The references describe the typefaces and contrast guidance. The palette values, page layout, and typography pairing are design decisions made for this template; the previous orange-and-white treatment is not retained.
