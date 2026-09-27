# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/flown |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.764 | 0.409 | marginal | 155 | 17.2 | 0.291 | 0.314 s | 0.247 | 1/0 |
| v04 | 4.00 | 0.973 | 0.570 | robust | 165 | 20.9 | 0.275 | 0.408 s | 0.191 | 2/0 |
| v05 | 5.00 | 1.185 | 0.539 | robust | 165 | 26.4 | 0.269 | 0.365 s | 0.134 | 4/0 |
| v05.5 | 5.50 | 1.256 | 0.552 | robust | 165 | 28.0 | 0.267 | 0.372 s | 0.129 | 4/0 |
| v05.75 | 5.75 | 1.213 | 0.550 | robust | 315 | 28.8 | 0.270 | 0.430 s | 0.122 | 5/0 |
| v06 | 6.00 | 1.189 | 0.559 | robust | 175 | 28.5 | 0.267 | 0.375 s | 0.149 | 2/0 |
| v06.25 | 6.25 | 1.018 | 0.458 | marginal | 355 | 30.2 | 0.293 | 0.419 s | 0.188 | 2/0 |
| v07 | 7.00 | 1.239 | 0.462 | marginal | 205 | 31.7 | 0.301 | 0.322 s | 0.216 | 2/0 |
| v08 | 8.00 | 1.153 | 0.465 | marginal | 255 | 35.2 | 0.326 | 0.332 s | 0.195 | 2/0 |
| v09 | 9.00 | 1.041 | 0.388 | marginal | 365 | 37.6 | 0.345 | 0.353 s | 0.190 | 2/0 |
| v10 | 10.00 | 0.560 | 0.000 | fragile | 355 | 38.4 | 0.365 | 0.000 s | 0.184 | 2/0 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable.
