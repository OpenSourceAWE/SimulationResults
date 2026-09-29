# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.740 | 0.339 | marginal | 155 | 17.2 | 0.290 | 0.230 s | 0.251 | 1/23 **← worst** |
| v04 | 4.00 | 1.032 | 0.448 | marginal | 165 | 18.6 | 0.275 | 0.298 s | 0.200 | 3/23 |
| v05 | 5.00 | 1.179 | 0.503 | robust | 165 | 25.0 | 0.269 | 0.315 s | 0.137 | 6/23 |
| v05.5 | 5.50 | 1.236 | 0.518 | robust | 195 | 27.8 | 0.266 | 0.321 s | 0.122 | 5/23 |
| v05.75 | 5.75 | 1.251 | 0.519 | robust | 195 | 27.7 | 0.266 | 0.322 s | 0.168 | 2/23 |
| v06 | 6.00 | 1.201 | 0.494 | marginal | 195 | 28.4 | 0.267 | 0.307 s | 0.171 | 2/23 |
| v06.25 | 6.25 | 1.172 | 0.477 | marginal | 195 | 29.1 | 0.268 | 0.295 s | 0.192 | 2/23 |
| v07 | 7.00 | 1.160 | 0.494 | marginal | 175 | 31.1 | 0.300 | 0.307 s | 0.214 | 2/23 |
| v08 | 8.00 | 1.122 | 0.434 | marginal | 175 | 33.6 | 0.326 | 0.268 s | 0.189 | 2/23 |
| v09 | 9.00 | 1.086 | 0.429 | marginal | 175 | 35.0 | 0.346 | 0.264 s | 0.189 | 2/23 |
| v10 | 10.00 | 1.034 | 0.400 | marginal | 175 | 36.6 | 0.364 | 0.245 s | 0.187 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (plant_coeffs, course_loop_model.jl; the gain schedule keeps the turn-rate table, as flown); all margins are the worst case over the sign of its pole.
