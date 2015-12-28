# tutorials

## Requirements

### Ubuntu <= 12.04

Add the texlive-backports PPA and update the repositories:
```
$ sudo add-apt-repository ppa:texlive-backports/ppa
$ sudo apt-get update
``` 

### Installation

Install texlive and required packages:
```
$ sudo apt-get install scons texlive texlive-latex-extra texlive-science
``` 

## Compilation

You can compile all the PDFs under this folder simply by running:
```
$ scons && scons -c
``` 
