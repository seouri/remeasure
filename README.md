# Setup

Install `uv` if needed:

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Sync the project environment:

```sh
uv sync
```

# Usage

```sh
uvx opendataloader-pdf -f markdown -o references/md references
```

# Manuscript LaTeX

The cleaned LaTeX manuscript is in `manuscript/main.tex`.

Install TeX Live locally with Homebrew:

```sh
brew install texlive
```

Compile the manuscript from the repository root:

```sh
latexmk -lualatex -cd manuscript/main.tex
```

The compiled PDF is written to `manuscript/main.pdf`.

Clean generated LaTeX build files:

```sh
latexmk -C -cd manuscript/main.tex
```

If LuaLaTeX reports that it has no writable cache path in a sandboxed shell, use a workspace-local home directory:

```sh
mkdir -p .tex-home
HOME="$(pwd)/.tex-home" latexmk -lualatex -cd manuscript/main.tex
```

[Zotero Collection](https://www.zotero.org/groups/69319/zaklab/collections/SXNPGSNX/collection)

# Transcripts

- [May 20](https://harvard.zoom.us/rec/share/_xlHuNvgjwkUY0-SAN7wm1kX5iN83c70r1abed5UgKZZ-JGzJ_R2PGKfHiH3K5U2.I_EgRJl6KFSRs3cb?pwd=DGvQtIoEjKXqWj-fuwAAIAAAADwvkjqPpfzW_i7BkFvSSFoMk-CbGhgDSGvDjYMZuuwbx_JQMntXlOXU-ntvYoLohjAwMDAwNA)
