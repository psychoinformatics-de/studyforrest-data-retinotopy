studyforrest.org Dataset
************************

|license| |access| |doi|

Retinotopic Mapping
===================

All participants in the phase2 extension of the studyforrest dataset underwent
retinotopic mapping with standard flickering checkerboard stimulus (ring and
wedges). More information on the procedure and the results can be found in:

     Ayan Sengupta, Falko R. Kaule, J. Swaroop Guntupalli, Michael B. Hoffmann,
     Christian Häusler, Jörg Stadler, Michael Hanke. `An extension of the
     studyforrest dataset for vision research
     <http://biorxiv.org/content/early/2016/03/31/046573>`_. (submitted for
     publication)

For further information about the project visit: http://studyforrest.org

Content
-------

``code/``:

 source code for retinotopic mapping analysis.

 - The main script is *process_retmap* and a Python based GUI *easyret_gui* to
   call it from an easy to use front end. The *process_retmap* script calls the
   Python scripts *RetMap_phaseshift* for post processing phase shift (if
   required) and *combine_volumes*  for combining the clw/ccw maps and ecc/con
   maps together.

``src/``:
   links to repositories containing all inputs for the analysis

``sub-??/``:
   analysis results per participant

   ``surface_maps/``:
     contains eccentricity and polar angle maps of left and right hemispheres
     of a particular participant's cortical surface in *MGH* format

   ``post_processing/``:
     contains the post-processed/combined compressed *NIfTI* files in a
     participant's bold3Tp2 image template space
     (see ``src/templatetransforms``), before it is aligned to the
     *T1 structural* and represented on cortical surfaces.

``qa/``:
   contains the *pyretmap_subjQuali.ods* file which details the quality of the
   participant-wise retinotopic maps produced by the *processing pipeline*.


How to obtain the data files
----------------------------

This repository contains metadata and information on the identity of all
included files. However, the actual content of the (sometime large) data
files is stored elsewhere. To obtain any dataset component, git-annex_ is
required in addition to Git_.

1. Clone this repository to the desired location.
2. Enter the directory with the local clone and run::

     git annex init

   Older versions of git-annex may require you to run the following
   command immediately afterwards::

     git annex enableremote mddatasrc

Now any desired dataset component can be obtained by using the ``git annex get``
command. To obtain the entire dataset content run::

     git annex get .

Keep data up-to-date
--------------------

If updates to this dataset are made in the future, update any local clone by
running::

     git pull

followed by::

     git annex get .

to fetch all new files.


.. _Git: http://www.git-scm.com

.. _git-annex: http://git-annex.branchable.com/

.. |license|
   image:: https://img.shields.io/badge/license-PDDL-blue.svg
    :target: http://opendatacommons.org/licenses/pddl/summary
    :alt: PDDL-licensed

.. |access|
   image:: https://img.shields.io/badge/data_access-unrestricted-green.svg
    :alt: No registration or authentication required

.. |doi|
   image:: https://img.shields.io/badge/doi-missing-lightgrey.svg
    :target: http://dx.doi.org/
    :alt: DOI
