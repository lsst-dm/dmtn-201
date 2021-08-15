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

   We describe the architectural choices and tradeoffs for the large scale object storage to be used at the USDF.



Introduction
============

This document describes the evaluation process of MinIO object store for Rubin science data. It includes a brief 
description of hardware specfication and features of MinIO. The evaluation is based on a list of criteria ranging
from Rubin's need on storage volume, feature, integration with Rubin data processing software, etc. SLAC SCS 
operational preferences are also part of the evaluation creteria. 

Data Requirements and Challanges
================================


Data Volume, Variety and Access Patterns
----------------------------------------
- overview of the types of data products and size


Challenges and Remediations
---------------------------

- highlight specific things we need to worry about
- high level posisble solutions



Architectural Motivation
========================

- repeatable: well documented
- scalable: both management and performance
- robust: tiering



Technical Design
================

Hardware
--------

- define standard building blocks of storage
- define performance envelopes
- define resilience of solutions



Software
--------

- overview of software solutions
- pros/cons of ceph/minio
- supportabilty of solutions



Operational Processes
=====================

Deployment
----------

- large amounts of storage added per year
- easy to deploy, consistent and repeatable

Monitoring
----------

- hardware and software steady state and failure reporting requirements
- environmentals and zoning?

Common Tasks
------------

- what does hardware failure look like? disks, servers, racks?
- what are the high level responsibilities and roles required?


Life-cycle
----------

- what procedures required to replace hardware?



Proof of Concept
================

Scope and what are we trying to achieve
---------------------------------------

- why kubernetes?
- describe why minio and direct-csi


Deployment Experience
---------------------

- deployment steps and references 


Operational Experience
----------------------

- performance benchmarking
- simulating failures







Initial Hardware and Software Choices
=====================================

- dell xe7100 vs wd data102 vs seagate 4u100
- what and why










.. Add content here.
.. Do not include the document title (it's automatically added from metadata.yaml).

.. .. rubric:: References

.. Make in-text citations with: :cite:`bibkey`.

.. .. bibliography:: local.bib lsstbib/books.bib lsstbib/lsst.bib lsstbib/lsst-dm.bib lsstbib/refs.bib lsstbib/refs_ads.bib
..    :style: lsst_aa
