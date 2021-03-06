# Project Organization


Keep your repository organized. By using a standard directory structure both
you and your users will know where to find what they are looking for and
different aspects of your project will not become intertwined with each other.
At the top level of your project should be several files that provide some
metadata about your project as well as several folders that contain different
aspects of your project.


Most importantly, your project should contain a README file that gives an
overview of your project (we provide more details about what a good README file
should contain in another section)—what it does, installation instructions,
etc. but at a high level. Other standard files to include at this level are:
* CHANGES: A log of the changes your project has made between versions. This is
  an often overlooked but important document. It provides a quick and easy way to
  communicate changes to your users. If you are using GitHub, this file can
  easily be kept up-to-date by looking back at all the pull requests to your
  project and using the one-line summary of the pull request as a changelog
  entry.
* AUTHORS: A list of all the contributors to your project—not just you or the
  core team, but anyone who made a contribution, no matter how small.
* LICENCE: The license for your project.
* CONTRIBUTING: Include a document, for potential contributors, that outlines the
  process by which someone can contribute to your project. It should both
  describe how contributions can be made (e.g. a pull request) as well as any
  standards for a pull request to be accepted into the main code base (e.g tests
  must pass, follows coding style). 

Outside of these files, your project should contain a set of folders:
* docs: Detailed documentation for your project. Documentation should be a set of
  text files—not pdfs of your papers that use your model—that describe your
  project in some depth (see the documentation section). Ideally, these text
  files should be able to be rendered in other formats (e.g. html, epub).
* src: All your source code.
* tests: All your tests—both unit tests and system tests and any associated data.

There are a few things, which sometimes seem to get included, that probably
shouldn’t:
* Binary files: binary files do not lend themselves well to version control
  systems such as git—they are often large files and, because of the nature of
  their format, it is not easy to provide a useful diff between versions. Apart
  from not being helpful, this can also result in repositories quickly growing in
  size since even a tiny change to a binary file will mean that a copy of the
  entire file will be made for the small difference. Examples of binary files
  that are sometimes included that maybe shouldn’t be are input or output data
  files, pre-compiled binary distributions.
* Generated files: files that can be regenerated probably shouldn’t be
  included—particularly if they are meant to be regenerated. An example of this
  could be documentation files that are autogenerated from your source code.
  Including them will not only increase the size of your repository (even if only
  slightly) but may cause confusion for someone who tries to edit them but then
  later has their edits lost when the files are regenerated.
