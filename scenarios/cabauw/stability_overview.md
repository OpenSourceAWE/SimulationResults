# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total | α guided, c2 = 0 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.711 | 0.356 | marginal | 155 | 17.2 | 0.291 | 0.272 s | 0.247 | 1/23 | 0.458 **← worst** |
| v04 | 4.00 | 1.105 | 0.450 | marginal | 165 | 20.9 | 0.275 | 0.328 s | 0.191 | 2/23 | 0.536 |
| v05 | 5.00 | 1.294 | 0.452 | marginal | 165 | 26.4 | 0.269 | 0.310 s | 0.134 | 4/23 | 0.516 |
| v05.5 | 5.50 | 1.357 | 0.463 | marginal | 175 | 26.2 | 0.267 | 0.319 s | 0.129 | 4/23 | 0.527 |
| v05.75 | 5.75 | 1.366 | 0.476 | marginal | 175 | 28.8 | 0.266 | 0.325 s | 0.122 | 5/23 | 0.535 |
| v06 | 6.00 | 1.370 | 0.464 | marginal | 175 | 28.5 | 0.267 | 0.315 s | 0.149 | 2/23 | 0.521 |
| v06.25 | 6.25 | 1.371 | 0.448 | marginal | 175 | 29.5 | 0.268 | 0.303 s | 0.188 | 2/23 | 0.502 |
| v07 | 7.00 | 1.379 | 0.445 | marginal | 215 | 32.5 | 0.302 | 0.303 s | 0.216 | 2/23 | 0.496 |
| v08 | 8.00 | 1.389 | 0.390 | marginal | 175 | 33.5 | 0.326 | 0.264 s | 0.195 | 2/23 | 0.437 |
| v09 | 9.00 | 1.398 | 0.371 | marginal | 175 | 35.5 | 0.346 | 0.250 s | 0.190 | 2/23 | 0.415 |
| v10 | 10.00 | 1.392 | 0.358 | marginal | 175 | 37.2 | 0.364 | 0.240 s | 0.184 | 2/23 | 0.399 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity coefficient c2 of the turn-rate law cannot be identified, so α inner, α guided and DM guided are the worst case over c2 in C2_BOUNDS = (0.0, 2.45) (course_loop_model.jl); α guided, c2 = 0 is the guided margin without the gravity pole, the upper end of the range.
