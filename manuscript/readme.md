# Manuscript Package

This directory contains the cleaned LaTeX manuscript converted from the source DOCX.

## Files

- `main.tex`: main LaTeX manuscript file.
- `figures/`: figure image files referenced by `main.tex`.
- `source/manuscript_source.docx`: original DOCX source used for conversion.

## Notes

- Filenames use lowercase letters, numbers, underscores, and hyphens only.
- Figure references include file extensions and use relative paths.
- For journal systems that require a flat upload, upload `main.tex` and the files in `figures/` individually, preserving the exact filenames or updating the paths accordingly.

## Build

Install TeX Live locally with Homebrew:

```sh
brew install texlive
```

From the repository root, compile with LuaLaTeX through `latexmk`:

```sh
latexmk -lualatex -cd manuscript/main.tex
```

This writes `manuscript/main.pdf`.

To clean generated LaTeX files:

```sh
latexmk -C -cd manuscript/main.tex
```

If LuaLaTeX cannot find a writable cache path in a sandboxed shell, run:

```sh
mkdir -p .tex-home
HOME="$(pwd)/.tex-home" latexmk -lualatex -cd manuscript/main.tex
```
