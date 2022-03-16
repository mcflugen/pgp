# Pretty Good Practices in Geoscientific Model Software

Scientists are becoming more reliant on software than ever before for their
research. And not only as users. They now also find themselves developing and
maintaining their own software. Much of this software ends up being written by
scientists who are neither trained as software engineers nor have time to learn
the trade of software engineering. Instead, the foremost concern of a scientist
is to do science, publish papers, or write a thesis and graduate.


Software maintenance becomes even more important when we notice that often it
is graduate students and postdocs—whose tenure with any single group is
limited—who are writing software. Inevitably, the authors will leave the
research group but the software will stay to be picked up by the next
generation. A result of these factors is that much of the scientific software
generated within this environment becomes a mess.


The good news is that there is a relatively small set of practices that a
writer of scientific software can employ to make their software less fragile
without having to become—or hire—a full-time software engineer. Our aim here is
to provide guidelines for developing and maintaining research software that is
robust and sustainable across changing developers—as is often the case within
research groups that rely on graduate students and postdocs for software
development. Our guidelines fall into four main categories: versioning,
documentation, testing, and design.


How important is well written code? After all, all that really matters is that
the code is bug free and does what it’s intended to do. That’s true, of course,
but consider the analogy that a software model is like a scientific paper. When
you write a paper for a journal, you want your text to not only be free of
grammatical errors but to also tell a clear story that someone else can follow
and even reproduce. Your code should live up to the same standard. When someone
picks up your code they should be able to clearly see the story you intended to
tell and then be able to reproduce it. Your software—unlike the journal
article—will be a living document onto which others will want to extend
directly upon, which is all the more reason to be clear and concise. 


As a model developer, how much time do you spend reading code vs writing code?
If you are like most people, you spend significantly more time reading code
than writing code. Sometimes it is reading code written by others, but it might
also be code written by your past self; either way, though, you will be
grateful to be scouring through code that is easy to read and to understand.
Not only will it be more enjoyable and less frustrating but it will make you a
more effective and efficient programmer. This is why writing good, clean, clear
code is so important.


We would like to be clear that the practices we present here are guidelines,
not commandments to be followed blindly. Our advice is based on decades of
experience developing scientific software and are practices we have found to be
valuable and to work in practice. This is certainly not the last word to be
said on the subject and there are undoubtedly other ways to achieve similar
results. You may even think we’re out to lunch with some of our advice. That’s
ok. We hope that we will at least leave you with some food for thought so that
you can be more intentional with the way that you write software.


In the following sections, we will provide specific practices that you can use
to craft durable code that will withstand the test of time. If we were,
however, to distill these guidelines into just a few guiding principles, they
would be to: write code that favors simplicity and readability (even if it is
occasionally at the expense of optimization), use automation whenever possible
(and it’s almost always possible), and use existing standards wherever you can.


When you write scientific software it is often in an environment that focuses
on the generation of output (graphs, papers, etc). This makes sense—after all
we’re funded to do science—but is often at the expense of documentation,
maintenance, testing, and reproducibility. Moving quickly in an effort to get
results will just as quickly build up a large amount of technical debt and this
debt compounds with time. Without a software philosophy, it will come time to
pay this debt sooner than you may expect. In the following sections we provide
one philosophy that we hope will help you craft better scientific software
within today’s research environment. It’s worked for us and we think it will
work for you as well.


```{tableofcontents}
```
