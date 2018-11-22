# The Wikibook Project

[![Build Status](https://travis-ci.com/illinois-cs241/wikibook-project.svg?branch=master)](https://travis-ci.com/illinois-cs241/wikibook-project)


The Wikibook Project is an aim to standardize and build upon Angrave's [original wikibook experiment](https://github.com/angrave/SystemProgramming/wiki).

The most recent version of the wikibook as a single pdf is here: [main.pdf](https://github.com/illinois-cs241/wikibook-project/raw/master/main.pdf).

## Overview

### Goals

* Improve the quality and rigour of the original wikibook
* Keep the openness aspect hand have this be a repository people can make pull requests into.
* Improve the factualness by including citations, footnotes, extended reading, and a glossary
* Have exports in the form of pdf and html
* The content of the wikibook should be in between the current wikibook and an exhaustive survey of linux programming
* Have ownership of the book in case it should go into syndication or something similar
* Have travis build so people don't need to install a bunch of pre-reqs to get started.
* Keep in line with lectures

### What that means
* Not everything you find on here will be in the quiz
* This is class is meant to be pragmatic. Unless extremely relevent, you won't get asked to cite dates and facts.

## Contributing

Want to contribute? Afraid of latex or python? Don't be!

If you want to contribute, all you need to do is
1. Fork
2. Make the changes by
    1. Going to the appropriate chapter
    2. Make changes either online or on the command line
    3. Make a PR
3. The PR will be cleared up and on build, a new version of the wikibook will be released and deployed!

### Contributing Guidlines

If you want to make a quick typo fix or a quick formatting fix, make the pull request and it should be resolved soon.

Otherwise, you should probably make an issue first to see what either the course staff or the professor has to say about it. 
Examples of something like this could be adding a new chapter, adding a substantial amount about some topic, adding more "fun examples", or changing the build system.


## Building

### Build dependecies

On linux, you will need the following prerequisites:

* A latex compiler (`sudo apt install texlive-full` is an overkill solution to get all packages required in recent debian/ubuntu distros)
* Make
* inotify-tools (`sudo apt install inotify-tools` on recent debian/ubuntu distros)

To build this project, we have provided a make file and a rebuild script. To compile the latex, just run `make` from the root of the project. If you'd like the project to automatically recompile as you make changes, run `./rebuilder.sh` instead.

By default, `./rebuilder.sh` will create a new file in /tmp and will re-use it every time it is ran for logging purposes. If a command line argument is specified, `./rebuilder.sh` will treat the argument as a path and will use that as its logging file instead.

### Scripts


## Documentation, Structure

- All directories that don't start with `_` are a chapter in the wikibook
  a chapter is a tex file with bib files and optional images
- `github_redefinitions.tex`
- `glossary.tex`
latexmk.out
- `latexmkrc` configuration file for latexmk.
- `LICENSE.code` Licenses all the code in the book
- `main.pdf` The PDF version of the wikibook
- `main.tex`
- `Makefile` Tried and true makefile for buildings. We don't need ya fancy build systems
- `order.tex` This file is autogenerated from the `order.yaml` file so that the actual ordering of the chapter stays in one place
- `order.yaml` This file controls the ordering of the chapter. Changing this and typing make will cause `order.tex` to be reformatted.
- `prelude.tex` contains all of the includes and definitions before the start of the document in main. This is a different file solely so that we can accurately convert each chapter with pandoc. More in the `_scripts/gen_wiki.py`
- `rebuilder.sh` Efficiently autobuilds the files for maximum productivity
- `requirements.txt` python requirements if you are building the `wiki` version of the wikibook
- `_scripts` This folder contains various scripts to do different things like generate the wiki, spellcheck etc.

