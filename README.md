# texwc
A simple command line script for getting a more accurate word count on LaTeX projects. This is basically a wrapper for `detex | wc` with support for configuration files for projects, so that a word count can be obtained from the terminal simply be entering `texwc`.

## Installation and usage
* Put `texwc` on your path (e.g. `~/bin`).
* Add an index file named `.texwc` to your LaTeX project's root directory.
* Add the relative paths of any `.tex` files you would like to include in the word count to the index file on separate lines.
* From the terminal, run `texwc [path]`, where `path` is the root directory of your LaTeX project. If `path` is omitted, the current working directory is used.

## Dependencies
`detex` (`sudo apt install texlive-extra-utils`, or see [OpenDetex](https://github.com/yjkimjunior/opendetex) for a more recent version)
