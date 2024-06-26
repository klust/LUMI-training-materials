# LUMI training materials repository

## Processing

The web site can is built using the `mkdocs` tool that is also used for the 
[main LUMI documentation](https://github.com/Lumi-supercomputer/lumi-userguide).
However, the version of the software that is used to build this web site may be
different, and some additional packages may be employed. See the 
`requirements.txt` file in the repository.

All development is done in a fork of the repository. GitHub is set up with
`upstream` as the remote name for the 
[main repository on the lumi-supercomputer GitHub](https://github.com/Lumi-supercomputer/LUMI-training-materials)
while `origin`is used as the remote name for the fork in which all work is being done.

IF the repositories are set up in this way, then the following Makefile targets can
be used to build the web site:

-   `serve` or `preview`: Preview the web site on your computer. (Point the browser to - usually - localhost:8000)
-   `build`: Build locally, not very useful.
-   `deploy-origin`: Deploy the web site to the remote `origin`, i.e., the fork, which is ideal for testing without
    disrupting the production site.
-   `deploy-upstream`: Deploy the web site to the remote `upstream`, i.e., the 
    [production site on lumi-supercomputer.github.io](https://lumi-supercomputer.github.io/LUMI-training-materials/)

Alternatively, it is also possible to rebuild the website using a GitHub action.
The options are:

-   When pushing to the main branch, the rebuild process will run automatically. So be careful not to
    push unfinished work as this would bring the web site in an inconsistent state.

-   It is aso possible to run the action manually:

    -   Go to the repository in the web interface of GitHub (well, you might be there if you read this)

    -   Click the "Actions" menu at the top of the screen.

    -   In the left column, chose "Deploy on push to main or manually"

    -   Now select the "Run workflow" dropdown box at the right

    -   And use the drop-down box that appears now to select the branch.

    -   And finally click on "Run workflow"

The preferred workflow is to do all work via branches. During a course, when frequent updating of the web
site is needed, it is better not to work on the main branch but on one branch for the duration of the course
and process from that branch either by running `mkdocs` on your laptop or by triggering the deploy action
manually in the branch that you are working on. In that way, if an annoying mess-up is made during the course,
it is always easy to restore the training materials web site to the hopefully consistent state from before the
course.


## Structure of the docs subdirectory

-   Each regular course has its own subdirectory with materials in the `docs` subdirectory. As such it becomes
    rather easy to archive that material when no longer relevant.

    Hackathon materials are also considered as a course.

    Each course also has its own subdirectory in the 
    [LUMI-training-lumio `courses` subdirectory](https://github.com/klust/LUMI-training-lumio). The capitalisation
    of the name in there may be different as it has to be a valid bucket name and it turns out that it the character
    range that can be used for the name of a bucket on LUMI-O is rather limited, e.g., no capitals.

-   The user coffee break material is considered as a special course, so get a subdirectory (`User-Coffee-Breaks`) 
    with further organisation in that subdirectory. 
    There is currently a single bucket on LUMI-O for all material of the coffee breaks (`user-coffee-breaks`).

-   The User Update docs and sessions made after some system updates are also together considered as a special course
    with currently a single bucket on LUMI-O for all material. Again we do make a further structure in the `User-Updates` 
    subdirectory in this repository and can do the same in the `user-updates` bucket.

Other subdirectories:

-   `docs/assets` currently only contains the favicon.
-   `docs/stylesheets` contains the stylesheet used to define extra admonitions.
-   The contents of `site_customisations` is largely based on that for the LUMI docs


## Data management

Large files (e.g., tar files, images, PDFs) are not stored on GitHub but on
LUMI-O. The data is pushed to LUMI-O from a laptop on which the data is
prepared using `rclone`. Some data is public, some data is private. 
Scripts to facilitate data management per course can be found in the
[LUMI-training-lumio repository](https://github.com/klust/LUMI-training-lumio)
but the way of working may need some further information that will be provided
in that repository.
