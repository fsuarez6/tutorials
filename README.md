# tutorials

## Requirements Ubuntu 12.04

### Texlive

Add the texlive-backports PPA and update the repositories:
```
$ sudo add-apt-repository ppa:texlive-backports/ppa
$ sudo apt-get update
``` 
Install texlive and required packages:
```
$ sudo apt-get install biblatex sketch texlive texlive-generic-extra texlive-humanities texlive-latex-extra texlive-publishers texlive-science
``` 

### Python modules
Some scripts require the following modules:
```
$ sudo apt-get install python-pip python-numpy python-matplotlib
$ pip install matplotlib2tikz --user
``` 

## Compilation

For compiling LaTeX I prefer `scons`. Install it:
```
$ sudo apt-get install scons
``` 

You can compile all the PDFs under this folder simply by running:
```
$ scons -Q && scons -c
``` 
