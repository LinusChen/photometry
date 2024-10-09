The functions in the following need be developed.

Some shorthands in this document.
bp: band pass
sp: spectrum| get_response_unitBB   | bp, T     | flux          |

res: synthetic photometry, or "response", represented as an band-averaged flux, in Jy.
get_res: normally mean "get response".

|  Function name        |  Input      |    Output      |
|-----------------------|:-----------:|---------------:|
| get_res               | bp, sp      | res            |
| get_res_unitBB        | bp, T       | res            |
| get_resGrid_unitBB    | bp, grid_T  | grid_res       |

