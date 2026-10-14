.. _sec_project_data_storage:

Where project data is stored
=========================================

Where project data is stored depends on the workflow in iRIC. There are three cases.

* When a new project is created
* When a project file (\*.ipro) is opened
* When a project folder is opened

Each case is described below.

.. _sec_project_data_storage_new:

When a new project is created
-------------------------------

When a new project is created, the project data is stored in a temporary folder
created in the working directory until the project is saved for the first time.

The subsequent process differs depending on whether the project is saved to a project file (\*.ipro) or to a project folder.

When saved to a project file (\*.ipro)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A project file (\*.ipro) is actually a ZIP file. Therefore, you can check its contents by changing the extension from \*.ipro to \*.zip and opening it.

When a project file (\*.ipro) is saved, the process is performed in the following steps.

1. The project data is saved in the working directory.
2. A ZIP file named (random string).zip is created in the working directory as a temporary file, and the contents of the project data are stored in it.
3. The ZIP file created in step 2 is renamed to the file name specified by the user.

.. note:: Information stored in the project file (\*.ipro)

   In step 2 above, only the following files are stored in the ZIP file.

   * The metadata and actual data saved in the working directory by iRIC GUI
   * Files saved directly under the working directory by something other than iRIC GUI

   Because of this process, when saving to a project file (\*.ipro), please note that files saved in subfolders of the working directory by something other than iRIC GUI are lost.

   If you want to keep files created by something other than iRIC GUI in subfolders, save to a project folder.

When saved to a project folder
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When saving to a project folder, the process is performed in the following steps.

1. The project data is saved in the working directory.
2. The working directory is renamed to the name specified by the user (if the destination project folder is on a different drive from the working directory, the working directory is copied and then deleted).

.. _sec_project_data_storage_ipro:

When a project file (\*.ipro) is opened
-------------------------------------------------

When a project file (\*.ipro) is opened, its contents are extracted into a temporary folder
created in the working directory and read from there.

The subsequent process is the same as in :ref:`sec_project_data_storage_new`.

.. _sec_project_data_storage_folder:

When a project folder is opened
-------------------------------------------------

When a project folder is opened, the project folder itself is used as the working directory. The files in the project folder are read.

When geographic data is imported or deleted, the files in this folder are saved or deleted.

Therefore, as described in :ref:`sec_data_incompatibility`, in order to prevent inconsistency in the project data, when a project folder is opened,
the project is always saved when it is closed.

.. note::

   There used to be an option that, when a project folder was opened, extracted the contents of the project folder into a temporary folder
   created in the working directory, in the same way as when a project file (\*.ipro) is opened. This option has since been removed.
