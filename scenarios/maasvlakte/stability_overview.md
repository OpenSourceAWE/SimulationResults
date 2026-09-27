# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/flown |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.497 | 0.328 | marginal | 264 | 15.9 | 0.289 | 0.322 s | 0.288 | 1/0 **← worst** |
| v04 | 4.00 | 0.644 | 0.419 | marginal | 155 | 16.8 | 0.288 | 0.325 s | 0.280 | 1/0 |
| v05 | 5.00 | 0.829 | 0.521 | robust | 155 | 19.5 | 0.280 | 0.374 s | 0.233 | 1/0 |
| v06 | 6.00 | 1.066 | 0.540 | robust | 155 | 21.0 | 0.273 | 0.379 s | 0.165 | 2/0 |
| v07 | 7.00 | 1.286 | 0.523 | robust | 165 | 25.2 | 0.269 | 0.354 s | 0.128 | 7/0 |
| v08 | 8.00 | 1.313 | 0.548 | robust | 175 | 27.0 | 0.267 | 0.370 s | 0.106 | 6/0 |
| v08.25 | 8.25 | 1.152 | 0.517 | robust | 195 | 29.5 | 0.267 | 0.356 s | 0.134 | 5/0 |
| v08.5 | 8.50 | 1.231 | 0.514 | robust | 195 | 30.2 | 0.267 | 0.352 s | 0.152 | 3/0 |
| v09 | 9.00 | 1.156 | 0.505 | robust | 195 | 29.3 | 0.272 | 0.352 s | 0.180 | 2/0 |
| v10 | 10.00 | 1.347 | 0.476 | marginal | 195 | 32.3 | 0.304 | 0.319 s | 0.208 | 2/0 |
| v11 | 11.00 | 1.244 | 0.429 | marginal | 195 | 30.9 | 0.324 | 0.291 s | 0.206 | 2/0 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable.
