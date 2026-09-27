# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.812 | 0.449 | marginal | 155 | 17.2 | 0.291 | 0.341 s | 0.247 | 1/23 |
| v04 | 4.00 | 1.150 | 0.531 | robust | 165 | 20.9 | 0.275 | 0.382 s | 0.191 | 2/23 |
| v05 | 5.00 | 1.319 | 0.516 | robust | 165 | 26.4 | 0.269 | 0.350 s | 0.134 | 4/23 |
| v05.5 | 5.50 | 1.375 | 0.529 | robust | 175 | 26.2 | 0.267 | 0.361 s | 0.129 | 4/23 |
| v05.75 | 5.75 | 1.383 | 0.525 | robust | 175 | 27.2 | 0.266 | 0.357 s | 0.122 | 5/23 |
| v06 | 6.00 | 1.385 | 0.523 | robust | 175 | 28.5 | 0.267 | 0.352 s | 0.149 | 2/23 |
| v06.25 | 6.25 | 1.377 | 0.503 | robust | 175 | 29.5 | 0.268 | 0.337 s | 0.188 | 2/23 |
| v07 | 7.00 | 1.387 | 0.490 | marginal | 215 | 32.5 | 0.302 | 0.331 s | 0.216 | 2/23 |
| v08 | 8.00 | 1.396 | 0.427 | marginal | 175 | 33.5 | 0.326 | 0.288 s | 0.195 | 2/23 |
| v09 | 9.00 | 1.382 | 0.411 | marginal | 175 | 35.5 | 0.346 | 0.276 s | 0.190 | 2/23 |
| v10 | 10.00 | 1.399 | 0.392 | marginal | 175 | 37.2 | 0.364 | 0.262 s | 0.184 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable.
