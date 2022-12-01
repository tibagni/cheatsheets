# Ctags
## Install
```bash
$ sudo apt-get update && sudo apt-get install -y exuberant-ctags
```
### Install without sudo
1. Download ctags source: http://prdownloads.sourceforge.net/ctags/ctags-5.8.tar.gz
2. Extract, compile and install in the home directory
```bash
$ tar zxf ctags-5.8.tar.gz
$ cd ctags-5.8
$ ./configure --prefix=$HOME
$ make && make install
```
4. ctags is installed under `$HOME/bin`, make sure to add it to `$PATH` in .bashrc or similar
```bash
export PATH="$HOME/bin:$PATH"
```
## Resources
* https://courses.cs.washington.edu/courses/cse451/10au/tutorials/tutorial_ctags.html
* https://kulkarniamit.github.io/whatwhyhow/howto/use-vim-ctags.html
* https://ctags.sourceforge.net/
