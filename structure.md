
Terminology/shorthands:
- bp: band pass
- sp: spectrum
- res: synthetic photometry, or "response", represented as an band-averaged flux, in Jy.
- get_res: normally mean "get response".
- ResTable: A class. Contains a parameter grid, and the pre-tabulated results of a (typically expensive-to-evaluate) function on it.

The functions in the following table need be developed.
Maybe in the module "response.py"

|  Function name        |  Input      |    Output      | Note |
|-----------------------|:-----------:|---------------:|-------|
| get_res               | bp, sp      | res            |
| unitBB                | T           | sp             |
| get_res_unitBB        | bp, T       | res            |
| get_resGrid_unitBB    | bp, grid_T  | grid_res       | as ResTable |
| dump_resGrid_unitBB  | bp, grid_T, bn, dir  |       | write grid_res to "dir/bn.pickle" |

The class ObservedSED need to have the methods in the following table.

Q: Can ResTable be pickled?
A: The data part certainly can pickled.
    Problem is about the interpolation function.
    So, maybe develop deploy() and undeploy().

|  Function name        |  Input      |    Output      | Note |
|-----------------------|:-----------:|---------------:|-------|
| get_res               | sp          | res            | As a 1d array. |
| dump_resGrid_unitBB   | grid_T, dir |       | for each band, write grid_res to "dir/bn.pickle" |
| load_resGrid_unitBB   |             |                | initializing self.l_res_grid|
| get_res_unitBB        | T           | res            | As a 1d array. |
