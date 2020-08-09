.. BTF Trace Generation Framework on RTFParallella documentation master file, created by
   sphinx-quickstart on Sat Aug  8 14:33:16 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

BTF Trace Generation Framework on RTFParallella : documentation
===========================================================================


############
Introduction
############

The purpose of this project is to implement a tracing framework based on the Best Trace Format(BTF) to enable the debugging and timing analysis of the tasks executed on multicore heterogeneous platform. The framework has been developed as an extension to the RTFParallella. The documentation for the RTFParallella 
is available at `RTFParallella documentation`_.


The source code for the changes related to RTFParallella is available in Eclipse APP4MC `example repository`_.

The project also involves extending the existing CDGen application to generate the code for the provided System Model along with the BTF trace framework. The documentation for the CDGen application is available at `CDGen documentation`_.


The source code for the changes related to CDGen is available in Eclipse APP4MC `tools repository`_.


What is Best Trace Format (BTF)
===============================

The Best Trace Format is a tracing format for timing evaluation of event based system. It is a Comma Separated Value (CSV) based format for representation of event-traces in ASCII. It allows analyzing the behavior of the system in a chronologically correct manner in order to apply timing, performance or reliablility evaluations on embedded real-time multi-core systems. The specifications of this tracing format is based on OSEK Architecture.


Contribution
============

This project has been developed as part of Google Summer of Codes 2020. The following tasks has been achieved as part of extension to existing RTFParallella framework and CDGen tool.

* Implement the basic specification of BTF over RTFParallella framework.
* Create a tracing framework based on the BTF specification independent of the hardware platform.
* Implement the proper time scaling instead of tick count which is configurable.  
* Establishing timing synchronization between host system and the epiphany co-processor.
* Visualizing the generated trace format on tools such as Eclipse Trace Compass.
* Feature enhancement of CDGen tool to add code generation of tracing functionality.
* Testing and Documentation of the features developed as part of RTParallella and CDGen tool.



Scope
=====

The documentation will include the following:

* Overview of the Adapteva Parallella board along with the development environment setup.
* BTF Specification and its adaptation in the project.
* Implementation details of the tracing framework and synchronisation between multiple cores.
* Usage of tracing framework for different system models and hardware platforms.
* Memory mapping of the BTF trace framework on Adapteva Parallella.
* Feature extension of tracing framework on CDGen tool.
* Limitations and future scope of work.


Index
=====

.. toctree::
   :maxdepth: 2
   :caption: Contents:
.. toctree::
   :maxdepth: 2
   
   adapteva_parallella 

   dev_setup

   btf_spec

   trace_framework

   memory_mapping

   sys_model

   cdgen_ext

   run

   example 



.. _RTFParallella documentation: https://rtfparallella.readthedocs.io/en/latest/
.. _example repository: https://git.eclipse.org/c/app4mc/org.eclipse.app4mc.examples.git/
.. _CDGen documentation: https://cdgendoc.readthedocs.io/en/latest/
.. _tools repository: https://git.eclipse.org/c/app4mc/org.eclipse.app4mc.tools.git/







