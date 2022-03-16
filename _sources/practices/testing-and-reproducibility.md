# Testing and Reproducibility


What does it take for a model simulation to be reproducible? Metadata that
describes the execution environment (dependencies and versions), input files,
platform details, source code snapshot.


## Continuous Integration
Continuous integration is the process of running all of your project’s tests
with every change to your code base. This workflow ensures that any new changes
to the code do not break any existing tests. Although this may seem excessive
at first, it is far better to find bugs sooner rather than later. The earlier
you can identify a problem, the easier it will be to fix. Once a bug becomes
part of the main code base, and the longer it remains undetected, it becomes
increasingly integrated into the rest of the code and more difficult to
identify and remove. Identifying problems before a contribution is merged
allows the author of the pull request—not the maintainers (i.e. you)—to fix the
problem. They are the ones most familiar with the code being merged and how
best to fix any issues. Once merged, however, it becomes increasingly less
obvious who was responsible for the bug and how best to deal with it. Perhaps
the contributor has even moved on (graduated, found a job) and isn’t available
to fix the problem. If they had been aware of the problem at the time, they
likely could have fixed it quickly right then and there but instead you are
left to try to disentangle things.


Thus far we have discussed how a software project can use continuous
integration as an efficient way to test software and to ensure that bugs are
found as early as possible and fixed at the time they are identified. Another
important aspect of continuous integration—particularly in a scientific
setting—is how it can help with reproducibility. By “reproducibility” we are
describing the ability of another group to be able to run your software to
replicate your results—ensuring the conclusions of a published scientific work
are being faithfully represented by the associated code. Where the first set of
tests (unit tests) are known as white-box testing, this second set of tests are
known as black-box testing (system tests).


Whereas white-box tests ensure that small pieces of code—individual functions,
the small code blocks that do only one job—are working properly, the purpose of
black-box tests is to ensure that multiple interconnected pieces of code—even
your entire application—work together as expected. Ultimately, the black-box
tests are the ones that matter to your audience since they test the
functionality of your entire application. They can, however, be more difficult
to write but, following a few guidelines a project author can put together a
set of robust tests.


For software, and scientific software in particular, a robust and thorough set
of system tests can be difficult to put together. Scientific software can often
be best described as prototype software—that is, a program that is rapidly
changing and never truly in a stable state. It’s not always obvious what to
even compare the results of a simulation to to ensure that it’s working
correctly. Sometimes we write scientific software to answer questions for which
we don’t have an answer and the answers are surprises to us—it is difficult to
follow a test-driven development process when the answers are not known
beforehand. Other problems also exist such as non-deterministic results that
may depend on stochastic inputs or parallelism where results will vary slightly
from run to run depending on the timing of messages being passed between jobs.
Even running large parallel jobs may not be feasible due to a lack of
resources. We can’t always overcome all of these problems but we can try to
minimize them by following some not-too-difficult to implement practices, which
we outline below.


Numerical models commonly are used to answer questions for which there is not
an expected answer. In such cases it’s why we’ve created the model in the first
place but it makes it difficult to write robust system tests. How can one be
expected to write a test before the expected result is known? There are several
solutions to this. 


## Analytical solutions


Where analytic solutions are known, perhaps only for a set of specific cases,
one can write tests that compare model output to those known solutions.
Although these tests will likely not test all of your model’s functionality,
they will provide you the assurance that much of the interconnected components
of your code are working together as you expect. These tests also demonstrate
to your users, by reproducing well-known solutions they are familiar with, that
your software is working. By producing them with the corresponding inputs for
these solutions, they are then given an easy way to get started and to have a
template that they can then use to begin playing with your model and possibly
adapt it to their specific use-case.

