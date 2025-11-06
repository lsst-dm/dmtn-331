.. image:: https://img.shields.io/badge/dmtn--331-lsst.io-brightgreen.svg
   :target: https://dmtn-331.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-331/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-331/actions/

#############################################
Background matching via null-space projection
#############################################

DMTN-331
========

Background matching is a family of algorithms for estimating the temporal backgrounds of astronomical images by using the differences between pairs of visits as the input data, since the vast majority of astrophysical sources disappear in those differences.  For $N$ images with $N$ different backgrounds, this only yields $N-1$ constraints, ensuring an underconstrained problem.  This technical note sketches out an approach that explicitly projects out the unconstrained linear combination of background models to be fit later after building a coadd, in order to avoid the problem of stitching together a reference image that that complicates most other background-matching methods.

Links
=====

- Live drafts: https://dmtn-331.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-331

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-331

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
