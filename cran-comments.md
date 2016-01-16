## Resubmission

This is a resubmission. In this version I have:  

* Fixed the misuse in the LICENSE file.  
* Changed the documentation of `install_packages.R` to refer to `utils::install.packages`, there is no `base::install.packages` function.  
* Changed the package name from `packages` to `easypackages`.

## Release summary

This is the package's first release.

## Test environments

* local Windows 8 install, R 3.2.3
* ubuntu 14.04 LTS (VM), R 3.2.3

## R CMD check results

There were no ERRORs, WARNINGs or NOTEs when running R CMD check locally.

When running the win builder (via `devtools::build_win`) I got this NOTE on both checks:

```
* checking CRAN incoming feasibility ... NOTE
Maintainer: 'Jake Sherman <jake@jakesherman.com>'

New submission
```

On one of the win builder machines (using R version 3.2.3 (2015-12-10) and using platform: x86_64-w64-mingw32 (64-bit)) I got the following note:

```
* checking package dependencies ... NOTE
  No repository set, so cyclic dependency check skipped
```

I did not get this note on my local machines or on the other win builder machine. The issue is mentioned in (this)[https://stackoverflow.com/questions/23164929/note-in-r-cran-check-no-repository-set-so-cyclic-dependency-check-skipped] StackOverFlow post. I tried their solution, which was to add a `.Rprofile` file to the repo containing this code: `local({r <- getOption("repos"); r["CRAN"] <- "http://ftp.ussg.iu.edu/CRAN/";   options(repos = r)})` but it did not fix the problem. 
