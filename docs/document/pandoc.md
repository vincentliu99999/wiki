# Pandoc - a universal document converter

[Manual](https://pandoc.org/MANUAL.html)

## CLI

```shell
pandoc --version

# to HTML
pandoc -o output.html input.md

# to Word
pandoc -o output.docx input.md
pandoc -o output.docx -s input.md

# online Markdown to Word
pandoc -f markdown -t docx -o CHANGELOG.docx --request-header User-Agent:"Mozilla/5.0" https://raw.githubusercontent.com/angular/angular/master/CHANGELOG.md
```

## Sample

```markdown
---
title: Test
---

# Title!

This is a test of *pandoc*.

- list one
- list two
```

```shell
# Markdown to HTML
pandoc test1.md -f markdown -t html -s -o test1.html
# MArkdown to LaTeX
pandoc test1.md -f markdown -t latex -s -o test1.tex
pandoc test1.md -s -o test1.tex
```