# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.710 | 0.293 | fragile | 155 | 17.2 | 0.291 | 0.227 s | 0.247 | 1/23 |
| v04 | 4.00 | 1.071 | 0.369 | marginal | 165 | 20.9 | 0.275 | 0.274 s | 0.191 | 2/23 |
| v05 | 5.00 | 1.261 | 0.360 | marginal | 165 | 26.4 | 0.269 | 0.252 s | 0.134 | 4/23 |
| v05.5 | 5.50 | 1.331 | 0.370 | marginal | 175 | 26.2 | 0.267 | 0.261 s | 0.129 | 4/23 |
| v05.75 | 5.75 | 1.342 | 0.378 | marginal | 175 | 28.8 | 0.266 | 0.264 s | 0.122 | 5/23 |
| v06 | 6.00 | 1.345 | 0.367 | marginal | 175 | 28.5 | 0.267 | 0.256 s | 0.149 | 2/23 |
| v06.25 | 6.25 | 1.346 | 0.353 | marginal | 175 | 29.5 | 0.268 | 0.244 s | 0.188 | 2/23 |
| v07 | 7.00 | 1.362 | 0.343 | marginal | 215 | 32.5 | 0.302 | 0.239 s | 0.216 | 2/23 |
| v08 | 8.00 | 1.371 | 0.290 | fragile | 175 | 33.5 | 0.326 | 0.200 s | 0.195 | 2/23 |
| v09 | 9.00 | 1.381 | 0.270 | fragile | 175 | 35.5 | 0.346 | 0.185 s | 0.190 | 2/23 |
| v10 | 10.00 | 1.378 | 0.257 | fragile | 175 | 37.2 | 0.364 | 0.175 s | 0.184 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c3·sin(ψ)·cos(β) with c3 = 0.23 1/s (course_loop_model.jl), identified on the flown figures of eight; all margins are the worst case over the sign of its pole.
