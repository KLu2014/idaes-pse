Getting Started
===============

Installation
------------
To install the IDAES PSE framework, follow the set of instructions below that are
appropriate for your needs and operating system. If you get stuck, please contact
`idaes-support@idaes.org <idaes-support@idaes.org>`_.

After installing and testing IDAES, it is strongly recommended to do the IDAES tutorials
located on the |examples-site|.

If you expect to develop custom models, we recommend following the
:ref:`advanced user installation<advanced_user_guide/advanced_install/index:Advanced User Installation>`.

The OS specific instructions provide information about optionally installing
Miniconda. If you already have a Python installation you prefer, you can skip
the Miniconda install section.

.. note:: IDAES supports Python 3.6 and above.

+------------------+-----------------------------+
| System           | Section                     |
+==================+=============================+
| Linux            | :ref:`min_install_linux`    |
+------------------+-----------------------------+
| Windows          | :ref:`min_install_windows`  |
+------------------+-----------------------------+
| Mac OSX          | :ref:`min_install_osx`      |
+------------------+-----------------------------+
| Generic          | :ref:`min_install_generic`  |
+------------------+-----------------------------+

.. warning:: If you are using Python for other complex projects, you may want to
            consider using environments of some sort to avoid conflicting
            dependencies.  There are several good options including conda
            environments if you use Anaconda.


.. _min_install_windows:

Windows
-------

**Install Miniconda (optional)**

1. Download: https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe
2. Install anaconda from the downloaded file in (1).
3. Open the Anaconda Prompt (Start -> "Anaconda Prompt").
4. In the Anaconda Prompt, follow the :ref:`min_install_generic` instructions.

.. _min_install_linux:

Linux
-----

**Install  Miniconda (optional)**

1. Download: https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
2. Open a terminal window
3. Run the script you downloaded in (1).

**Install Dependencies**

1. The IPOPT solver depends on the GNU FORTRAN, GOMP, Blas, and Lapack libraries,
   If these libraries are not already installed on your Linux system, you or your
   system administrator can use the sample commands below to install them. If you
   have a Linux distribution that is not listed, IPOPT should still work, but you
   the commands to install the required libraries may differ. If these libraries
   are already installed, you can skip this and proceed with the next step.

   .. note:: Depending on your distribution, you may need to prepend ``sudo`` to
            these commands or switch to the "root" user.

   apt-get (Current Ubuntu based distributions)::

      sudo apt-get install libgfortran4 libgomp1 liblapack3 libblas3

   yum (Current RedHat based distributions, including CentOS)::

      yum install lapack blas libgfortran libgomp

**Complete Generic Install**

Follow the :ref:`min_install_generic` instructions.


.. _min_install_osx:

Mac/OSX
-------

**Install  Miniconda (optional)**

1. Download: https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
2. For the next steps, open a terminal window
3. Run the script you downloaded in (1).

**Complete Generic Install**

Follow the :ref:`min_install_generic` instructions.


.. _min_install_generic:

Generic install
---------------

The remaining steps performed in either the Linux or OSX Terminal or Powershell.
If you installed Miniconda on Windows use the Anaconda Prompt or Anaconda
Powershell Prompt.  Regardless of OS and shell, the following steps are the same.


**Install IDAES**

1. Install IDAES with pip::

    pip install idaes-pse

2. Run the :doc:`idaes get-extensions command<user_guide/commands/get_extensions>`
   to install the compiled binaries::

    idaes get-extensions

..

   .. warning:: The IDAES binary extensions are not yet supported on Mac/OSX.

                As fallback (assuming you are uisng a conda env) you can install
                the generic ipopt solver with the command ``conda install -c
                conda-forge ipopt`` though this will not have all the features
                of our extentions package.

3. Run the :doc:`idaes get-examples command <user_guide/commands/get_examples>` to download
   and install the example files::

    idaes get-examples

..

    By default this will install in a folder "examples" in the current directory.
    The command has many options, but an important
    one is `--dir`, which specifies the folder in which to install.

    for Mac and Linux users this would look like::

        idaes get-examples --dir ~/idaes/examples

    or, for Windows users, it would look like::

        idaes get-examples --dir C:\Users\MyName\IDAES\Examples

    Refer to the full :doc:`idaes get-examples command documentation <user_guide/commands/get_examples>`
    for more information.

4. Run tests::

    pytest --pyargs idaes -W ignore

5. You should see the tests run and all should pass to ensure the installation worked. You
   may see some "Error" level log messages, but they are okay, and produced by tests for
   error handling. The number of tests that failed and succeeded is reported at the end of the pytest
   output. You can report problems on the |github-issues|
   (Please try to be specific about the command and the offending output.)
