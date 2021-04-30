HDF5 library DLL outputs error
======================================

iRIC uses HDF5 library.

When you install programs that bundles HDF5 library DLL whose version is different
from that bundled with iRIC, for example Anaconda, it occurs that
HDF5 library output error message like below:

.. code-block:: text
   :name: hdf_warning
   :caption: Example of error message that HDF5 libarary output
   
   Warning! ***HDF5 library version mismatched error***

In such cases, you can solve the problem, by adding (iRIC Install target)\\guis\\prepost to PATH 
environmental variable with higher priority than the folders that contains other HDF5 library.

Or, you can disable the warning, by defining environmental variable HDF5_DISABLE_VERSION_CHECK with value 1.
Please note that as the warning suggests, using HDF5 library with different version can cause problems, so please fix the problem with the way above, if possible.
