# texwc
A simple command line script for getting a more accurate word count on LaTeX projects. This is basically a wrapper for `detex | wc` with support for configuration files for projects, so that a word count can be obtained from the terminal simply be entering `texwc`.

## Installation and usage
* Put `texwc` on your path (e.g. `~/bin`).
* Add a config file named `.texwc` to your LaTeX project's root directory.
* The index file should contain a JSON object with a `"files"` field, containing a list of relative `.tex` file paths to be included in the word count.
* From the terminal, run `texwc [path]`, where `path` is the root directory of your LaTeX project. If `path` is omitted, the current working directory is used.

## Dependencies
`detex` (`sudo apt install texlive-extra-utils`, or see [OpenDetex](https://github.com/yjkimjunior/opendetex) for a more recent version)

## Config file
The config file contains a JSON object representing configuration options, such as which files should be included in the word count. Automatic generation of config files is coming.
