
OSG Council Webpages
====================

This repository manages the webpages of the OSG Council.  A few notes about its contents:

-   An auto-deploy script is setup; when a commit is made to the master branch, Travis-CI
    will automatically rebuild the static website and push the results to the `gh-pages`
    branch.
-   [GitHub hosts the website itself](https://opensciencegrid.github.io/council).
-   The `twiki` subfolder contains a snapshot of all public data from the previous twiki
    setup.
-   If a twiki page needs to be brought into the mkdocs setup, we use the `jagregory/pandoc`
    docker image:
    ```
    pushd twiki
    docker run -v `pwd`:/source jagregory/pandoc -f twiki -t markdown_github New > ~/projects/council/docs/Members.md
    popd
    ```
    This will do a reasonable automatic conversion from twiki to MarkDown - typically 1-5 minutes of human review is
    needed on the resulting document.

