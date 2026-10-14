.. _sec_project_files:

Files included in project data
=====================================

Project data is stored in multiple files extracted into a folder.

This section explains the files included in the project data.

Types of data
------------------

Project data is classified into the following two types.

* Meta information
* Actual data

Each of them is described below.

Meta information
----------------

Meta information is stored in the following files.

* project.xml
* subwindows/preprocessor.xml, etc.

All meta information is stored in XML files.

project.xml
~~~~~~~~~~~~~~

The main metadata. It stores basic information about the project, such as:

* The version number of iRIC GUI that saved the project
* The solver executed in the project and its version
* The coordinate system of the project

subwindows/preprocessor.xml, etc.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The XML files in the subwindows folder, such as subwindows/preprocessor.xml, store
information for each window, such as the pre-processor and the visualization windows.

The XML files in the subwindows folder are referenced from project.xml by the "ref" attribute.

The XML files in the subwindows folder store information such as:

* The data type of each item in the object browser, and the path of the actual data file that stores the data
* The expanded/collapsed state of folders in the object browser
* Data visualization settings

.. _sec_project_files_real:

Actual data
------------

Actual data is the data used in the project. The main data included in the actual data are listed below.

* Geographic data
* Hydraulic data
* Grid generation conditions
* Boundary condition settings
* Grid data
* Calculation conditions
* Solver output log
* Calculation results
* Measured values
* Background images

Each type of data is described below.

Geographic data
~~~~~~~~~~~~~~~~~~

Geographic data is stored in the following files.

* (grid type)/geographicdata/(geographic data group name)/riversurvey1.dat, etc.

**(grid type)** is the name attribute of the <GridType> element in the solver definition file. For solvers that have only one grid type and do not define a <GridType> element, it is the value of the name attribute of the root element <SolverDefinition> of the solver definition file, that is, the name of the solver (e.g. Nays2DH).

**(geographic data group name)** is the value of the name attribute of the <GridRelatedCondition /> element in the solver definition file.

The file format of geographic data differs for each type of data (e.g. cross-section survey data, point cloud data), and is a binary format specific to iRIC. Depending on the data, the information may be split into multiple files (e.g. rainfall data). The internal representation of the binary format is not public.

Hydraulic data
~~~~~~~~~~~~~~~~~~

Hydraulic data is stored in the following files.

* (grid type)/hydraulicdata/(hydraulic data group name)/wse1.dat, etc.

**(grid type)** is the name attribute of the <GridType> element in the solver definition file. For solvers that have only one grid type and do not define a <GridType> element, it is the value of the name attribute of the root element <SolverDefinition> of the solver definition file, that is, the name of the solver (e.g. Nays2DH).

**(hydraulic data group name)** is currently only "waterelevation".

Grid generation conditions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Grid generation conditions are stored in the following files.

* (grid type)/(zone name)/gridcreatingcondition.dat, etc.

**(grid type)** is the name attribute of the <GridType> element in the solver definition file. For solvers that have only one grid type and do not define a <GridType> element, it is the value of the name attribute of the root element <SolverDefinition> of the solver definition file, that is, the name of the solver (e.g. Nays2DH).

**(zone name)** is iRICZone for most solvers.
For solvers that handle multiple grid types, it is the name attribute of the <GridType> element followed by 1, 2, 3.

Boundary condition settings
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Boundary condition settings are stored in the following files.

* **Target region polygon**: (grid type)/(zone name)/bcsetting/inflow1.dat, etc.
* **Settings**: (grid type)/(zone name)/bc/inflow1.dat, etc.

The files that store the target region polygons are in a binary format specific to iRIC. The internal representation of the binary format is not public.

The files that store the settings are in CGNS file format. The settings are stored in the following element in the CGNS file.

* **Settings**: iRIC/iRICZone/ZoneBC

Grid data
~~~~~~~~~~~~~~~~

Grid data is stored in the following file.

* Case1_input.cgn

Case1_input.cgn is in CGNS file format.
Grid data is stored in the following elements in the CGNS file.

* **Grid dimensions**: iRIC/iRICZone/ data
* **Grid node coordinates**: iRIC/iRICZone/GridCoordinates
* **Grid attributes**: iRIC/iRICZone/GridConditions
* **Definition of grid cells**: iRIC/iRICZone/Element/ElementConnectivity (unstructured grids only)
* **Boundary conditions**: iRIC/iRICZone/ZoneBC

Calculation conditions
~~~~~~~~~~~~~~~~~~~~~~~~~~

Calculation conditions are stored in the following file.

* Case1_input.cgn

Case1_input.cgn is in CGNS file format.
Calculation conditions are stored in the following elements in the CGNS file.

* **Basic items**: iRIC/iRICZone/CalculationConditions
* **Complex items**: iRIC/iRICZone/GridComplexConditions

Solver output log
~~~~~~~~~~~~~~~~~~~~

The solver output log is stored in the following file.

* consoleLog.txt

consoleLog.txt is in text format.
It stores what the solver wrote to standard error and standard output.

Calculation results
~~~~~~~~~~~~~~~~~~~~~~~~

The files that store calculation results differ depending on the project setting
"Output calculation results to a separate file for each time step".

When outputting to a separate file for each time step
++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Calculation results are stored in the following files.

* result/Solution1.cgn, etc.

Solution1.cgn, etc. are in CGNS file format.
Calculation results are stored in the following elements in the CGNS file.

* **Results defined at grid nodes**: iRIC/iRICZone/FlowSolution1
* **Results defined at grid cells**: iRIC/iRICZone/FlowCellSolution1
* **Results defined at grid edges (I direction)**: iRIC/iRICZone/FlowIFaceSolution1
* **Results defined at grid edges (J direction)**: iRIC/iRICZone/FlowJFaceSolution1
* **Results defined at grid edges (K direction)**: iRIC/iRICZone/FlowKFaceSolution1
* **Results defined for particles**: iRIC/iRICZone/ParticleSolution1, iRIC/iRICZone/ParticleGroupSolution1
* **Results defined for particles (displayed as images)**: iRIC/iRICZone/ParticleGroupImageSolution1
* **Results defined for polygons**: iRIC/iRICZone/PolyDataSolution1
* **Results defined globally**: iRIC/BaseIterativeData

When not outputting to a separate file for each time step
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Calculation results are stored in the following file.

* Case1.cgn

Case1.cgn is in CGNS file format.
Calculation results are stored in the following elements in the CGNS file.

* **Results defined at grid nodes**: iRIC/iRICZone/FlowSolution1, etc.
* **Results defined at grid cells**: iRIC/iRICZone/FlowCellSolution1, etc.
* **Results defined at grid edges (I direction)**: iRIC/iRICZone/FlowIFaceSolution1, etc.
* **Results defined at grid edges (J direction)**: iRIC/iRICZone/FlowJFaceSolution1, etc.
* **Results defined at grid edges (K direction)**: iRIC/iRICZone/FlowKFaceSolution1, etc.
* **Results defined for particles**: iRIC/iRICZone/ParticleSolution1, iRIC/iRICZone/ParticleGroupSolution1, etc.
* **Results defined for particles (displayed as images)**: iRIC/iRICZone/ParticleGroupImageSolution1, etc.
* **Results defined for polygons**: iRIC/iRICZone/PolyDataSolution1, etc.
* **Results defined globally**: iRIC/BaseIterativeData

Measured values
~~~~~~~~~~~~~~~~~

Measured values are stored in the following files.

* MeasuredData_1.vtk, etc.

MeasuredData_1.vtk, etc. are in VTK binary format. For details of the format, see the following.

https://docs.vtk.org/en/latest/design_documents/VTKFileFormats.html

Background images
~~~~~~~~~~~~~~~~~~~~

Background images are stored in the following files.

* backgroundimages/image1.png, etc.

image1.png, etc. are in PNG file format.
