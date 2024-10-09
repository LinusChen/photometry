
Terminology/shorthands:
- bp: band pass
- sp: spectrum
- res: synthetic photometry, or "response", represented as an band-averaged flux, in Jy.
- get_res: normally mean "get response".
- ResultGrid: A class. Contains a parameter grid, and the pre-tabulated results of a (typically expensive-to-evaluate) function on it.

The functions in the following need be developed.

|  Function name        |  Input      |    Output      | Note |
|-----------------------|:-----------:|---------------:|-------|
| get_res               | bp, sp      | res            |
| get_res_unitBB        | bp, T       | res            |
| get_resGrid_unitBB    | bp, grid_T  | grid_res       | as ResultGrid |
| write_resGrid_unitBB  | bp, grid_T, bn, dir  | | write grid_res to "dir/bn.pickle" |

