Notes
================
Jessica Minnier
1/31/2018

Links:
======

Materials: [rstd.io/forgot](https://github.com/jennybc/what-they-forgot)

To use "in building" mirror: `options(repos = c(CRAN = "https://cran.rstudio.com/"))`

Random thoughts
===============

Morning - library exploration
-----------------------------

-   JB has us go to issues and put emoji on OS, tests that we've signed into github! also sees how many windows users there are
-   it's ok that things take a long time
-   make things self explaining, don't spend a lot of time writing wordy explainers that you have to maintain and won't want to read later
-   organize your files and keep readme up to date!
-   "unless you can keep it current, don't write it"
-   it helps to know about your R installation and where packages go in order to make a package
-   new package `fs`, helps us work with file paths. note, don't use paste() to work with file paths like they are strings, they are not!

Mid-morning - file copying and naming, projects
-----------------------------------------------

-   turn of .RData loading and never ask to save .RData
-   restart R often!
-   no absolute paths
-   use a stable base: `here::here("data","raw-data.csv")` in your project directory, `fs::path_home()`
-   form paths at runtime relative to a stable base
-   normalizePath() makes it work on both windows and mac
-   Rstudio set up a mirror for downloading packages **in** the building! What!
-   use `basename` instead of `strsplit` to get name of file (don't have to specify  or /)
-   name files and directories as thing\_thing-info\_thing2 so for instance day\_session\_topic so you can order and deliminate them later

Side note from my own issues in moving this repo to github
----------------------------------------------------------

How to add an existing Rstudio repo to github:

This has changed since [git 2.9](https://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories), now when you add remote and then pull you need a special option.

    git remote add origin https://github.com/jminnier/rstudioconf18_jennybryan_forgot.git
    git pull origin master --allow-unrelated-histories

Afternoon - git/github
----------------------

-   git is scary but you should learn the 3 things you always have to do and just do them over and over until you are comfortable ("get off the beach!")
-   easier to start from github then go to rstudio (sad)
-   when you clone a repo in Rstudio and copy the ssh (or https) into the prompt, then press TAB, it will auto-fill the name of the repo into the next field!
-   in git commit: two yellow question marks: local file git has never seen before
-   jenny commits her .Rproj (this is controversial)
-   intermediate step "staging" tells git you do want these files to be part of the next commit, this way you can commit files separately
-   use conventional file extensions so that github can show you customized diffs
-   jenny thinks putting derived products in version control is a good idea (i.e. html from Rmds)
-   jim hester will show us how github makes it easy to search code
-   when using workbook button from .R files we get a html report (jenny says html maybe not best option, more later)
-   oh yeah, html does not look good on github =( too raw!
-   mullet: what you need to write (.R, .Rmd) = this business in front; what you want to read/see (.html, .md) = party in the back (or is it the other way around?)
-   .html is not useful but .md is useful for github; use YAML:

        #' ---
        #' output: github_document
        #' ---

-   now github will render the resulting .md file this to look pretty nice!
-   source only hard-liners say don't version control output (only source code). but this makes it really useful to see what the output looks like and how it changes.