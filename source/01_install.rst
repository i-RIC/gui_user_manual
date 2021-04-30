Installation
================

This page explains how to install iRIC, and related topics.

How to Install
-----------------

1. Download the installer of iRIC from the iRIC web site. Please access https://i-ric.org/download/.
2. Execute the installer that you've downloaded.

.. warning: About install target folder

   Please note that the install target folder must not include spaces or non-ASCII characters.

   * Good: C:\\Users\\user1\\iRIC
   * Good: D:\\iRIC
   * Bad: C:\\Users\\ユーザ1\\iRIC
   * Bad: C:\\Users\\Firstname Lastname\\iRIC

Warning about installing Miniconda
------------------------------------------

iRIC 3.0 can run solvers developed with Python.

To run solver developed with python, iRIC installer bundles Miniconda as Python runtime environment.
Please refer to the following URL about the detail of Miniconda.

https://docs.conda.io/en/latest/miniconda.html

When you install Miniconda using iRIC installer, Miniconda is installed to "Miniconda3" folder under
the iRIC install target folder.

Note that when you have an environement where Miniconda is already installed, if you
install Miniconda additionally using iRIC installer, it cause bad dffects to the Miniconda
environment that already exists.

So, in that case, DO NOT install Miniconda using iRIC installer, and follow the
steps described in :ref:`sec_use_existing_miniconda`.

If you accidently installed Miniconda additionally, follow the steps in :ref:`sec_recover_miniconda3`,
to rescue the environment.

.. _sec_use_existing_miniconda:

Preparing iRIC solver runtime environment using Miniconda that is already installed
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can prepare iRIC solver runtime environment using Miniconda that is already installed.
The steps can be applied for Anaconda too.

Do not install Miniconda 
..................................

When installing iRIC, please make sure that the check boxes for the items below are checked off.
For safety, they are checked off in the default state.

* Miniconda 
* iriclib for Miniconda

Create virutal environment for iRIC
..........................................

Launch "Anaconda Prompt (miniconda3)" from start menu, and execute the command below:

.. code-block:: text
   :caption: Commands to create a virtual environment

   conda create -n iric python=3.8
   conda activate iric
   conda install numpy

The commands creates virtual environment named "iric", and installs Python 3.8 and numpy to that.

For example when you've installed Miniconda to D:\\Miniconda3, make sure that
now you have Python.exe in D:\\Miniconda\\Envs\\iric.

Install iriclib for Python
................................

Install iriclib for Python to the virtual environment you've created.

For example, when you've installed Miniconda to D:\\Miniconda3, 
please copy the files below to D:\\Miniconda\\Envs\\iric\\Lib\\site-packages.

* IRICROOT\\guis\\prepost\\sdk\\python\\iric.py
* IRICROOT\\guis\\prepost\\sdk\\python\\_iric_python38.pyd --> rename to _iric.pyd after copying
* IRICROOT\\guis\\prepost\\iriclib.dll
* IRICROOT\\guis\\prepost\\cgnsdll.dll
* IRICROOT\\guis\\prepost\\hdf5.dll
* IRICROOT\\guis\\prepost\\szip.dll
* IRICROOT\\guis\\prepost\\zlib.dll

In the list above, iRICROOT means the install target folder of iRIC (For example C:\\Users\\user1\\iRIC).

Testing iriclib
..............................

Launch "Anaconda Prompt (miniconda3)" from start menu, and execute the following commands.

.. code-block:: text
   :caption: Commands for testing iriclib

   conda activate iric
   python
   import iric

When no error message is shown, iriclib is installed correctly.

Setup Python path setting on iRIC
.....................................

Setup iRIC so that it can run solvers using the environment that you've created. Please follow the steps below:

1. Launch iRIC, by double clicking the iRIC icon on your desktop.
2. Select [Option] -> [Preference] from menu.
3. Input the path of Python to [Python path]. For example, in the case above, it should be "D:\\Miniconda\\Envs\\iric\\Python.exe".

.. _sec_recover_miniconda3:

How to recover in case you've overwritten the original Miniconda environement accidently
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When you install Miniconda with iRIC installer, the following problem occurs for the Miniconda environment that you've installed in advance.

* "Anaconda Prompt (miniconda3)" and "Anaconda Powershell Prompt (miniconda3)" that you can launch from start menu refers the new environment that you've installed using iRIC installer.

You can recover the problem above, with the following steps:

1. Right-click on "Anaconda Prompt (miniconda3)" in start menu, and select "Other" -> "Open the file location".
2. A new explorer window opens, and the shortcut "Anaconda Prompt (miniconda3)" is shown. Right-click on the shortcut, and select "Property".
3. "Make sure that the "link target" value is like below:

   %windir%\System32\cmd.exe "/K" (iRIC install target)\\Miniconda3\\Scripts\\activate.bat (iRIC install target)\\Miniconda3

4. Replace (iRIC install target) with the path that you've installed Miniconda, and click on [OK] button.

You can recover "Anaconda Powershell Prompt (miniconda3)" shortcut with the same steps too.
