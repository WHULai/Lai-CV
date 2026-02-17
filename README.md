# Lai-CV

An academic CV template built with XeLaTeX, customized from `Yuan's Resume`.

## Acknowledgements

Many thanks to the original author **HF Yuan** for creating and open-sourcing the template:  
https://github.com/xyz-yuanhf/yuan-resume

This project also acknowledges the works referenced by the original template:

- Jian Xu's CV: http://www.jianxu.net/en/files/JianXu_CV.pdf
- Matty's Resume: https://github.com/mattyHerzig/mattys_resume

## New Features

- Manage `Publications` with `ref.bib`, and render entries via `\fullcite{...}`.
- Automatically bold your own name in `Publications` by setting:
  - `\renewcommand*{\MyFamilyName}{...}`
  - `\renewcommand*{\MyGivenName}{...}`
- Automatically mark co-first authors and corresponding authors (superscript style) with:
  - `\SetPubAuthorRoles{zhu2026high}{1,2}{3,12,13}`

## Usage

Configure in `main.tex`:

```tex
% Automatically bold your own name in publications
\renewcommand*{\MyFamilyName}{Wei}
\renewcommand*{\MyGivenName}{Lai}

% Author-role marks for one paper
% \SetPubAuthorRoles{bibkey}{co-first author indices}{corresponding author indices}
\SetPubAuthorRoles{zhu2026high}{1,2}{3,12,13}
```

Cite in the `Publications` section:

```tex
\item \fullcite{zhu2026high}
```

Notes:

- Author indices are 1-based and follow the order in `author={...}` of that BibTeX entry.
- You can add a symbol legend under each item, for example:  
  `\textsuperscript{\textdagger} Co-first authors; \textsuperscript{*} Corresponding authors.`

## Compile

- Compile with **XeLaTeX** + **biber** (for example: `latexmk -xelatex main.tex`).
- Fonts are included in this repository; please respect their license terms.

## License

MIT License. Copyrighted fonts are not subjected to this License.
