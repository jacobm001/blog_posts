**Author:** Jacobm001

**Publish Status:** draft

# So you want to install _______

One of the most common questions I see on the Raspberry Pi StackExchange regards how to install a specific piece of software. While often straightforward, the question can be much more complicated than one might be used to.

In this post, I'll try to explain the basics of why some software simply can't be installed on the Raspberry Pi. In the next post, I'll be starting a series on using [Tmux](https://tmux.github.io/). The first post in the series will be about installing the latest version from source, rather than using the package manager. 

## Processor Types

By far, the most common problem we see is when a user wants to install a program they use on their `x86` desktop. This isn't usually possible, because all Raspberry Pi models (at the time of this writing) run some variation of an `ARM` processor. Since these are fundamentally different, a binary application can't be dropped from one machine to another.

### Wait, what!? Isn't a processor a processor?

Yes, and no. A processor (aka a CPU), is what does the computing within a computer. Each processor has a fundamental *archiecture* type. In desktop, laptop, and servers the most common architecture used is `x86`. Your phone, laptop, and cable box almost always contain an `ARM` processor.

To simplify the different a little, think about the languages humans speak. A book can be written in English, French, and German. If a person only speaks English, giving them a book written in German is useless to them. Sure, the book has meaning, but they can't understand it.

### How about virtualization? Could Qemu run my program?

Maybe, but it's probably not worth it on the Raspberry Pi. `x86` processors are significantly more powerful than any `ARM` processor. They have much more advanced instruction sets which allows them to be much more efficient. Your desktop could emulate the RPi with ease, but it's not going to be so easy going the other way around.

## So how do I install programs?

For open source tools, the solution is often fairly simple. Many projects will host an `ARM` binary, and/or it's available through your distrobution's package manager.

In Raspbian, this is accomplished using `apt-get`. To install vim, the command `sudo apt-get install vim` will automatically install not only vim, but any dependencies that vim requires to run*.

If you're not sure what the package is called you can search through the repository using `apt-cache search vim`. Notice that you don't need administrative rights to run the search!

For the other open source projects, you can download the source and compile it yourself. You may want to do this if the version in the repository is older than you want, or it simply isn't in the repository. We'll go into more detail on this in the first post of our Tmux series.

*Note: Always run `sudo apt-get update` before installing an application. Otherwise you might install an older version than you want.
