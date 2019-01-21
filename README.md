
<!-- README.md is generated from README.Rmd. Please edit that file -->
sandbox
=======

Welcome !
---------

If you are a newcomer in the `packs4stics` community, this repository is for you. It was specifically created to help new people to learn the basis of all tools used in the project.

The first thing to learn is how to use GIT and GITHUB.

GIT and GITHUB
--------------

GIT is a software designed for efficient version control. It helps you and your collaborators develop better softwares. With GIT, you can save "snapshots" of your work at any moment, and return to a previous state whenever you want. GIT has much more to offer, but this the basis you need to understand for now.

### GIT basis

You'll need some basis on GIT before training on this repository. A first reading that is well adapted to our example is the book of [Hadley Wickham](http://r-pkgs.had.co.nz/git.html). It explains well the basis of GIT in conjunction with R. There are several also several tutorials on the internet for begginers:

-   [learngitbranching](https://learngitbranching.js.org/)
-   [Udacity free MOOC](https://eu.udacity.com/course/how-to-use-git-and-github--ud775#?autoenroll=true)
-   [Github tutorial](https://lab.github.com/)
-   [openclassrooms course](https://openclassrooms.com/fr/courses/2342361-gerez-votre-code-avec-git-et-github) for french only.

A good way to start is also by reading the [GIT book](https://git-scm.com/book/en/v2), that is made for everybody.

### Clone the sandbox repo

To use this example, follow these simple steps:

1.  Download [GIT](https://git-scm.com/) and install it.
2.  Download and install [Github desktop](https://desktop.github.com/), an app to simplify the intercation between you and GIT.
3.  Create an account on [Github](https://github.com/).
4.  Open Github desktop, and set you personal informations to connect it with your Github.com account.
5.  On Github desktop, go to "File", clone repository, or press ctrl+shift+O. And then click on "URL", and enter this adress:

    ``` html
    https://github.com/SticsRPacks/sandbox.git
    ```

    Then, choose where the repository will be cloned (copied) into your computer.

> People that already are members of the SticsRPacks organisation may find the repository directly in the "Github.com" tab.

Congratulations, you just clone the sandbox repository onto you computer! You can see all files in your computer by opening the corresponding folder (`ctrl+shift+F`).

R package format
----------------

An R package needs several mandatory files and folders:

-   DESCRIPTION: this file describes the package (name, authors...)
-   NAMESPACE: this file lists the functions
-   R folder: the folder that contains all R code
-   man folder: the folder that contains all the help pages of the package
-   .Rbuildignore: the file that tells R which files are excluded from the package build

And some are not mandatory but helpful:

-   LICENSE: the license under which the project is developed on.
-   README.Rmd: A text file that explains the project to humans using the Rmarkdown format. When knited, this file produces the `README.md` file that is rendered by Github on the main page
-   README.md: the file rendered by Github in the main page of project and that aims at explaining the project objectives.
-   .gitignore: the file that tells GIT which files to ignore.

Most of these files are automatically generated using specific tools that are described further.

Package example
---------------

Before doing this tutorial, you need to:

1.  Download and install [RStudio](https://www.rstudio.com/)
2.  Download and install [R](https://cloud.r-project.org/)
3.  Download and install the tools to build the package:
    -   [Rtools](https://cran.r-project.org/bin/windows/Rtools/) if you have a windows machine
    -   `XCode` from the AppStore if you have a mac
    -   `r-base-dev` on linux
4.  Use this command line on R to download these packages:

``` r
install.packages(c("devtools", "roxygen2", "testthat", "knitr"))
```

### Open the Rstudio project

Double-click on the `sandbox.Rproj` file. It will open the Rstudio project. From the "Files" window, open the R folder. You will find here all the R scripts used for the package. It is highly encouraged to put each function in a separate file, unless they are very short and can be grouped under a common file with a title that describes well their purpose.

### Simple function

Click on the [`add.r`](R/add.r) file. This file contains one function: `add_x()`. This function simply adds the input to itself. You can see that it is preceded by some text formatted as follows: `#' Text`. This text is a Roxygen documentation. It is formated on a special way that helps R generate the package documentation.

### Build the package

Now that you have the package on your computer, you can build the documentation for all your functions by pressing ctrl+shift+D, or by going on the `Build` tab on the upper-right and by clicking on `More`&gt;`Document`. This uses Roxygen to build the help pages from the documentation you write above your functions. The help pages are written in `.Rd` files on the `man` folder of the package. Do not edit these files.

You can finally build and install your package by going on the `Build` tab on the upper-right, and by clicking on the `Install and Restart` button (or press ctrl+shift+B). This step build the package into your computer.

Now execute this command to access the help page of the function:

``` r
?add_x
```

The help page of the function should pop-up.

### Add a function

Add the following code to the R script:

``` r
add_xy= function(x,y){
  x+y
}
```

This function adds x to y. Your R script should look like this now:

``` r
#' Add once
#'
#' @description Adds the input to itself
#'
#' @param x Double or Integer
#'
#' @return x+x
#' @export
#'
#' @examples
#' add_x(2)
#'
add_x= function(x){
  x+x
}

add_xy= function(x,y){
  x+y
}
```

To add the documentation to your function, place your cursor into the function, click on the magic wand just above your script and choose `Insert Roxygen Skeleton`, or press ctrl+shift+alt+R. This will create a dummy Roxygen documentation above your function using the arguments of your function. Your function should look like this:

``` r
#' Title
#'
#' @param x 
#' @param y 
#'
#' @return
#' @export
#'
#' @examples
add_xy= function(x,y){
  x+y
}
```

Fill the documentation such as:

``` r
#' Add x to y
#'
#' @param x Double or integer
#' @param y Double or integer
#'
#' @return x+y
#' @export
#'
#' @examples
#' add_xy(2,3)
add_xy= function(x,y){
  x+y
}
```

Then re-build your documentation (ctrl+shift+D), and re-build your package (ctrl+shift+B). You should have access to your own function help page:

``` r
?add_xy
```

Share your changes
------------------

GIT commit + push to Github

Make a website
--------------

pkgdown
