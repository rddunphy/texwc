# texwc
A simple command line script for getting a more accurate word count on LaTeX projects. This is basically a wrapper for `detex | wc` with support for configuration files for projects, so that a word count can be obtained from the terminal simply be entering `texwc`.

## Installation
Put `texwc` on your path (e.g. `~/bin`).

## Dependencies
`detex` (`sudo apt install texlive-extra-utils`, or see [OpenDetex](https://github.com/yjkimjunior/opendetex) for a more recent version)

## Usage
* From the terminal, run `texwc [path]`, where `path` is the path of a `.tex` file.
* To get a word count from multiple files, specify the path of a `.texwc` config file for `path`, or the path of a directory containing a config file. If no value is specified for `path`, the current working directory is used.
* Config files can be generated with the `-i` option (see below for details).
* By default, \\input and \\include commands are ignored. This is to allow contol over which included files should be counted (e.g. appendices are usually not included in a word count). To expand these commands, use the `--with-includes` option.
* The output will show line, word and character counts for each specified file as well as a total:
  ```
  $ texwc report/.texwc
  LINES WORDS CHARS FILE
     35   595  3965 chapters/01_introduction
    285  5370 33619 chapters/02_background
    220  3002 18913 chapters/03_methodology
    339  4106 25191 chapters/04_implementation
    305  1669 10659 chapters/05_results
     25   814  5156 chapters/06_conclusion
   1209 15556 97503 TOTAL
  ```

## Options
The following options can be specified to modify the behaviour of the script:
* `-h`/`--help`: Print help message with usage information.
* `-i`/`--init`: Initialise directory with a default config file containing all `.tex` files in this directory.
* `-r`/`--recursive`: Recursively include files in subdirectories when initialising (only with `-i`).
* `-w`/`--with-includes`: Expand \\input and \\include commands. (This takes precedence over `detex-options`.)
* `-p`/`--print-text`: Print output of `detex` instead of word count. This can be useful to ensure that the correct text is included in the word count, e.g. that the right environments are being ignored.
* `--plain`: Print in plain text, without formatting by ANSI escape sequences.

## Config file
A texwc config file contains a JSON object representing configuration options.

JSON fields in a config file:
* `"files"` (required): A list of relative `.tex` file paths to be included in the word count.
* `"detex-options"`: A list of options to be passed to `detex`. See the `detex` [documentation](https://www.systutorials.com/docs/linux/man/1-detex/) for details.
* `"ignore-envs"`: A list of environments to exclude from the word count.
