# Packaging and Distribution


Most likely the main audience of your software will be users—not
developers—and, as such, will not be willing to invest a lot of time and effort
into installing your software onto their own computer. Even for well-seasoned
developers, compiling software can be time consuming and cause many headaches.
Since new users will need to build and install your software before they can
take it for a trial run, before they know if it’s worth getting to know, the
installation process should be as easy as possible. To accomplish this, use a
package manager whenever possible. Although the package manager you use may
depend on the language your software is written in, choose one that is easy to
use, contains packages for you dependencies, and is familiar to your users.
Ideally, users will use a package manager to install your software, and all of
its dependencies from an online package repository. Your users will not need to
compile your software or that of any of your dependencies and will be available
for a range of platforms (Linux, Mac, Windows, etc.).


We have found that the conda package manager, which comes with the Anaconda
distribution to be a good choice as it contains thousands of user-contributed
packages from a range of languages (Python, C, C++, Fortran, R, and others).


Another benefit of conda is that it will allow you to install pre-built
packages in whatever directory you wish on your computer. This gives your users
a lot of flexibility in how and where they install your software. Since they
can install everything in their home directory, say, installing your package
just to try it out becomes low risk—they don’t need to install as an
administrator—and fast—they don’t need to wait for an administrator with the
necessary privileges to install the software.


Along these same lines, your code should never contain hard-coded paths or make
assumptions about the directory structure of your users computer—the directory
“/home/jcleese” may exist on your computer but it’s unlikely to exist on anyone
else’s. Your users should specify these sorts of parameters programmatically,
as a command line argument, or through an input file.


One overall theme of these rules is to make it as easy as possible for a new
user to get acquainted with your software: easy to find, easy to install, easy
to try out. If a new user encounters even a small amount of friction in any of
these steps, they will likely move on and leave you with one less user and—more
importantly—one less user-contributor.

