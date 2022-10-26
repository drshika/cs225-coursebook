# CS 225 Coursebook

A coursebook that is written by a mix of course staff and students for UIUC CS 225! All the files live on the Github repo as markdown files and feel free to hop in and update any file and submit a Pull Request! The coursebook is built with [Bookdown](https://bookdown.org/) and Github Pages. 

This generates both `pdf` and a static website. 

### Setup

- [ ] 1. Clone your new repo with *File, New Project..., Version Control, Git* in RStudio. 

### Render the book

- [ ] 1. Install **bookdown** with `install.packages("bookdown")`. If you already have it, update to the [latest version](https://CRAN.R-project.org/package=bookdown).

- [ ] 2. Render locally with `bookdown::render_book("index.Rmd")`.

- [ ] 3. Use `browseURL("docs/index.html")` to view your book locally (or just open `index.html` in a browser).

- [ ] 4. If it looks good, commit and push all changed files to GitHub. 

### Using the GUI interface

1. To generate a page of the book, press the `Knit` button in the upper lefthand corner
<img width="543" alt="Screen Shot 2022-10-25 at 7 18 14 PM" src="https://user-images.githubusercontent.com/67125579/197905472-776e597b-8182-40a7-ae22-b602f07786f7.png">
This will open a pop-up with the compiled bookdown page. 
2. To build the entire book, press the `Build` button in the build tab in the upper righthand subwindow. 
<img width="919" alt="Screen Shot 2022-10-25 at 7 20 13 PM" src="https://user-images.githubusercontent.com/67125579/197905661-4c4428c4-8dd9-4e73-a711-50e3a64cd381.png">

### Set up GitHub Pages

- [x] 1. On the home page of your repo, click Settings. Scroll down to the GitHub pages section and change **Source** to **master branch /docs folder**.  Above the **Source** line, a bar will appear with your book's URL. The bar will initially be blue and indicate that your book is *ready* to be published and will change to green once it is published. Copy the URL. (Note that sometimes there is a delay until your book actually appears at that URL. If it doesn't appear after a few minutes, make a change and commit it to trigger a GitHub Pages build.)

- [x] 2. Click the gear button near "About" on the home page of the repo and paste your book URL into the **Website** field that appears on the right.

## Structure 

The structure is similar to most [bookdown](https://bookdown.org/) projects with this specific [template](https://github.com/jtr13/bookdown-template).

* The chapter files themselves are saved as `NN-chapter.Rmd` with the number specifying the order they are presented. Mostly this is where most of your work will happen.

* The associated images are saved in `images/chapter` (no number) and you can use these in your documents. If you're using a picture form another chapter, consider making a copy to have everything in the right place.

* `index.Rmd` has the front matter for the book. This is the opening of the book for people. 

* `_bookdown.yml` and `_output.yml` have some configuration that affects the entire site.

* `style.css` has styling that we can mess with the website 

* `tex/` has book specific templating that is used for the PDF generation

* `bookdown-template-master 2.Rproj` is needed so that you can open the project in RStudio and has the bookdown build configuration.

* `docs/` has the generated site and pdf. You shouldn't need to manually edit anything here and it should always be generated. If you make any changes here, keep in mind that they will probably be overwritten 


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please update the respective issues based on what chapters you work on.

In the file tree, you can edit the following files (each chapter has a file).

```
02-CIntro.Rmd
03-Arrays.Rmd
04-Trees.Rmd
05-BST.Rmd
06-Heaps.Rmd
07-DSets.Rmd
08-BTrees.Rmd
09-Hashing.Rmd
10-Graphs.Rmd
11-GraphAlgs.Rmd
```

You should not need to touch anything besides the markdown files and the images folder. 

## Resources

- [ ] The official guide to **bookdown**: https://bookdown.org/yihui/bookdown

## License
[CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
