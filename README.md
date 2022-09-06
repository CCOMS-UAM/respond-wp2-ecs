# Respository `respond-wp2-ecs`

Data integration tasks of the Edad con Salud cohort data for Respond-WP2

# Project installation

## Software components

- Install [R version 4.2.1][R]:
  In Windows, using the [binary installer][inst] is recommended.

[R]: https://cran.rstudio.com/bin/windows/base/old/4.2.1/
[inst]: https://cran.rstudio.com/bin/windows/base/old/4.2.1/R-4.2.1-win.exe

- [Rstudio Desktop][RS]: Although not strictly necessary, it is recommended
  to install the Rstudio IDE; for strict reproducibility, use build
  [2022.07.1+554 for Windows 10/11][RSv].

[RS]: https://www.rstudio.com/products/rstudio/download/#download

[RSv]: https://download1.rstudio.org/desktop/windows/RStudio-2022.07.1-554.exe

- [Git client][G]: Install the Git client in order to be able to clone locally
  the project repository.
  On Windows, use the [64-bit Windows installer][GW].

[G]: https://git-scm.com/download

[GW]: https://github.com/git-for-windows/git/releases/download/v2.37.3.windows.1/Git-2.37.3-64-bit.exe

## Installing the project locally

This project is hosted as a GitHub repository.
It can be cloned as a local Git repository following [these instructions][CR]
(steps 2 through 7).
Note that this will create a local copy of ('clone') the GitHub repository as an
Rstudio project in the folder specified.
The URL that must be entered into the `Repository URL` text box is:

```
https://github.com/CCOMS-UAM/respond-wp2-ecs.git
```

[CR]: https://book.cds101.com/using-rstudio-server-to-clone-a-github-repo-as-a-new-project.html#step---2

After cloning the repository,
the Rstudio project will open automatically in the Rstudio IDE.
If it doesn't, or you want to return later to the project in Rstudio,
you can do so by double clicking on the file `mapping-initiatives.Rproj`
that has been created in the project folder when cloning the repository.

**NOTE:** It is common practice to avoid using and versioning `.Rprofile` files.
Hoever, this project uses [package `renv`][renv]
to create a reproducible environment,
which needs the `.Rprofile` file that lives in the root directory of the
project. **Please DO NOT delete or edit this file**; it will install and
activate the `renv` package and make it ready for restoring the environment.

[renv]: https://cran.r-project.org/package=renv

## Restoring the environment

The reproducible environment created by `renv` must be restored to install
all the packages this project needs to be built properly. Use the
"renv" => "Restore library..." button in Rstudio's "Packages" tab to restore
the environment. Alternatively, you can type in the console:

```r
renv::restore()
```

# Repository structure

The file structure of this repository is as follows:

```
respond-wp2-ecs
|
|--- dat       (To store input datasets; must NEVER be checked-in to Github)
|
|--- notebooks (Notebooks to explore data and test processes live here)
|
|--- output    (Processing outputs; files must be individually "checked-in" if necessary)
|
|--- R         (R functions created for this project live here)
|
|--- renv      (System library necesssary for `renv` to work. DON'T TOUCH)
|
|--- src       (Source scripts that implement the main processes)
|
|--- www       (Project assets, e.g., images, bibliography files, etc.)
```

Use the folders as indicated to store the different files and generate the
outputs of the processes.
