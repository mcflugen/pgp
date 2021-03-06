# Standards

Wherever possible, rely on existing standards. Maintaining a software
package—or set of packages—is a difficult task, and is even more difficult for
the typically small teams we see developing scientific software. There is not
an army of software testers, a battalion of documentation writers, or a troop
of software developers assigned to your project. No, there is just you. As
such, you will want to optimize your workflows as much as possible, which means
relying on standards as much as possible. Standards allow you to tie into a
wider range of existing tools to help you with the day-to-day maintenance of
your project, and make your project more accessible to new users and
contributors. Both of which will make your life easier and your software
better. If you ever find yourself creating a bespoke solution to a
problem—whether it be building documentation, loading configuration files,
writing data files—ask yourself if there isn’t already an existing standard
that you can use.


## Project organization


A well crafted piece of software will be a well organized piece of software. If
you follow standard practices of project organization, users new to your
software will immediately know where to look for the files they are interested
in without having to consult your documentation (once again, by relying on a
standard, you are able to write and maintain less documentation for your
users). As with other advice we have provided, the exact organization of files
will depend on the programming language you are using but, whatever the
language, there will be a standard project layout. Take the time to figure out
the standard organizational structure for your language and stick with it. The
file structure shouldn’t be complicated and will seem natural.


To use Python as an example, one possible structure will be to have at the
top-level folder: a “setup.py” file, which contains project metadata and a
means of installing your package, a folder that contains your package’s source
code, and a tests folder, which holds your project’s unit tests. There are
resources you can consult to get a fuller picture of what a well organized
Python project tools like—we’ve outlined just the basic layout—as well as tools
that will help set up your project for you.


## Language-specific standards


Stick with the norms of the programming language you are using. These may be
things like conforming to a particular coding style—CamelCase or snake_case for
variables, for example. These are things that won’t prevent your code from
running but will make it easier for others to read and understand. In Python,
for example, it’s customary to use snake case for variable names but camelcase
for class names. Knowing this allows you to glance at a snippet of code—even
out of context—and orient themselves to get an idea of what they are looking,
and what it does without having to scan back through other files to try to
discover, for example, if a name is referring to a class or an instance of a
class. To eliminate this sort of confusion is the one the reasons a standard
was made for Python (as expressed in PEP8). Python is a good example to use
here. By design, it is a flexible language—in that it doesn’t impose a
particular style—but yet it’s author felt the need to provide a set of style
guidelines that would codify the norms for a community. Other languages will
have similar standards (and if they don’t, create your own! Just be sure to
stick with whatever “rules” you come up with. Maybe even publish them somewhere
and, who knows, maybe they will become a community standard!).


Examples of other standards:
* C++/C: gnu, google, etc
* Fortran?
* Python: PEP8
* Java


## Interfaces


Just as with file formats, when it makes sense to do so, reuse existing
interfaces. They will be familiar to your users, they will require less
documentation, you will write and maintain less documentation, and your
software will more easily tie into existing tools. Your software will have
several interfaces to consider. One is, as we have mentioned, input and out
files.


For your end users, this will be the primary way they will interact with your
software but, as we have already discussed this topic, we will not say anything
more about file standards.


Another way a user may interact with your software is through its command line
interface. We will discuss command line interfaces in more detail in another
section but we note here that there are, once again, standards to fall back
on—particularly when running on Unix-based systems. A well-behaved command line
interface has several characteristics.
* Standard options for help and version
* Verbosity level
* Reads from standard input if passed a dash as a file name argument
* Options are optional, arguments are not. There shouldn’t be many options. The
  options for a model simulation—like model parameters—should be kept in a config
  file.
* Error messages and status is written to standard error. This includes all
  messages to the user.
* Output, which can be sent to another command, is sent to standard output.
* If nothing is passed as an argument, it does nothing but doesn’t report an
  error
* Exits with 0 unless an error occurred. If an error occurred, then exit with a
  non-zero integer.


## Build process


Every software project needs to turn code into action. The way you do this will
depend on the language your code is written in-for compiled languages like C or
Fortran, for instance, this means running your code through a compiler to
convert it to a language your computer can understand. This step is undoubtedly
a critical step and is one that you will likely take thousands of times and one
that new users of your software will struggle with. For new users (or perhaps
more precisely user-developers) of your software, this will likely be their
first introduction to your code and if not the hardest step toward running your
software, it certainly has the potential to be the most frustrating. Speaking
from experience, the last thing users want to do is mess with compiling code
and trying to divine the magical collection of compiler flags necessary to get
your software to build on their computer.  The person who takes pleasure in
compiling code is indeed folkloric and, if they are ever to be found, I’m
certain they can’t be trusted. Your users don’t want to compile code, they want
to run models and do science.


This is a long way of saying you should strive to make your build process as
easy as possible. One way to do this is to rely, once again, on standards.
Although the details will depend on the programming language you are using, a
discussion using examples from specific languages can still be valuable.
Although there are others, two standard build tools for building software
written compiled languages—C, C++, and Fortran, for example—are cmake and
autotools (a collection of tools that includes the unix utilities autoconf and
automake). Both of these tools create a standard “Makefile” but do so in
different ways (as a side note, these two tools are themselves examples of
software that rely on a standard—the makefile. Both tools generate a makefile
that a user uses in the standard way to build and install their software). If
you have a choice, steer clear of autotools—it’s confusing, difficult to learn,
platform dependent—and, instead, use cmake. Cmake can build projects on both
Windows and Unix-based platforms, and uses what can loosely be described as a
"programming language" (unlike autotools) that isn’t difficult to learn.


There are standard ways to build projects in every language. Python, for
example, uses setuptools, a setup script (setup.py), and a standard project
layout but other languages will have their own standards. When you rely on a
standard build process, it will more likely be already familiar to your users.
They won’t be slowed by have to consult your documentation and you won’t be
slowed by having to create custom documentation for your project. Instead, you
can simply point your users to the standard documentation maintained elsewhere.
Again using Python as an example, the latest build and packaging procedures are
maintained by The Python Packaging Authority, which has great up-to-date
instructions. Regardless of the language your software is written in, become
familiar with its standard and stick to it. Both you and your users will be
grateful for it.


## File formats


The standardization of file formats provides opportunities for increased
efficiency. In many scientific software applications, developers tend to create
their own idiosyncratic file formats—both for input and output files—when a
standard file format would do just fine.


It is common for software models to have at least one text configuration file.
Such files typically list model parameters for a specific model simulation—the
number of iterations to run, the size of the time steps, values for physical
parameters. Standard file formats such as yaml or toml are ideal for these
situations. They are text based (so easy to put into version control), they are
easily read by a human, are built to describe configuration data
structures—i.e. dictionaries or hash tables—and, importantly, libraries already
exist in most languages that read from and write to these formats. Of course
new formats come and old formats go-the above formats we have suggested here
may not exist when you read this-regardless, there will most certainly be a
standard format for configuration files. Don’t worry about supported a variety
of standard formats, picking one is fine. So long as it is standard, your users
will be able to use existing tools to convert between formats. By using
standard formats you have both made it easier for your users to use your model
as well as provide an easy to access entry point for them to contribute to your
software. By using off-the-shelf software they could, for example, create a
plugin for your model to read from a different standard file format.


All of the arguments we have used for promoting the use of standard file
formats for configuration files also applies to data files. Where configuration
files are text-based and typically used to static parameters for a model
simulation, data files often contain time series data that may also be
spatially variable. Examples include a time series of the water discharge for a
stream or a digital elevation model of a watershed. Although the text-based
formats we suggest for configuration files are inadequate for this type of
data, there are other standard formats to choose from. Some popular formats
include netcdf, or csv. Although a powerful and flexible format, netcdf can
also be somewhat cumbersome to work with and, being a binary format, requires
specialized tools to work with. When choosing a data file format, try not to
overthink things—where a simple format will do, go with simplicity. Your users
(and you) will appreciate the simplicity of a simple CSV text file that they
can open with any text editor and see interpret the data with their own eyes.
And, being a standard format, can be read into most any visualization software
and plotted. More complicated formats—like netcdf—certainly have their place.
They are efficient (by compressing data they are able to store lots of data),
they are flexible (a wide range of data structures can be stored—structured
data, unstructured data). As we have mentioned, this power comes with the cost
of a loss in ease-of-use but with larger, more complicated datasets, the
benefit outweighs the cost. Although netcdf is a standard and commonly used
format, there are other standard formats suitable for storing large data sets.
When making a choice, also consider not just the broader use of the format but
also if there is a standard format that people use in your specific field of
study. If there is a standard format your users are familiar with, you should
give that some weight in your decision. Recognize, though, that your choice may
make it more difficult to integrate your software with a broader community.


We should note that there is a difference between a data format (like netcdf or
csv, say) and how data are represented in that format. Netcdf is a general
format that can store a wide range of data and the way data can be stored is
just as wide. This is the difference between a format and a schema. As a simple
example, consider a csv-formatted file that contains a time series of daily air
temperature at some meteorological station. One obvious way to store the data
would be as two columns of numbers with the first column being day of the year
and the second being temperature. Another way would be to list the data in
rows-the first row being measurement dates and the second row the temperatures.
Both csv-formatted files, both temperature data but represented in different
ways. To solve this problem, again, look for standards. In your field, is there
a standard way people record this sort of data? If so, that’s likely the way to
go. If not, make good use of metadata to indicate how the data are represented.
In our example, for instance, you could include a header line that labels each
column and contains units for the data.

