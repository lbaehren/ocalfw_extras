ocalfw_scripts
==============

Collection of (shell) scripts to be used within the TROPOMI OCAL framework


Organization of the code base
-----------------------------

    .
    |-- CMakeLists.txt
    |-- scripts
    |   |-- CMakeLists.txt
    |   |-- copy_quicklooks
    |   |-- create_quicklook_tasks
    |   `-- run_tasks
    `-- templates
        |-- proc_quicklook.ocal
        |-- proc_raw.ocal
        |-- quicklook_detector.ocal
        |-- quicklook_raw.ocal
        |-- quicklook_scanning_maximum.ocal
        `-- quicklook_scanning_row.ocal


Installation instructions
-------------------------

In order to allow integration of the scripts into your normal working setup,
you might want to do one of the following:

 1. Add the ``scripts`` directory to your ``PATH`` variable; this will allow you
    to call the script directly from any location on the system.

 2. Manually copy the scripts to a location (e.g. ``$HOME/sw/bin``) where you are
    keeping custom installations of software packages/tools which are in your
    ``PATH``.

 3. Use [CMake](http://www.cmake.org) to configure the package and install the
    executable scripts.

    a. Create build directory

        mkdir build

    b. Configure package

        cmake ..

    c. Install scripts (and auxiliary data)

        make install
