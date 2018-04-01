# texwc
A simple Bash script for getting a more accurate word count on LaTeX projects.

## Usage
* Put texwc on your path (e.g. `~/bin`).
* Add an index file named `.texwc` to your LaTeX projects root directory.
* Add the relative paths of any `.tex` files you would like to include in the word count to the index file on separate lines.
* From the terminal, run `texwc [DIR]`, where `DIR` is the root directory of your LaTeX project. If `DIR` is omitted, the current working directory is used.

## Dependencies
detex (`sudo apt install texlive-extra-utils`)
