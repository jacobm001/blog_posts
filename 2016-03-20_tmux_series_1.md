**Author:** Jacobm001

**Publish Status:** draft

**Suggested Tags:** raspberrypi, raspbian, tmux

# Tmux 101: Installing from Source

In last week's post, I mentioned that we'd be starting a series on [Tmux](https://tmux.github.io/). I've already mentioned installing software using the package manager (`sudo apt-get install tmux`), but this article is going to go over how to install it from the source.

## What is Tmux?

Tmux is a "terminal multiplexer". In short, it allows you to have multiple "windows" in the same terminal; if desired, the windows can then be split into "panels" that allow you to have mutliple terminal inputs visible at the same time.

## Why install from the source? Isn't the Repo good enough?

In most cases, the repository is adequate for the average users needs. It is however, imperfect. The repo doesn't contain all the software that you may want to install (large as it is), and that software is often significantly behind the current version.  Now, there's often good reason for this. Software in the repository has been pretty thoroughly tested and you can be reasonably sure it's not going to break your system. Both of those factors take time, and mean that the repository can't necessarily guarantee the most recent version of the software in question.

If the software in question is missing features that may be found in a more current version, you may want to install from source.  In this case, the repository has version `1.7`, but the most recent release of tmux is `2.1`. 

## Installing:

### 1. Installing Dependencies

The first thing we'll need to do is install some dependencies. As the homepage specifies, tmux relies on the libraries, [libevent](http://libevent.org/) and [ncurses](http://invisible-island.net/ncurses/). We can install these by using the commands[^1]:

	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install libevent-dev libncurses5-dev

### 2. Getting tmux

Now that the dependences are installed, we can download the source code for tmux. Download and unzip the source using the commands[^1]:

	wget https://github.com/tmux/tmux/releases/download/2.1/tmux-2.1.tar.gz
	tar xfa tmux-2.1.tar.gz
	cd tmux-2.1

In case you're unfamiliar with what you just did, `wget` downloaded an archive file containing the tmux source code. `tar` is then used to extract the files[^2]. Finally, `cd` changes the pwd to location where we extracted our files.

### Compiling tmux





[^1]: These commands work on Raspbian and most Debian based operating systems. If you're running a different OS, like Arch, you'll need to use that distribution's package manager instead.

[^2]: The flags as follow are:
- `x`: extract
- `f`: read from a file
- `a`: automatically detect the type of archive (`gz`, `bzip2`, `lzma`, etc)