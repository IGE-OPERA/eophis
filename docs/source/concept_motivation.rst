Why Eophis ?
============

.. autosummary::
   :toctree: generated

A bit of context
----------------

Eophis development takes place in the context of combining Python scripts with legacy Earth System Models (ESM) that are written in low-level abstraction languages, such as Fortran or C/C++.

Typical applications include:
    - Machine Learning (ML) / Physic-based hybrid modelling
    - Quick deployment of fast-evolving high-level libraries in stable low-level environment
    - Testing prototypal code before conversion for official merging


Interfaces are here required to make both components to interact. Beyond the heterogeneity of programming languages, the interface may also be compulsory to couple a CPU-optimized code with a GPU-optimized code. ML / Physics hybridation is a complete representative example of all these needs.


.. image:: images/GEO_AI_worlds.png
   :width: 400px
   :align: center

The question is adressed here through the strategy of creating pipes between a Fortran ESM and a Python script executed seperately. In this framework, both components are intended to exchange generic formatted data (typically arrays) through a coupling library.

Advantages of this approach are many:
    - Flexibility to fill each component of any content with mininal bindings
    - Execution of each component in different processing architectures
    - Python scripts easily shareable
    - Each compnent is up-to-date with its own environment


`OASIS3-MCT <https://oasis.cerfacs.fr/en/>`_ is a coupling library that allows to perform exchanges of 2D/3D fields with/out interpolation between the coupled components, and appears to be a good candidate. It provides Fortran, C and Python APIs, allowing coupling of heterogeneously written codes. Most of all, OASIS3-MCT is already widely used in the climate modeling community.



.. image:: images/Fort_OASIS_Py.png
   :width: 350px
   :align: center
   :alt: Exchange data between Fortran/C and Python with OASIS3-MCT.

.. note:: Main motivation is to use OASIS3-MCT to make an ESM exchange data with an external Python script that includes an OASIS3-MCT interface and modeling / ML functions.

Difficulties
------------

Let us assume that we developed a Python model that takes some geophysical fields as inputs. We wish to deploy it within a Fortran ESM. Assuming OASIS3-MCT is already configured in the Fortran side, remaining work is to implement and configure the OASIS3-MCT interface in the Python script, write the OASIS3-MCT namelist and manage connexions between sent/received data and inputs/ouputs of the Python model.

We can highlight several points:
    - OASIS3-MCT assumes that all coupled components share a set of features typically implemented in ESMs: a time-stepping procedure, an internal MPI communication layer, and autonomy in generating both the physical fields and the discretization grids. Those are likely to be missing in a standalone Python script that only contains functions.

    - A good understanding of OASIS3-MCT and its namelist is required to set up the coupling. Reccurent errors may occur with non OASIS-experts.
    
    - All of these steps should be repeated and adapted for each coupling situation and Python scripts, making them tedious.
    
    - Aimed OASIS3-MCT usage requires both simplified and complexified operations compared to the typical use, making standard learning of OASIS3-MCT unadapted.


.. note:: Eophis aims to provide the missing features required by OASIS3-MCT usage, abstract away the unnecessary complexities by generalizing the configuration of OASIS3-MCT on the Python side through a simplified interface, and provide tools to assist in setting up the global coupling environment.


Storytelling
------------

The above presented context may be quickly summarized in this way: *we wish to deploy Python code within geoscientific models*.

Let's reformulate this in a more figurative way: *we wish to populate earth with snakes*.
What is more natural than the parent of all snakes to fulfill this objective ?

Here comes **Eophis**, name of the oldest known snake ancestra (2023).
