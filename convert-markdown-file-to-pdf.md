
# Convert Markdown file to pdf with Pandoc

## Install Pandoc 

After a while (9300s) wondering how to make a pdf export from a atom generated markdown (...I know), without any success, finaly I went to Pandoc.

First download the pandoc installer for debian based distro here Ubuntu:
https://github.com/jgm/pandoc/releases/tag/2.10.1

Install the package with:  sudo dpkg -i pandoc-2.10.1-1-amd64.deb 

	pandoc --version: 

pandoc 2.10.1
Compiled with pandoc-types 1.21, texmath 0.12.0.2, skylighting 0.8.5
Default user data directory: /home/x/.local/share/pandoc or /home/x/.pandoc
Copyright (C) 2006-2020 John MacFarlane
Web:  https://pandoc.org
This is free software; see the source for copying conditions.
There is no warranty, not even for merchantability or fitness
for a particular purpose.


## Some packages are to install ([LaTeX](https://fr.wikipedia.org/wiki/LaTeX) packages) : 

	sudo apt install texlive-xetex

To make a pdf from a markdown file, then run the command:

	pandoc yourfile.md --pdf-engine=xelatex -o yourfile.pdf
