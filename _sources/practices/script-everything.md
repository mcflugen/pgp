# Script everything


If you are going to do something more than once, consider writing a script to
do it. There are two resons for this. The first is obvious, it will likely save
you time in the future and will make the task less error prone. Of course, in
reality, there is a balance to be made: one one side of the scale is the time
it will take you to complete the task be hand multiplied by the number of times
you will carry out the task, and on the other side is the time it will take you
to write the script to automate the process. Which side wins out depends on
your particular situation but it is our experience that scripting almost always
wins out.

A second benefit of scripting everything is that the script provides a
definitive record of what you did. Thus, following the script someone else will
be able to replicate what it was you did. This could be particularly useful in
light of the difficulty of reproducing model results. Your script should be
written in such a way that another person in your working group should be able
to pick up your script and reproduce your results. I’m fact, having some in
your group do this, is a great idea. These sorts of scripts-those that test
your model as a whole-should be a part of your automated black-box testing (see
section on continuous integration).


How to write a script. You can write scripts in a number of languages. Some
popular scripting languages are bash, Python, and makefiles but the language
doesn’t really matter so long as it is easily available and with few extra
dependencies. If your software is written in Python, then Python would be a
good choice. Otherwise, a shell scripting language-like bash or ash-might be a
good choice as they are  commonly available and are useful for creating
workflows that interact with the operating system. Another  easy way to script
a simple task is by using a makefile to create a simple command line interface
to do lots of stuff.


A side effect of this (or perhaps a corollary?) is that you should use standard
input and output files (straight text files, csv, etc., no excel files)

