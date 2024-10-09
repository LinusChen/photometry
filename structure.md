
Terminology/shorthands:
- bp: band pass
- sp: spectrum
- res: synthetic photometry, or "response", represented as an band-averaged flux, in Jy.
- get_res: normally mean "get response".
- ResultGrid: A class. Contains a parameter grid, and the pre-tabulated results of a (typically expensive-to-evaluate) function on it.

The functions in the following table need be developed.

|  Function name        |  Input      |    Output      | Note |
|-----------------------|:-----------:|---------------:|-------|
| get_res               | bp, sp      | res            |
| get_res_unitBB        | bp, T       | res            |
| get_resGrid_unitBB    | bp, grid_T  | grid_res       | as ResultGrid |
| write_resGrid_unitBB  | bp, grid_T, bn, dir  |       | write grid_res to "dir/bn.pickle" |

The class DataObs (maybe renamed to ObservedSED) need to have the methods in the following table.

|  Function name        |  Input      |    Output      | Note |
|-----------------------|:-----------:|---------------:|-------|
| get_res               | sp          | res            | As a 1d array. |
| write_resGrid_unitBB  | bp, grid_T, bn, dir  |       | write grid_res to "dir/bn.pickle" |
| read_resGrid_unitBB   | bp, grid_T  |                | initializing self.l_res_grid|
