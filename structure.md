
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
| get_resTable_unitBB    | bp, grid_T  | grid_res       | as ResTable |
| dump_resTable_unitBB  | bp, grid_T, bn, dir  |       | write grid_res to "dir/bn.pickle" |

The class ObservedSED need to have the methods in the following table.

|  Function name        |  Input      |    Output      | Note |
|-----------------------|:-----------:|---------------:|-------|
| get_res               | sp          | res            | As a 1d array. |
| dump_resTable_unitBB  | grid_T, dir |       | for each band, write grid_res to "dir/bn.pickle" |
| load_resTable_unitBB  |             |                | initializing self.l_res_grid|
| get_res_unitBB        | T           | res            | As a 1d array. |

Q: Can ResTable be pickled?
A: The data part certainly can pickled.
    Problem is about the interpolation function.
    So, maybe develop deploy() and undeploy().

Q: How to avoid redundantly creating the pretabulate tables?
A: develop a checking function check_file_resTable(filename, grid_perParam,).
   return code:
   - 0: a valid ResTable is read, with correct parameter grid.
   - 1: file not exist (or cannot be read).
   - 2: cannot pickle.load
   - 3: not a ResTable
   - 4: not on the correct grid.

Should I further develop a class ParamGrid?
could be over-design.
If I do, it should contain:
- the 1d grid for each parameter.
- keys_param
- shape (derived information).

