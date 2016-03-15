# Introduction #

Simple one functions library that allows implementation of HTTP based authentication.

# Details #

This is a script that will:
  1. Prompt user for username and password
  1. Check the credentials against a simple array with usernames and passwords.
  1. Determine the "mode" which is the kind of the user account. Very similar to what group would be.
  1. Returns a structure filled out with the results of the verification.
  1. Recognizes some standard modes: admin, when user is an administrator; anonymous - when user is without u/p; unknown - when credentials are not recognized; undefined - when the verification was canceled.

# Known issues #

Sign out procedure is not very convenient and obvious from end user stand point of view.

# Repository #

Get a local copy of the boyanov prototypes repository with this command:
> hg clone https://prototypes.boyanov.googlecode.com/hg/ boyanov-prototypes

Direct browsing:
> http://code.google.com/p/boyanov/source/browse/?repo=prototypes#hg/httpauth

# Screenshots #

![http://prototypes.boyanov.googlecode.com/hg/httpauth/httpauth-352x312s.png](http://prototypes.boyanov.googlecode.com/hg/httpauth/httpauth-352x312s.png)