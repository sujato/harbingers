# README.md

View `.md` file in any markdown viewer or plain text editor.

The following is for anyone who wants it in a different form.

## make pdf

Working PDF generated with `pandoc`. Note that the template is included solely because the `mainmatter` command has to be removed for it to not add a blank page after the the title page. 

```
pandoc --pdf-engine lualatex --template=template.tex -H styles.tex harbingers.md -o harbingers.pdf
```

To add cover (doesn't put it on first page unfortunately), include `--include-before-body cover.tex`

## make cover pdf

Lulu requires covers in PDF. But for some reason it was finnicky about the file size, even though the png source was exactly correct. Oh well, i solved it using:

```
img2pdf cover_full_6x9.png -o cover_full_6x9.pdf --imgsize 915.4x666 --pagesize 915.4x666
```

This creates a PDF file with embedded PNG, no file conversion or loss.

## make html

```
pandoc -s  --toc -H styles.css harbingers.md -o harbingers.html

```

This produces a pretty sweet and clean HTML document, with table of contents and included styles. 

One thing to do by hand. For the licencing page, remove the {curly brackets} and wrap it in `<small>`.

## make epub

```
pandoc harbingers.md -o harbingers.epub
```
