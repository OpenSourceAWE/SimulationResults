# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.721 | 0.307 | marginal | 155 | 17.2 | 0.291 | 0.237 s | 0.247 | 1/23 |
| v04 | 4.00 | 1.085 | 0.385 | marginal | 165 | 20.9 | 0.275 | 0.285 s | 0.194 | 3/23 |
| v05 | 5.00 | 1.273 | 0.402 | marginal | 165 | 25.0 | 0.269 | 0.288 s | 0.134 | 5/23 |
| v05.5 | 5.50 | 1.340 | 0.418 | marginal | 175 | 26.2 | 0.267 | 0.302 s | 0.130 | 4/23 |
| v05.75 | 5.75 | 1.349 | 0.426 | marginal | 195 | 28.9 | 0.266 | 0.304 s | 0.163 | 3/23 |
| v06 | 6.00 | 1.349 | 0.413 | marginal | 195 | 28.9 | 0.267 | 0.295 s | 0.174 | 2/23 |
| v06.25 | 6.25 | 1.346 | 0.394 | marginal | 195 | 29.1 | 0.268 | 0.279 s | 0.188 | 2/23 |
| v07 | 7.00 | 1.351 | 0.378 | marginal | 215 | 32.5 | 0.302 | 0.269 s | 0.206 | 2/23 |
| v08 | 8.00 | 1.375 | 0.351 | marginal | 195 | 33.8 | 0.326 | 0.247 s | 0.198 | 2/23 |
| v09 | 9.00 | 1.371 | 0.311 | marginal | 195 | 35.6 | 0.346 | 0.219 s | 0.179 | 2/23 |
| v10 | 10.00 | 1.361 | 0.288 | fragile | 175 | 37.2 | 0.364 | 0.202 s | 0.176 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c3·sin(ψ)·cos(β) with c3 = 0.23 1/s (course_loop_model.jl), identified on the flown figures of eight; all margins are the worst case over the sign of its pole.
