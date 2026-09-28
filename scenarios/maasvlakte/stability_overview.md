# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.622 | 0.309 | marginal | 156 | 14.2 | 0.294 | 0.250 s | 0.288 | 1/23 |
| v04 | 4.00 | 0.706 | 0.323 | marginal | 165 | 16.8 | 0.288 | 0.253 s | 0.280 | 1/23 |
| v05 | 5.00 | 0.920 | 0.329 | marginal | 155 | 19.5 | 0.280 | 0.245 s | 0.233 | 1/23 |
| v06 | 6.00 | 1.127 | 0.354 | marginal | 155 | 21.0 | 0.273 | 0.258 s | 0.165 | 2/23 |
| v07 | 7.00 | 1.250 | 0.355 | marginal | 165 | 25.2 | 0.269 | 0.249 s | 0.128 | 7/23 |
| v08 | 8.00 | 1.310 | 0.372 | marginal | 175 | 27.9 | 0.267 | 0.259 s | 0.106 | 6/23 |
| v08.25 | 8.25 | 1.315 | 0.371 | marginal | 175 | 28.5 | 0.267 | 0.258 s | 0.134 | 5/23 |
| v08.5 | 8.50 | 1.326 | 0.377 | marginal | 175 | 29.4 | 0.267 | 0.262 s | 0.152 | 3/23 |
| v09 | 9.00 | 1.322 | 0.343 | marginal | 175 | 29.9 | 0.272 | 0.238 s | 0.180 | 2/23 |
| v10 | 10.00 | 1.337 | 0.320 | marginal | 175 | 31.5 | 0.304 | 0.221 s | 0.208 | 2/23 |
| v11 | 11.00 | 1.325 | 0.297 | fragile | 195 | 30.9 | 0.324 | 0.207 s | 0.206 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c3·sin(ψ)·cos(β) with c3 = 0.23 1/s (course_loop_model.jl), identified on the flown figures of eight; all margins are the worst case over the sign of its pole.
