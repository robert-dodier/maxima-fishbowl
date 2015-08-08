Maxima-Fishbowl
========

An interactive document user interface for Maxima (based on Fishbowl and IPython)

Maxima-Fishbowl is an [IPython](http://ipython.org) kernel (back end) for [Maxima](http://maxima.sourceforge.net),
a computer algebra system, based on the [Fishbowl](https://github.com/fredokun/fishbowl-repl) project
by Frederic Peschanski. Thanks a million, Frederic!

## Requirements ##

To try Maxima-Fishbowl you need :

 - a Maxima executable

   - built with a Common Lisp implementation which has native threads

     - Clozure CL works for sure; SBCL should work (incompletely tested)

     - Other implementations may be possible

   - You don't need to build Maxima! See notes below about creating
     the Maxima-Fishbowl executable.

 - Quicklisp (see: http://www.quicklisp.org)

   - When you load Fishbowl into Maxima for the first time,
     it will download some dependencies automatically.
     Good luck.

 - Python 3.2 or above

 - IPython 2.something -- IPython 3.something doesn't work (yet)
 
   - I obtained IPython 2.something by cloning the IPython Git repo
     and switching to the 2.x branch.

   - You may need to install various and sundry packages to make
     IPython happy. Your mileage may vary.

## Quick launch ##

For simple interactions on the console, enter something like:

    python3 ./run-maxima-fishbowl.py --maxima-fishbowl-exec=/path/to/maxima-fishbowl

NOTES:

  (1) There needs to be an executable named `ipython3` in your path.
  On my system this requires setting both PYTHONPATH and PATH and 
  creating the `ipython3` script which is included in Maxima-Fishbowl.
  Perhaps you already have an executable named `ipython3` so you won't need
  the one in Maxima-Fishbowl.

  (2) The executable named by `--maxima-fishbowl-exec` is an executable
  saved Lisp image. The saved image needs to contain Maxima and Fishbowl.
  I create these images by executing Maxima and loading Fishbowl into
  Maxima, and then saving an image. See `make-maxima-fishbowl-recipe.txt`
  for a recipe for that.

  (3) When you enter stuff to be evaluated, you omit the usual trailing
  semicolon or dollar sign:

```
In [1]: 2*21
Out[1]: 42

In [2]: 
```

## Notebooks ##

I created this project in order to combine Maxima with the IPython notebook
(with the goal of using the notebook to create blog posts containing text,
formulas, and plots). To execute the notebook server:

    python3 ./run-maxima-fishbowl.py notebook --maxima-fishbowl-exec=/path/to/maxima-fishbowl

The file `MaximaFishbowlExample.ipynb` is an example of a Maxima-Fishbowl notebook. [Here it is as rendered by the notebook viewer at ipython.org](http://nbviewer.ipython.org/github/robert-dodier/maxima-fishbowl/blob/master/MaximaFishbowlExample.ipynb)

Note that the Github notebook renderer is currently (August 2015) broken ([bug report here](https://github.com/jupyter/nbviewer/issues/452)) so if you look at `MaximaFishbowlExample.ipynb` in the Github viewer, it will look funny.

----

Have fun and keep me posted. Feel free to send pull requests, comments, etc.

Robert Dodier
robert.dodier@gmail.com
robert-dodier @ github
