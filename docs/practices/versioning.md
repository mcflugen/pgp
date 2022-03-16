# Version Control


## Version Control Systems (e.g. git)

Even if you are a developer writing a piece of software by yourself, you should
be using a version control system. Today the most popular system is git (and
GitHub) and, although a quick glance at the documentation may make a new user
nervous, the basic idea is relatively straightforward and easy to understand. A
typical workflow really only requires knowledge of a few basic commands. A
typical workflow might look like the following:
* You change one or more files, are happy with the changes, and would like to
save those changes
* You commit the changes with a brief message that describes the changes
* You push those changes to a git server (e.g. GitHub) for others to see
* You pull changes from GitHub that other developers had committed and merge them
into your local version

There are, of course, more details but these are the basics.


There is one more practice we would like to leave you with that will help make
you a more effective git user. Always work from a branch—making commits to
this branch until you have a group of commits that are ready to merge into the
main branch of your repository. This has several benefits. Your changes will be
isolated to your branch and will not affect other people working on your
software. You are free to make changes, undo those changes, and break things as
you home in on a solution. Once you are satisfied your contribution is ready to
be incorporated into the main development branch of the code, you can merge it
as a single organized thought (perhaps as a pull request if using github and
after a code review). Because you will only merge your changes after all of
your software’s tests pass (see section on testing), you will be confident you
haven’t broken anything. This ensures that your main branch will always contain
a stable version of your software. 


Your modifications will be merged as a group of changes that solve a problem
(e.g. fix a bug) or add a new feature. Because they are merged as a group, it
will be clear to others why you made all of those changes.

% How often should you commit? Early and often.


## Versioning of software releases

Related to version control is the versioning of software releases. This is the
version number that is attached to snapshots of the software’s source code and,
although a version can be any string, typically it is three numbers separated
by a decimal (i.e. X.Y.Z). Whatever format you use, the most important thing is
that it must be easy for someone else looking just at the version string and be
able to tell newer versions from older.


As with version control, using a well-defined versioning system is important
even if the total number of users is one (you). Stamping versions of the
software allows your users to know exactly what version of the code they are
using, which is useful for several reasons. When users discover bugs or have
questions about the code, they are easily able to communicate to you what
version of the code they are using. When trying to run a simulation or analysis
that uses the software, a version number can be recorded so that the analysis
is reproducible. A version string doesn’t just help you but also communicates
information about your project to your users. If you follow a well-defined
versioning system, the version string can give your users a brief synopsis of
what has changed without having to dig through your change log. 


A popular versioning system is Symantic Versioning. Symantic Versioning assigns
meaning to the different parts of the version string, which then communicates
to your users what has changed since the last version. Under this system, a
version number is divided into three components, MAJOR.MINOR.PATCH, where each
component is an integer (e.g. 3.14.159). An increase in the PATCH number
indicates the software has seen one or more bug fixes, an increase in the MINOR
version indicates one or more new features, and if the MAJOR version changes,
there has been a large enough change that the software is no longer backward
compatible. For many pieces of research software, it may not be necessary to
strictly follow a versioning system like Symantic Versioning but all software
will benefit from some form of versioning.


A note about Semantic Versioning or similar systems. In Symantic Versioning if
the major version number is 0 (e.g. 0.2.718) this indicates that your software
is in beta meaning that the developers have not yet decided on a standard
interface and so may change things in such a way that may break backward
compatibility. Because of the freedom this offers, there is a tendency for
developers to want to stay in 0-version. Try not to do this where possible—your
users will appreciate it. Users who rely on your software will quickly become
frustrated if new updates begin to break their code. Even if version 1.0 isn’t
perfect, consistency will make up for it. Your software will also benefit from
moving to version 1.0 as it will force you to spend time carefully considering
your design, which you should be doing anyway. Staying in a beta version is the
easy way out, instead, make decisions, stick with them, and enforce
consistency. Everyone will be happier and better off for it.

