# docker-chrome

Docker Image packaging for Chrome

## Update the images

Run the script to update the images:

```
./update.sh chrome70 chrome69
```

## Develop

### MacOS

#### Install Homebrew

First, visit Homebrew homepage and follow the installation instructions to install Homebrew.

Then add the following line to your `.bashrc` or `.zshrc` or `.profile` file:

```
PATH="$(brew --prefix coreutils)/libexec/gnubin:$PATH"
```

#### Install the GNU Command Line Tools

First comes the most important one

```
brew install coreutils
```

GNU Coreutils contains the most essential UNIX commands, such as ls, cat.

Then you may probably want to install the following ones (For some of the packages, you need to run brew tap homebrew/dupes first, but only once for your system):

```
brew install binutils
brew install diffutils
brew install ed --with-default-names
brew install findutils --with-default-names
brew install gawk
brew install gnu-indent --with-default-names
brew install gnu-sed --with-default-names
brew install gnu-tar --with-default-names
brew install gnu-which --with-default-names
brew install gnutls
brew install grep --with-default-names
brew install gzip
brew install screen
brew install watch
brew install wdiff --with-gettext
brew install wget
```

Homebrew is prepending a g to each of the newly installed commands, thus we could use these commands as default commands over the ones shipped by OS X.

```
ln -s $(which gsed) $(brew --prefix coreutils)/libexec/gnubin/sed
```

In addition, some GNU command line tools already exist by default on OS X, but you may want a newer version:

```
brew install bash
brew install emacs
brew install gdb  # gdb requires further actions to make it work. See `brew info gdb`.
brew install gpatch
brew install less
brew install m4
brew install make
brew install nano
```

You may also want to add $HOMEBREW_PREFIX/opt/coreutils/libexec/gnuman to the MANPATH environmental variable, where $HOMEBREW_PREFIX is the prefix of Homebrew, which is /usr/local by default.
