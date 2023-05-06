You can chek example, docx to md folder 
---

# Pandoc

## docx to markdown converting

---
if you wanna convert to docx to markdown, you can use pandoc open-source project.


1. go to pandog.org ---> download for you system. I use Win.
2. After Install run cmd and test your pandoc. 

    > pandoc -h

    you can see similar to the cmd screen 

```cmd
    pandoc [OPTIONS] [FILES]
  -f FORMAT, -r FORMAT  --from=FORMAT, --read=FORMAT
  -t FORMAT, -w FORMAT  --to=FORMAT, --write=FORMAT
  -o FILE               --output=FILE
                        --data-dir=DIRECTORY
  -M KEY[:VALUE]        --metadata=KEY[:VALUE]
                        --metadata-file=FILE
  -d FILE               --defaults=FILE
                        --file-scope
                        --sandbox
  -s                    --standalone
                        --template=FILE
  -V KEY[:VALUE]        --variable=KEY[:VALUE]
                        --wrap=auto|none|preserve
                        --ascii
                        --toc, --table-of-contents
                        --toc-depth=NUMBER
  -N                    --number-sections
                        --number-offset=NUMBERS
                        --top-level-division=section|chapter|part
                        --extract-media=PATH
                        --resource-path=SEARCHPATH
  -H FILE               --include-in-header=FILE
  -B FILE               --include-before-body=FILE
  -A FILE               --include-after-body=FILE
                        --no-highlight
                        --highlight-style=STYLE|FILE
                        --syntax-definition=FILE
                        --dpi=NUMBER
                        --eol=crlf|lf|native
                        --columns=NUMBER
  -p                    --preserve-tabs
                        --tab-stop=NUMBER
                        --pdf-engine=PROGRAM
                        --pdf-engine-opt=STRING
                        --reference-doc=FILE
                        --self-contained
                        --embed-resources
                        --request-header=NAME:VALUE
                        --no-check-certificate
                        --abbreviations=FILE
                        --indented-code-classes=STRING
                        --default-image-extension=extension
  -F PROGRAM            --filter=PROGRAM
  -L SCRIPTPATH         --lua-filter=SCRIPTPATH
                        --shift-heading-level-by=NUMBER
                        --base-header-level=NUMBER
                        --track-changes=accept|reject|all
                        --strip-comments
                        --reference-links
                        --reference-location=block|section|document
                        --markdown-headings=setext|atx
                        --list-tables
                        --listings
  -i                    --incremental
                        --slide-level=NUMBER
                        --section-divs
                        --html-q-tags
                        --email-obfuscation=none|javascript|references
                        --id-prefix=STRING
  -T STRING             --title-prefix=STRING
  -c URL                --css=URL
                        --epub-subdirectory=DIRNAME
                        --epub-cover-image=FILE
                        --epub-title-page=true|false
                        --epub-metadata=FILE
                        --epub-embed-font=FILE
                        --split-level=NUMBER
                        --chunk-template=PATHTEMPLATE
                        --epub-chapter-level=NUMBER
                        --ipynb-output=all|none|best
  -C                    --citeproc
                        --bibliography=FILE
                        --csl=FILE
                        --citation-abbreviations=FILE
                        --natbib
                        --biblatex
                        --mathml
                        --webtex[=URL]
                        --mathjax[=URL]
                        --katex[=URL]
                        --gladtex
                        --trace
                        --dump-args
                        --ignore-args
                        --verbose
                        --quiet
                        --fail-if-warnings
                        --log=FILE
                        --bash-completion
                        --list-input-formats
                        --list-output-formats
                        --list-extensions[=FORMAT]
                        --list-highlight-languages
                        --list-highlight-styles
  -D FORMAT             --print-default-template=FORMAT
                        --print-default-data-file=FILE
                        --print-highlight-style=STYLE|FILE
  -v                    --version
  -h                    --help
```

3. create to folder in the desktop : docx to md  (its my chois)
4. put the docx file you want to convert in the folder. (for example: data_book.docx)
5. we need to do is to open the terminal inside this folder. (.\Desktop\docx to md>)



>  6. write command :
> 
>     \Desktop\docx to md> pandoc -t gfm --extract-media . "data_book.docx" -o main.md

Let's explain all the steps

1. pandoc --> its start..!

2. -t gfm --> This is our command that tells Pandoc which type of markdown we want to use. We add "gfm" because we want to use the Github Flavors Markdown type. Let's not forget that this is not an obligation. On Pandoc.org web page, there are many types of markdowns.
   
    *Ps : You can see all the markdown variants that are actually supported by Pandoc.* 

3. --extract-media --> we're going to say that we want to extract the media in the same folder where we are actually running this command. 


"data_book.docx" --> Type the name of the file we want to convert.

-o data_book.md--> output format with output file name

In a very short time from the moment we enter the command, Pandoc will create an image folder and a file with a .md extension whose name we have specified. 

And that's all. 

You can cut and resize all the images under the image folder. When you save it, you can automatically see it in your markdown file. 

