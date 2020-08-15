#######################################
Binary deployment on Parallella 
#######################################


This section explains the process of deployment of software executables compiled on the development platforms and executing them on the Adapteva Parallella hardware platform.



Deployment Script
------------------------

The deployment script can be found in the root folder of RTFParallella

.. code-block:: bash

   /parallellaDeploy.sh


Deployment parameters
-------------------------

The deployment script has the following parameters. Those parameters are to be changed for the particular parallella board and development machine used :

*	:envvar:`HOST_NAME`			: Replace with IP address or host name of parallella 
*	:envvar:`HOST_USER`			: Replace with name of the user with privilige to execute files in :envvar:`HOST_OFFLOAD_PATH`.
*	:envvar:`HOST_OFFLOAD_PATH`	: Replcae with desired execution path on parallella board file system (usually this will be a folder under :envvar:`home`).
*	:envvar:`PORT`				: Replace with the SSH port on parallella board (usually 22).
*	:envvar:`KEY`				: replace with the absolute path to ssh the public SSH key file on the development host. 

Invocation of Deployment script
--------------------------------------

This script must have at least one argument that must be passed when it is invoked. Namely, the file which should be deployed, any number of files is allowed, arguments (files' names) must be separated by a space.

.. code-block:: bash

   /parallellaDeploy.sh armcode main0.elf


Binary Execution on Parallella
------------------------------

The binary files loaded on the Adapteva Parallella can be executed using the script provided in the root folder of RTFParallella. This script will run the executables on Parallella platform using the arguments provided to the script from the development environment.

.. code-block:: bash

   ./parallellaRun.sh


The binaries can also be executed by logging in the Parallella terminal. Here is an example for it:

.. code-block:: bash

    ssh parallella@<parallella ip address>
    cd boardExec
    ./armcode -t trace.btf




Tracing Framework Usage
-----------------------

The usage of tracing framework can be viewed by executing the host application is '-h' argument.

.. code-block:: bash

    parallella@parallella:~/boardExec$ ./armcode -h
    Usage:
    	[-t|--trace-btf]=<Output trace file name.>
    	[-m|--model-file]=<Model file name used to generate the trace file.>
    	[-s|--scale]=<Timing scale used to generate the trace file in microseconds. Accepted values are 100 and 1000.>
     	[-d|--device]=<Device target on which the trace file is generated.>
    	[-h|--help]=<Print the help message.>
    Example:
    	./host_main_example1 -t trace.btf -s 100 -m model.xml -d parallella



Known issues
-------------------------
The development host's SSH key must be listed as a trusted key in the parallella board authorized key file

.. code-block:: bash

   ~/.ssh/authorized_keys 

