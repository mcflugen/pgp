# An Approach to style


No matter the size of your project or the size of your team, your project will
benefit from well written, high quality code. Scientific software, as we have
noted, is often prototype software that has been written hastily in an attempt
to answer a scientific question as quickly as possible. It is not (ordinarily)
the job of a geoscientist to sculpt well-crafted software. By following a few
simple rules, however, anyone can write well-crafted code. Not only will you
have code that is a pleasure to look at, your code will have less bugs, be more
efficient, and easier to maintain. Well written code will be more robust, more
persuasive, and will, in fact, lead you to those discoveries faster.


You are not a software engineer. At least not yet. Even though you may not know
how to write high quality code, we suspect you know what it is when you see it.
Or, maybe more importantly, you’re probably intimately familiar with what
poorly written code looks like and how difficult it can be to work with. When
starting out, a team can sometimes move at a sprint while disregarding code
quality; the sprint doesn’t last and progress slows to a crawl and the code
base becomes a twisted mess. In this section we provide a few easy-to-implement
practices that will help you and your team write higher quality code.


Write small, isolated blocks of code. Functions should be short—if the entire
function cannot fit on your screen it’s too long—and do just a single job.
These are the paragraphs of your code—a topic sentence (function name), with
subsequent sentences (function body) that lead to a conclusion (return value).
If someone asks you what your function does and in your response you use the
word “and”, it may be too long. Short functions are easier for a reader to
understand, they are significantly easier to test, and they can more easily be
refactored (for instance if implementing a new algorithm).


Use as few input parameters as you can—ideally just one or two. As you add more
input arguments, your tests become significantly more difficult to write since
the number of combinations of input parameters increases non-linearly.


Use sensible and descriptive names for variables and functions. Modern
programming languages no longer limit us to using short variable names so
neither should we. Use, instead, descriptive variables names of whatever length
makes sense. Most code editors will auto-complete variable names as you are
typing them so, again, length should not be a concern. Some additional best
practices when naming variables:
* Choose variable names that are pronounceable. Humans will be reading your code
  after all.
* Choose variable names that are searchable. Although a variable named “t” might
  make sense in some instances (as an example, perhaps “t” is a commonly used
  variable name in an equation), it makes it difficult to search your code for
  all occurrences of its use. A better name might be, for example, “time”. Even
  worse, as far as single letter variables go, are letters that are nearly
  indistinguishable from one another like “l” (lowercase “L”) and “I” (uppercase
  “i”). Some single character names are ok. For example, “i” and “j” are
  acceptable names when used as loop counters since those names are traditionally
  used in that context.
* The name of the variable should tell the reader your intent for the variable.
  Here is a good rule of thumb: if you feel like you need to add a comment next
  to a variable’s declaration, you’ve probably chosen a poor name.

An overriding goal for crafting high quality software is to allow the code to
speak for itself. Someone should be able to look at your code and read it
almost as though they were reading prose that describes what the code is doing.
As a goal to yourself, try not to rely on comments by letting the code speak
for itself. Comments certainly have their place—describing why you used a
particular algorithm for example—but they can easily be overused. Overly
commented code is difficult to read, and can easily become out-of-date as soon
as someone changes the code but forgets to change the associated comments. A
misguided or incorrect comment is significantly worse than no comment at all.


In software engineering there are many useful design patterns. Much like an
architect building a house who, when faced with a design problem, can turn to a
well known set of design patterns that solve their problem. One such design
pattern (or, perhaps, a set of design patterns) we have found to be useful for
writing easy to use software models that can be coupled to other software
models is the Basic Model Interface (BMI). Although the BMI is a well-defined
interface, it can also be thought of as a design pattern.


Model software should be structured in such a way that it provides entry points
that allow a user or another piece of software to access important aspects of
it. This design has several benefits. First of all, it provides a standard way
for running a software model. This means that once a user learns to use one
model, it will be easy for them to familiarize themselves and use any other
model that follows the same design. We think of this much like the design of a
car. When you climb into the driver’s seat of a car—even a car you’ve never
been in before—it will be familiar to you and, assuming you know how to driver
a car—not necessarily this car—you’ll have a pretty good idea of where
everything is, how to start it, how to drive, and how to stop it. 


The software model design pattern is composed of three categories of functions:
* Getters: functions that get information about your model. This information
  comes in two types: static (e.g. the name of your model) and dynamic (e.g.
  values of a quantity that changes as your model evolves).
* Setters: Functions that change values inside your model. These functions
  provide a means for you to control how another piece of software can change the
  value of a quantity used by your model.
* Controllers: Functions that control the execution of your model. The functions
  allow another piece of software to start up your model, move it forward, and
  shut it down.

The Basic Model Interface goes one step further by formalizing this design
pattern by defining a set of functions on which a software model can be built.
The BMI precisely specifies both function names and signatures. Implementing a
Basic Model Interface for your model should be a goal but, if that seems too
daunting starting out, simply designing your model so that it provides getters,
setters, and controllers will go a long way to making your software easier to
use, maintain, and couple.


Much like writing a paper, well crafted code doesn’t immediately spill from the
keyboard. It may be a slow process at first but don’t let but don’t let the
guidelines we have presented slow you down. You will be able to refine later.
As with writing a paper, there will be first drafts, followed by edits,
followed by a second draft, and more edits until you reach a final draft. The
first draft will be messy and break most of the rules, but knowing the rules,
you will be able to home in on a final draft by refactoring code blocks here
and there—making sure your tests continue to pass with each iteration—and,
before you know it, you will end up with code that is understandable,
maintainable, and tells the story you want to tell.


## Consistent coding style


Although at first it may seem like a trivial point, choosing and sticking to a
uniform coding style can make a significant difference to the ease with which
you are able to collaborate with others on your project. There are many tools
that automatically scan your code to ensure that whatever coding style you have
chosen—and it doesn’t really matter what style you’ve picked so long as you’ve
picked one—is being followed. As such, this is a fairly easy goal to reach.
It’s not so much the style that’s important but, when everyone on your project
contributes changes that look alike, incorporating changes becomes easier. Code
that follows a consistent style becomes easier to read and patterns are more
easily identified, superficial changes to lines are eliminated when looking at
differences between commits, and everyone’s code looks alike. This all
contributes to making code review faster and easier.


## Software reuse and dependencies


Where possible, reuse software. There’s no need to build a wheel if someone
else has already built one, except when there is a need. Perhaps the other
person’s wheel is fragile, or not round, doesn’t come with a warranty, or has
been sitting in the back of the garage, untouched, for years gathering cobwebs.
Reusing software often makes a lot of sense—you don’t have to write, test, and
maintain the software yourself—but, when adding a new dependency to your
software, you should give it some thought. After all, this dependency will form
part of the foundation upon which your software is built and, if breaks or
changes, your software package could collapse. Some things to consider when
using a wheel that someone else has built:
* Is this software being actively developed?
* How many contributors are there to the package?
* Is the package fragile? Is it well tested? What about its dependencies?
* Is it available on all of the platforms you want to support?
* What benefit does it provide to my package?
* What harm does it do to my package? For example, is it difficult to install and
  will it make it difficult for users to then install my package?
* Do I have a plan to prevent my software from collapsing if this package breaks?

Typically, the answers to these questions will lead you to conclude that it
probably does make sense to use the package. But not always and it’s important
to give this some thought.

## Command line interface


As a general rule, I prefer to use input files over command line arguments for
specifying input parameters to a program. In fact, the fewer command line
arguments the better. There are several reasons for this, which fall into three
categories: simplicity of design, reproducibility, and software reuse. There
is, of course, a balance between making things as easy as possible for your
user and making things as easy as possible for you, the developer. We must not
overlook the fact that making things easy for the developer will usually
translate into better, more robust code, which will, in turn, make things
easier for the user.


When designing a user interface, there is a tendency of the engineer to
over-design things—with the noble intent of giving a user a maximum of
flexibility and power as possible—often, unfortunately, to such a point that
both user and developer become overwhelmed. From a developer’s perspective,
every new bell, whistle, or dongle added means more code—more code means
greater potential for bugs—and more testing. It should be noted that for every
bell added, it is not sufficient to add one more test. No, to properly test
your interface you will need to add tests that make sure your new bell works
with all of the other combinations of existing bells and dongles. This can
quickly add up!


By removing some of the flexibility from the interface, your users may have to
do some additional tasks themselves, but overall your software becomes more
robust and easier to learn to use—fewer options means a more streamlined piece
of software that is more targeted—it does what it does and no more. Oftentimes
the extra accoutrements an engineer may want to adorn their software with are
better done by the operating system anyway.


Instead of adding more features to your software, make your software conform to
standard input and output formats so that it can more easily interact with
other pieces of software that are better suited for their particular task. For
instance, instead of making your software generate beautiful plots of generated
data, ensure that the generated data can easily be read into well-established
visualization software. The same can be applied to input. Instead of
programming to a wide range of input data formats, target one or two specific
commonly-used formats. If a user wants to use data from another format, which
is not supported by your application, they can use existing data converters to
transform from one format to another. Instead of programming to the wide range
of potential formats that a user’s data may come in, program to a standard
interface. This will allow user-contributors to easily write extensions to your
application for reading and writing to other formats. This also saves you time
of writing these extensions before you know if they will actually be used. You
might think someone will require this functionality but, without knowing with
certainty, you end up spending time creating something nobody will use.
Premature optimization may not be the root of all evil in programming but it
certainly can be a time sink. Instead, write extensible (extendable?) software
with these sorts of potential use-cases in mind.


Relying more on input files rather than an extensive list of options to a
command line interface also lends itself to reproducibility. If a user comes
across a folder that has one of your standard input files, and standard output
files, that user can be fairly certain the two go together. If parameters are
passed as options on the command line, it is not clear what set of parameters
generated the output. There are, of course, ways around this problem—input
parameters could be embedded in the output file or a separate parameter file
could be generated as part of the output—but most of these solutions add
unnecessary complexity. Also, a set of input files can be easily placed in a
version control system, without the generated output, and then rerun to
generate the output files, which need not be under version control.
