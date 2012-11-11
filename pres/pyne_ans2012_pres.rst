ANS Winter 2012
==============================

.. container:: main-title

    PyNE: Nuclear Engineering Toolkit

.. container:: main-names

    November 12th, 2012, San Diego, CA

    Anthony Scopatz*, Paul Romano, Kathryn Huff, Paul Willson 

    The Univ. of Chicago, MIT, Univ. Wisconsin - Madison

    \*scopatz@gmail.com


What is PyNE?
==============================
PyNE is a free & open source nuclear engineering toolkit.

.. break

It aims to be **fast** and **usable**.

.. break

Here is our software stack:

.. raw:: pdf

    Spacer 0 35

.. image:: img/stack1.png
    :scale: 400%
    :align: center

What is PyNE?
==============================
PyNE is a free & open source nuclear engineering toolkit.

It aims to be **fast** and **usable**.

Here is our software stack:

.. raw:: pdf

    Spacer 0 35

.. image:: img/stack2.png
    :scale: 400%
    :align: center


What is PyNE's Goal?
==============================
As a toolkit, PyNE is the substrate on which 
nuclear science and engineering problems are solved.  

.. break

The goal is to be **useful**.  Therefore new development takes an engineering 
approach with three main thrusts:

.. break

    * Data structures

.. break

    * Algorithms

.. break

    * Nuclear Data 


What is PyNE's Purpose?
==============================
As a free & open project, we want people (grad students) to stop 
*constantly* reinventing the wheel. |no-wheel|

.. break

The wheel that we do invent will be natural, fast, tested, documented, and 
reproducible.  We are not afraid of scope explosion!

.. break

This will allow *everyone* to shorten development time by more 
quickly being able to spin up new students, test new ideas, contribute 
back, and publish.

.. break

This means less overhead for maintanence and bug fixes.

..  |no-wheel| image:: img/no-wheel.jpg
                :scale: 100%

Whirlwind Tour!
==============================

.. container:: main-title

    Data Structures

Materials
==============================
PyNE materials are the primary object for sets of radionuclides, 
inspired by NumPy arrays and Python dicts.

.. break

.. code-block:: python

    In [1]: from pyne.material import Material

    In [2]: leu = Material({'U238': 0.96, 'U235': 0.04}, 42)

    In [3]: leu
    Out[3]: pyne.material.Material({922350: 0.04, 922380: 0.96}, 42.0, -1.0, {})

    In [4]: nucvec = {10010:  1.0, 80160:  1.0, 691690: 1.0, 922350: 1.0,
       ...:           922380: 1.0, 942390: 1.0, 942410: 1.0, 952420: 1.0,
       ...:           962440: 1.0}

    In [5]: mat = Material(nucvec)

    In [6]: weird_mat = leu + mat * 18

    In [7]: leu.comp[922350]
    Out[7]: 0.04

    In [8]: leu['U235']
    Out[8]: 1.68

    In [9]: weird_mat['U':'Am']
    Out[9]: pyne.material.Material({922350: 0.0736, 922380: 0.8464, 942390: 0.04, 942410: 0.04}, 50.0, -1.0, {})

Cross Section Formats (ACE)
==============================
We are developing readers and translators for standard cross section 
file formats from open publications.  (No one should have to do this 
twice).    ACE is the most mature.

.. break

.. image:: ../ace-gui.png
    :scale: 50%
    :align: center


Industry Standard I/O
==============================
Additionally, we have I/O routines for a number of industry stadard codes:

.. break

* ORIGEN 2.2

.. break

* Serpent

.. break

* MCNP

.. break

* NJOY

.. break

This is important! |no-wheel|


Whirlwind Tour!
==============================

.. container:: main-title

    Nuclear Data


Nucelar Data
==============================
Data distribution is as imporant as code distribution.

.. break

PyNE provides utilities for  managing basic data.

.. break

We have identified three orthoganal tiers of data:

.. break

.. raw:: pdf

    Spacer 0 65

.. image:: img/data-tiers.png
    :scale: 300%


Notes
==============================
come to your house

M&C tutorial

Blue sky afterwards


Questions
===============================
.. raw:: pdf

    Spacer 0 75

.. image:: img/qm.png
    :scale: 100%

