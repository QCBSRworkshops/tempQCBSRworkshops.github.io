---
layout: default
title: Contributing | Contribuer
---


# Contribute to the QCBS R Workshops!
<br>

## Getting started

### Install the package qcbsRworkshops

The workshop presentations were created using [Rmarkdown](https://rmarkdown.rstudio.com/) and
[`xaringan`](https://bookdown.org/yihui/rmarkdown/xaringan.html). See the QCBS
template [demo presentation](https://qcbsrworkshops.github.io/templateWorkshops/) and associate [html files](https://raw.githubusercontent.com/QCBSRworkshops/templateWorkshops/master/index.html) to learn how it works.

The package [`qcbsRworkshops` :package:](https://github.com/QCBSRworkshops/qcbsRworkshops) was created to facilitate the development of the R workshops, so the first step is to install and load the package `qcbsRworkshops`.

```r
install.packages("remotes")
remotes::install_github("QCBSRworkshops/qcbsRworkshops")
library(qcbsRworkshops)
```

### Clone the workshop repository

Secondly, you need to create a local copy on your computer of the **workshop##**
repository you will be working on. For example, if you want to work on workshop
\#1, [clone the GitHub
repository](https://help.github.com/articles/cloning-a-repository/) on your
computer using the following command line in a terminal (if you are not familiar
with a terminal, consider using a Git client such as
[GitKraken](https://www.gitkraken.com/)):

```r
git clone https://github.com/QCBSRworkshops/workshop01.git
```


## Workflow

1. Once you cloned the **workshop##** repository, you should be on the `dev` branch.

2. Create a **new branch** (choose a name that reflects what you are adding, we suggest something explicit like `workshop01_intro` if you want to edit the introduction of workshop #1): `git branch workshop01_intro`.

3. Switch branch: `git checkout workshop01_intro`; Note that you can create and switch branch with a single line of command: `git checkout -b workshop01_intro`.

4. Edit the workshop!

5. Once you are done editing, render the presentation using `build_workshops()` R function from the `qcbsRworkshops` package to check if everything works:

```r
# if the workshop folder is the current working directory (preferred), then use
build_workshops()
# if the path to the workshop folder is "path2workshop", then use
build_workshops("path2workshop")
```

5. When the presentation renders correctly, add and commit using the command line: `git add -A` and `git commit -m "instructive message about what you did"` (see this post for [guidelines about commit messages](https://www.freecodecamp.org/news/level-you-up-to-awesome-commit-messages-a85558cb90e8/)).

6. Go back on the `dev` branch: `git checkout dev` and pull `git pull` just to make sure you are up to date.

7. Switch back to your branch: `git checkout workshop01_intro` and merge locally: `git merge dev`. If there are conflicts, please resolve them! When you're done, push your branch on the Github repository: `git push --set-upstream origin workshop01_intro`.

8. Open a [Pull Request (PR)](https://help.github.com/articles/about-pull-requests/).

9. Assign your PR to a reviewer (one of the 3 R workshop coordinators).

10. The reviewer will squash and merge the post once the build passed on Travis.

11. Once the PR is merged, do not forget to pull the `dev` branch!


## Other ways to help us!

If you are not comfortable with Git, you can still help us improving the workshops!

If you notice any mistakes or inconsistencies, or if you'd like to make a suggestion, be it for improving the form or editing the content, do not hesitate to open an [issue](https://help.github.com/articles/about-issues/). Simply follow [these steps to create a new issue](https://help.github.com/articles/creating-an-issue/). Note that there is one unique GitHub repository for every workshop, and so you should use the proper repository when reporting an issues. For instance, if you have a suggestion about the first workshop, use the following URL https://qcbsrworkshops.github.io/workshop01/.




## About the presentation template

The template files (names that start with `qcbsR...`) and assets folder that are used to build the final presentations are in the repo [`templateWorkshops`](https://github.com/QCBSRworkshops/templateWorkshops); the version in the workshop folder are only used locally. This means that local modification to the template files will not be used once you pushed. The template should not be modified. <!--use the command line : `make copy_css` to copy the template files in all the workshop folders.-->
