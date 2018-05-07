RIC-Nays grid file (\*.grid)
----------------------------

A RIC-Nays grid file (\*.grid) is a binary file that stores data of the
calculation grid created by RIC-NaysPre as a flag (integer) that
describes the structure of a single-block BFC grid and the condition of
each grid cell.

Table 6‑5 shows the file format of the grid file.

iRIC does not read Obstacle Cell Flag in the RIC-Nays grid file.

Table ‑ Grid file format

+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Item                       | Data type                            | Description                                                                    |
+============================+======================================+================================================================================+
| Header of array            | Integer (4 bytes)                    | Always fixed as "20."                                                          |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| ISize                      | Integer (4 bytes)                    | Size of the grid in the I direction (Upstream side Downstream side)            |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| JSize                      | Integer (4 bytes)                    | Size of the grid in the J direction (Right bank side Left bank side)           |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| KSize                      | Integer (4 bytes)                    | Size of the grid in the K direction (Bed Water surface)                        |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Obst                       | Integer (4 bytes)                    | 0: No-obstacle-cell flag                                                       |
|                            |                                      |                                                                                |
|                            |                                      | 1: Obstacle-cell flag                                                          |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Footer of array            | Integer (4 bytes)                    | Always fixed as "20."                                                          |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Header of array            | Integer (4 bytes)                    | ISize × JSize × KSize × 24                                                     |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| x-coordinate of the grid   | Real number (8 bytes) X GridSize\*   | Stores x-coordinate by looping in terms of I, J and K as follows:              |
|                            |                                      |                                                                                |
|                            |                                      | X (I = 1, J = 1, K = 1)                                                        |
|                            |                                      |                                                                                |
|                            |                                      | X (I = 2, J = 1, K = 1)                                                        |
|                            |                                      |                                                                                |
|                            |                                      | …                                                                              |
|                            |                                      |                                                                                |
|                            |                                      | X (I = ISize, J = 1, K = 1)                                                    |
|                            |                                      |                                                                                |
|                            |                                      | X (I = 1, J = 2, K = 1)                                                        |
|                            |                                      |                                                                                |
|                            |                                      | …                                                                              |
|                            |                                      |                                                                                |
|                            |                                      | X (I = ISize, J = JSize, K = KSize)                                            |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| y-coordinate of the grid   | Real number (8 bytes) X GridSize\*   | Stores the y-coordinate in the same way as the x-coordinate.                   |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Z-coordinate of the grid   | Real number (8 bytes) X GridSize\*   | Stores the z-coordinate in the same way as the x-coordinate.                   |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Footer of array            | Integer (4 bytes)                    | ISize × JSize × KSize × 24                                                     |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Header of array            | Integer (4 bytes)                    | Exists only when "Obst =1."                                                    |
|                            |                                      |                                                                                |
|                            |                                      | (ISize -1) × (JSize-1) × (KSize-1) × 4                                         |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Obstacle Cell Flag         | Integer (4 bytes) X GridSize\*       | Exists only when "Obst =1."                                                    |
|                            |                                      |                                                                                |
|                            |                                      | Stores Obstacle Cell Flag data by looping in terms of I, J and K as follows:   |
|                            |                                      |                                                                                |
|                            |                                      | Obst (I = 1, J = 1, K = 1)                                                     |
|                            |                                      |                                                                                |
|                            |                                      | Obst (I = 2, J = 1, K = 1)                                                     |
|                            |                                      |                                                                                |
|                            |                                      | …                                                                              |
|                            |                                      |                                                                                |
|                            |                                      | Obst (I = ISize -1, J = 1, K = 1)                                              |
|                            |                                      |                                                                                |
|                            |                                      | Obst (I = 1, J = 2, K = 1)                                                     |
|                            |                                      |                                                                                |
|                            |                                      | …                                                                              |
|                            |                                      |                                                                                |
|                            |                                      | Obst (I = ISize -1, J = JSize -1, K = KSize -1)                                |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+
| Footer of array            | Integer (4 bytes)                    | Exists only when "Obst =1."                                                    |
|                            |                                      |                                                                                |
|                            |                                      | (ISize -1) × (JSize-1) × (KSize-1) × 4                                         |
+----------------------------+--------------------------------------+--------------------------------------------------------------------------------+

\* GridSize = ISize×JSize×KSize
