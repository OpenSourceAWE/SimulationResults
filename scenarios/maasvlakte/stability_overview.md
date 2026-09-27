# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total | α guided, c2 = 0 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.584 | 0.351 | marginal | 156 | 14.2 | 0.294 | 0.281 s | 0.288 | 1/23 | 0.477 **← worst** |
| v04 | 4.00 | 0.707 | 0.385 | marginal | 165 | 16.8 | 0.288 | 0.297 s | 0.280 | 1/23 | 0.491 |
| v05 | 5.00 | 0.944 | 0.403 | marginal | 155 | 19.5 | 0.280 | 0.295 s | 0.233 | 1/23 | 0.493 |
| v06 | 6.00 | 1.162 | 0.434 | marginal | 155 | 21.0 | 0.273 | 0.310 s | 0.165 | 2/23 | 0.517 |
| v07 | 7.00 | 1.283 | 0.445 | marginal | 165 | 25.2 | 0.269 | 0.305 s | 0.128 | 7/23 | 0.511 |
| v08 | 8.00 | 1.340 | 0.467 | marginal | 175 | 27.9 | 0.267 | 0.317 s | 0.106 | 6/23 | 0.526 |
| v08.25 | 8.25 | 1.344 | 0.467 | marginal | 175 | 28.5 | 0.267 | 0.317 s | 0.134 | 5/23 | 0.525 |
| v08.5 | 8.50 | 1.353 | 0.475 | marginal | 175 | 29.4 | 0.267 | 0.323 s | 0.152 | 3/23 | 0.531 |
| v09 | 9.00 | 1.351 | 0.440 | marginal | 175 | 29.9 | 0.272 | 0.298 s | 0.180 | 2/23 | 0.494 |
| v10 | 10.00 | 1.360 | 0.420 | marginal | 175 | 31.5 | 0.304 | 0.283 s | 0.208 | 2/23 | 0.470 |
| v11 | 11.00 | 1.345 | 0.394 | marginal | 195 | 30.9 | 0.324 | 0.268 s | 0.206 | 2/23 | 0.445 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity coefficient c2 of the turn-rate law cannot be identified, so α inner, α guided and DM guided are the worst case over c2 in C2_BOUNDS = (0.0, 2.45) (course_loop_model.jl); α guided, c2 = 0 is the guided margin without the gravity pole, the upper end of the range.
