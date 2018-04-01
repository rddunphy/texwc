# texwc
A simple command line script for getting a more accurate word count on LaTeX projects. This is basically a wrapper for `detex | wc` with support for configuration files for projects, so that a word count can be obtained from the terminal simply be entering `texwc`.

## Installation and usage
* Put `texwc` on your path (e.g. `~/bin`).
* From the terminal, run `texwc [path]`, where `path` is the path of a `.tex` file.
* To get a word count from multiple files, specify the path of a `.texwc` config file for `path`, or the path of a directory containing a config file. If `path`, the current working directory is used.

## Dependencies
`detex` (`sudo apt install texlive-extra-utils`, or see [OpenDetex](https://github.com/yjkimjunior/opendetex) for a more recent version)

## Config file
The config file contains a JSON object representing configuration options. Automatic generation of config files is coming.

Configuration options are:
* `"files"` (required): a list of relative `.tex` file paths to be included in the word count.
