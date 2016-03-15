# Introduction #

Read and parse ".ini" file, show it on the screen as HTML form and when submitted generate new ".ini" text with the changes.

# Details #

This is a script that will:
  1. Read and parse an ".ini" file.
  1. According to some simple rules it will determine what are: current values of the parameters; what are default values; what are possible values; comments specific to sections and parameters.
  1. Build a HTML form based of the gathered information.
  1. When form submitted  - generate new ".ini" text that reflects the changes made through the forms.

# Known issues #

Not all blank lines are preserved, especially at the beginning of the file. Double blank lines are not preserved either.

Not all white-space's are preserver, such as tabs. Multiple spaces at the beginning of the comments are reduced to only one space.

# Repository #

Get a local copy of the boyanov prototypes repository with this command:
> hg clone https://prototypes.boyanov.googlecode.com/hg/ boyanov-prototypes

Direct browsing:
> http://code.google.com/p/boyanov/source/browse/?repo=prototypes#hg/ctp

# Screenshots #

![http://prototypes.boyanov.googlecode.com/hg/ctp/ctp-662x472bw.png](http://prototypes.boyanov.googlecode.com/hg/ctp/ctp-662x472bw.png)