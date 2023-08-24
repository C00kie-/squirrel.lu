
# Convert Markdown file to pdf with Pandoc

## Install Pandoc 

After a while (9300s) wondering how to make a pdf export from a atom generated markdown (...I know), without any success, finaly I went to Pandoc.

First download the pandoc installer for debian based distro here Ubuntu:
[releases](https://github.com/jgm/pandoc/releases)

Install the package with:  sudo dpkg -i pandoc-[release_version]

	pandoc --version: 

pandoc 3.1.5
Features: +server +lua
Scripting engine: Lua 5.4
[...]


## Some packages are to install ([LaTeX](https://fr.wikipedia.org/wiki/LaTeX) packages) : 

	sudo apt install texlive-xetex

To make a pdf from a markdown file, then run the command:

	pandoc yourfile.md --pdf-engine=xelatex -o yourfile.pdf
