# CS 225 Coursebook

This is the repository for the CS 225 Coursbook built with [Bookdown](https://bookdown.org/)

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

- [ ] 1. On the home page of your repo, click Settings. Scroll down to the GitHub pages section and change **Source** to **master branch /docs folder**.  Above the **Source** line, a bar will appear with your book's URL. The bar will initially be blue and indicate that your book is *ready* to be published and will change to green once it is published. Copy the URL. (Note that sometimes there is a delay until your book actually appears at that URL. If it doesn't appear after a few minutes, make a change and commit it to trigger a GitHub Pages build.)

- [ ] 2. Click the gear button near "About" on the home page of the repo and paste your book URL into the **Website** field that appears on the right.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please update the respective issues based on what chapters you work on.

In the file tree, you can edit the following files (each chapter has a file).

```
01-C++_Review.Rmd
02-Array-List.Rmd
03-Trees.Rmd
04-BST.Rmd
05-Heaps.Rmd
06-DSets.Rmd
07-BTrees.Rmd
08-Hashing.Rmd
09-Graphs.Rmd
10-GraphAlgs.Rmd
```

The `tex` folder has the LaTeX template that is used to render the PDF. 
The `docs` folder has the HTML output that is used for the github pages website.
The `images` folder should have copies of all the graphics you use in the markdown files.
The `style.css` document contains the styles for the html page. 

You should not need to touch anything besides the markdown files and the images folder. 

## Resources

- [] The official guide to **bookdown**: https://bookdown.org/yihui/bookdown

## License
[CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)