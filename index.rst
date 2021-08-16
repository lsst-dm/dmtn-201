..
  Technote content.

  See https://developer.lsst.io/restructuredtext/style.html
  for a guide to reStructuredText writing.

  Do not put the title, authors or other metadata in this document;
  those are automatically added.

  Use the following syntax for sections:

  Sections
  ========

  and

  Subsections
  -----------

  and

  Subsubsections
  ^^^^^^^^^^^^^^

  To add images, add the image file (png, svg or jpeg preferred) to the
  _static/ directory. The reST syntax for adding the image is

  .. figure:: /_static/filename.ext
     :name: fig-label

     Caption text.

   Run: ``make html`` and ``open _build/html/index.html`` to preview your work.
   See the README at https://github.com/lsst-sqre/lsst-technote-bootstrap or
   this repo's README for more info.

   Feel free to delete this instructional comment.

:tocdepth: 1

.. Please do not modify tocdepth; will be fixed when a new Sphinx theme is shipped.

.. sectnum::

.. TODO: Delete the note below before merging new content to the master branch.

.. note::

   **This technote is not yet published.**

   This note describes evaluating of hardware building blocks and MinIO for Rubin's Archive Enclave.



Introduction
============

This document describes the evaluation of MinIO object store and the corresponding storage hardware
for Rubin Archive Enclave. The evaluation is based on a list of criteria ranging from Rubin's need on storage 
volume, feature, integration with Rubin Prompt Processing/Data Release Proudction/Data Access Center, etc. 
at USDF, etc. Integration with SLAC SDF architecture, and SDF operational preferences are also part of the 
evaluation creteria. 

Overview of Requirements 
========================
(contributors: K-T, Richard, Yee, Lance, ...)

`DMTN-189 (Rubin Data Faclity Specfications) <https://dmtn-189.lsst.io/v/u-ktl-initial-spec/index.html>`_
specifies that in the USDF's archive enclave, object storage with S3-type interface is preferred for
raw LSSTCam scince data, data release products (including intermediates), calibration data products. 
Data ingestion, prompt processing, calibration, data release production, distribution to FrDF, UKDF, and
Data Access Centers (DAC), as well as user analysis at the US DAC will all interact with this object storage. 
The usage pattern is write-once and read-many. The requirement emphasizes scalability and low cost. 
Low access latency is secondary compare to the cost.

USDF will be hosted by SLAC Shared Data Facility (SDF). SDF has its own set of refers in storage architecture
and service operation. This will be described in RTN-025.

Evaluation Criteria and Results
===============================
(Define criteria first, fill in results upon completion of evaluation)

MinIO Features 
--------------
(contributors: Yee)

One of the object storage technologies under evaluation is MinIO. Several features make MinIO outstanding 
in the evaluation:

* blah 
* blah blah
* backup to tape
* security ...

Hardware Candidates
-------------------
(contributors: Yee, Lance)

SDF prefers JBOD-like storage building blocks. As a proof-of-concept, USDF is planning a 3.5PB (usable?) storage
based on these building blocks. Candidates are:

* Seagate 4u100: (with integrated system board)
* ... 

Deployment and Operation
------------------------
(contributors: Lance, Yee)

SDF prefers in deployment and operation include:

* k8s, direct-csi
* Failure recovery: single disk failure, single node failure.  
* Monitoring
* Complexity and maintainability 

Integration with Rubin data processing pipelines
------------------------------------------------
(contributors: K-T, Wei, ...)

Expect no major problem with prompt processing, calibration, data release production and DAC becaus they are 
designed to interface with S3-type object storage.

* Evaluate integration with Panda (especially Panda Pilot)
* Evaluate integration with data backbone. Note: the current data tranfer mechanisms are centered around 
  Butler. It is an area that will continue to evolve. 

Storage Performance
-------------------
(contributors: who ?)

Simultaneous access by several componments in Rubin data processing pipeline may happen. 

Need to know write/read of bytes/sec and objects/sec from the following and evaluation storage readiness if 
they all happen at the same time:

#. Data ingestion from Summit
#. Prompt processing
#. Calibration
#. Data Release Production
#. Distribution to FrDF, UKDF and DACs
#. User jobs at US DAC
#. Backup to tape

Do we need to guarantee access priorities by the first two?


.. Add content here.
.. Do not include the document title (it's automatically added from metadata.yaml).

.. .. rubric:: References

.. Make in-text citations with: :cite:`bibkey`.

.. .. bibliography:: local.bib lsstbib/books.bib lsstbib/lsst.bib lsstbib/lsst-dm.bib lsstbib/refs.bib lsstbib/refs_ads.bib
..    :style: lsst_aa
