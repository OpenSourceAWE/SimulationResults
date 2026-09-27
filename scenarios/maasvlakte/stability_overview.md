# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.744 | 0.466 | marginal | 156 | 14.2 | 0.294 | 0.369 s | 0.288 | 1/23 |
| v04 | 4.00 | 0.809 | 0.483 | marginal | 165 | 16.8 | 0.288 | 0.369 s | 0.280 | 1/23 |
| v05 | 5.00 | 1.012 | 0.487 | marginal | 155 | 19.5 | 0.280 | 0.352 s | 0.233 | 1/23 |
| v06 | 6.00 | 1.203 | 0.514 | robust | 155 | 21.0 | 0.273 | 0.362 s | 0.165 | 2/23 |
| v07 | 7.00 | 1.285 | 0.512 | robust | 165 | 25.2 | 0.269 | 0.347 s | 0.128 | 7/23 |
| v08 | 8.00 | 1.334 | 0.515 | robust | 175 | 27.0 | 0.267 | 0.348 s | 0.106 | 6/23 |
| v08.25 | 8.25 | 1.364 | 0.523 | robust | 175 | 27.2 | 0.267 | 0.356 s | 0.134 | 5/23 |
| v08.5 | 8.50 | 1.372 | 0.532 | robust | 175 | 29.4 | 0.267 | 0.358 s | 0.152 | 3/23 |
| v09 | 9.00 | 1.367 | 0.492 | marginal | 175 | 29.9 | 0.272 | 0.331 s | 0.180 | 2/23 |
| v10 | 10.00 | 1.370 | 0.464 | marginal | 175 | 31.5 | 0.304 | 0.312 s | 0.208 | 2/23 |
| v11 | 11.00 | 1.354 | 0.427 | marginal | 175 | 33.4 | 0.324 | 0.286 s | 0.206 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable.
