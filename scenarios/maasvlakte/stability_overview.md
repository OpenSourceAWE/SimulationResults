# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.635 | 0.331 | marginal | 163 | 15.7 | 0.294 | 0.263 s | 0.290 | 2/23 |
| v04 | 4.00 | 0.713 | 0.320 | marginal | 165 | 16.8 | 0.289 | 0.249 s | 0.278 | 1/23 **← worst** |
| v05 | 5.00 | 0.927 | 0.338 | marginal | 155 | 19.5 | 0.280 | 0.251 s | 0.231 | 1/23 |
| v06 | 6.00 | 1.140 | 0.369 | marginal | 155 | 21.0 | 0.273 | 0.268 s | 0.166 | 5/23 |
| v07 | 7.00 | 1.265 | 0.403 | marginal | 165 | 25.2 | 0.269 | 0.289 s | 0.130 | 7/23 |
| v08 | 8.00 | 1.320 | 0.420 | marginal | 195 | 27.8 | 0.267 | 0.299 s | 0.111 | 6/23 |
| v08.25 | 8.25 | 1.323 | 0.419 | marginal | 175 | 28.5 | 0.267 | 0.299 s | 0.146 | 6/23 |
| v08.5 | 8.50 | 1.337 | 0.427 | marginal | 175 | 29.4 | 0.267 | 0.305 s | 0.158 | 4/23 |
| v09 | 9.00 | 1.335 | 0.398 | marginal | 205 | 30.0 | 0.274 | 0.282 s | 0.184 | 2/23 |
| v10 | 10.00 | 1.311 | 0.370 | marginal | 195 | 31.2 | 0.306 | 0.262 s | 0.204 | 2/23 |
| v11 | 11.00 | 1.325 | 0.345 | marginal | 195 | 31.0 | 0.324 | 0.245 s | 0.201 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c3·sin(ψ)·cos(β) with c3 = 0.23 1/s (course_loop_model.jl), identified on the flown figures of eight; all margins are the worst case over the sign of its pole.
