# Team Practices

Open source is not just for code. The development process of your project
should also be open for others to see and to participate in. In addition to
code development, when we talk about the “development process” we are also
thinking about design decisions, release timelines, bug reports and fixes, user
questions, feature requests, etc. Except for decisions of a personal nature
(hiring decisions, as an example), try to keep everything public.


Moving communication between you and your users from email (or some other
private channel) to a public forum will save you time, and bring more and
better ideas to your project. You should be ruthless with this. If, for
instance, someone emails you directly with a question about your software, (if
appropriate) move the conversation to a public forum such as the GitHub issue
tracker. It’s unlikely that this is (or will be) the only person with this
question. When such questions are asked and answered publicly, in the future
when someone has the same or similar question, the answer will already be there
for them to find without you having to spend time answering the question again.


A public forum provides a means for you to gather advice and feedback from your
users about the direction you may want to take your software, or new features
to add.


## Organizational space for code


Maintain an organization account for models—don’t keep models under user
accounts. It’s fine if the models start there but eventually they should belong
within an organizational account and the proper attribution given to the
original authors. Having the source code housed within an organization account
promotes a more collaborative environment since new contributions will not have
to go through, for instance, an ex-graduate student that may have graduated and
moved on to other things unrelated to this software. This will also prevent
speciation of the software in the case of someone wanting to pick up the
software and use it as part of their research. If the code remains housed under
another user account, it will be more likely that the new developer will simply
create a new repository—either as a fork or simply a copy of the code—so that
they will have their own version over which they have control. As a result,
multiple versions of the  model will appear, all with different features and
bug fixes. It would be better to have these new features and bug fixes all
incorporated into a single version of the model. Particularly bug fixes. As
bugs are found and fixed, the fixes should be propagated to the other versions
of the code, but if there are several versions spread about, it is unlikely the
bugs will be fixed for all the versions.

