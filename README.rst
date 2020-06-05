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

This repository is a `DataLad <https://www.datalad.org/>`__ dataset. It provides
fine-grained data access down to the level of individual files, and allows for
tracking future updates up to the level of single files. In order to use
this repository for data retrieval, `DataLad <https://www.datalad.org>`_ is
required. It is a free and open source command line tool, available for all
major operating systems, and builds up on Git and `git-annex
<https://git-annex.branchable.com>`__ to allow sharing, synchronizing, and
version controlling collections of large files. You can find information on
how to install DataLad at `handbook.datalad.org/en/latest/intro/installation.html
<http://handbook.datalad.org/en/latest/intro/installation.html>`_.

Get the dataset
^^^^^^^^^^^^^^^

A DataLad dataset can be ``cloned`` by running::

   datalad clone <url>

Once a dataset is cloned, it is a light-weight directory on your local machine.
At this point, it contains only small metadata and information on the
identity of the files in the dataset, but not actual *content* of the
(sometimes large) data files.

Retrieve dataset content
^^^^^^^^^^^^^^^^^^^^^^^^

After cloning a dataset, you can retrieve file contents by running::

   datalad get <path/to/directory/or/file>

This command will trigger a download of the files, directories, or
subdatasets you have specified.

DataLad datasets can contain other datasets, so called *subdatasets*. If you
clone the top-level dataset, subdatasets do not yet contain metadata and
information on the identity of files, but appear to be empty directories. In
order to retrieve file availability metadata in subdatasets, run::

   datalad get -n <path/to/subdataset>

Afterwards, you can browse the retrieved metadata to find out about
subdataset contents, and retrieve individual files with ``datalad get``. If you
use ``datalad get <path/to/subdataset>``, all contents of the subdataset will
be downloaded at once.

Stay up-to-date
^^^^^^^^^^^^^^^

DataLad datasets can be updated. The command ``datalad update`` will *fetch*
updates and store them on a different branch (by default
``remotes/origin/master``). Running::

   datalad update --merge

will *pull* available updates and integrate them in one go.

More information
^^^^^^^^^^^^^^^^

More information on DataLad and how to use it can be found in the DataLad Handbook at
`handbook.datalad.org <http://handbook.datalad.org/en/latest/index.html>`_. The
chapter "DataLad datasets" can help you to familiarize yourself with the
concept of a dataset.

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
