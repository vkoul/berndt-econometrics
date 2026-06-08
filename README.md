## Background

I first came across *The Practice of Econometrics: Classic and Contemporary* by [Ernst R. Berndt](http://mitsloan.mit.edu/faculty-and-research/faculty-directory/detail/?id=41392) through [Emmanuel Flachaire](https://sites.google.com/site/emmanuelflachaire/), who recommends the book for his [Applied Econometrics course](https://sites.google.com/site/emmanuelflachaire/cours/econometrie-appliquee?authuser=0).

The book caught my attention because of its strong applied focus. I searched further for the book and the author, which led me to this repository containing the accompanying datasets. I also found a [UMass Applied Econometrics course page](https://courses.umass.edu/econ753/) that recommends the book and provides links to scanned chapter-wise PDFs.

## Book Reviews

While researching the book, I also came across strong recommendations from several leading economists:

> “Studying this book and working through the exercises could do for economics students what interning in a city hospital does for medical students — give them a taste of what practice is really like and get them used to the sight of blood. This is wonderful education.”
>
> — **Robert M. Solow**  
> Massachusetts Institute of Technology

> “Berndt reveals how econometric methods are used in economic measurement and testing. Students will immediately understand how the book can help them develop usable skills. The examples and exercises really focus the student on the critical issues. A good course using this text can help students develop very rapidly technically and remember why they know each method.”
>
> — **Timothy F. Bresnahan**  
> Stanford University

> “Berndt’s book represents an ambitious, unusual, and impressive piece of work. It gives every promise of being extremely useful to a wide variety of readers.”
>
> — **Bennett T. McCallum**  
> Carnegie Mellon University

> “Ernie Berndt has done an outstanding job. I expect that his book will find a place on the reading list of virtually every serious course on applied econometrics.”
>
> — **Harvey S. Rosen**  
> Princeton University

## What This Repository Contains

This repository currently provides:

- Data files accompanying *The Practice of Econometrics*
- Links to scanned chapter PDFs of the book
- Supporting material for working through the book’s applied econometrics exercises

The hands-on material in the book looks especially useful for anyone who wants to understand econometrics through real empirical examples rather than theory alone.


### Fetch the Book Chapters
 The UMass course gives the links: 
 >Scanned chapters of The Practice of Econometrics (Ernest M. Berndt) are available from
http://courses.umass.edu/econ753/berndt.poe/Ch01.pdf (substituting for 01 with other chapter numbers).

Chatgpt created a code to download all via R. You can do similarly for Python 
```r
dir.create("berndt_chapters", showWarnings = FALSE)

base_url <- "https://courses.umass.edu/econ753/berndt.poe/Ch%02d.pdf"

for (i in 1:20) {
  url <- sprintf(base_url, i)
  dest_file <- file.path("berndt_chapters", sprintf("Ch%02d.pdf", i))
  
  message("Trying: ", url)
  
  result <- try(
    download.file(url, destfile = dest_file, mode = "wb", quiet = TRUE),
    silent = TRUE
  )
  
  if (inherits(result, "try-error")) {
    message("Chapter ", i, " not found or download failed.")
  } else {
    message("Downloaded Chapter ", i)
  }
}
```

The content of the book can be found here

## Original Repository Note

This repository contains the data files for the textbook *The Practice of Econometrics: Classic and Contemporary* by [Ernst R. Berndt][2]. [The Practice of Econometrics][1] was published in 1991 and has ISBN `0-201-49900-2`.

Currently, the repository contains the raw data files from the floppy disk that accompanied the textbook.

If time permits, I may work through the exercises using a more modern programming language.

## Other Resources

Completed exercises and data files using TSP for *The Practice of Econometrics* are available from [Clint Cummins’s website][3].

However, since TSP is rarely used today, this repository is intended to make the data more easily accessible to non-TSP users who want to complete the book’s exercises using modern tools.

[1]: https://www.worldcat.org/isbn/0201499002
[2]: http://mitsloan.mit.edu/faculty-and-research/faculty-directory/detail/?id=41392
[3]: https://clintcummins.com/
