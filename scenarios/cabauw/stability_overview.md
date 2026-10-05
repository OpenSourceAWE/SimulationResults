# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.986 | 0.536 | robust | 209 | 13.9 | 0.288 | 0.421 s | 0.281 | 1/19 |
| v04 | 4.00 | 1.125 | 0.565 | robust | 345 | 20.4 | 0.276 | 0.400 s | 0.183 | 2/23 |
| v05 | 5.00 | 1.243 | 0.562 | robust | 215 | 23.3 | 0.274 | 0.384 s | 0.140 | 2/23 |
| v05.5 | 5.50 | 1.120 | 0.574 | robust | 195 | 24.8 | 0.273 | 0.390 s | 0.159 | 2/23 |
| v05.75 | 5.75 | 1.173 | 0.583 | robust | 195 | 25.1 | 0.273 | 0.397 s | 0.127 | 1/23 |
| v06 | 6.00 | 1.276 | 0.595 | robust | 225 | 26.5 | 0.273 | 0.401 s | 0.133 | 2/23 |
| v06.25 | 6.25 | 1.310 | 0.590 | robust | 305 | 28.7 | 0.290 | 0.398 s | 0.148 | 1/23 |
| v07 | 7.00 | 1.205 | 0.565 | robust | 225 | 29.6 | 0.309 | 0.381 s | 0.176 | 1/23 |
| v08 | 8.00 | 1.145 | 0.526 | robust | 175 | 31.1 | 0.336 | 0.350 s | 0.159 | 1/23 |
| v09 | 9.00 | 1.068 | 0.451 | marginal | 235 | 32.7 | 0.365 | 0.297 s | 0.144 | 1/23 |
| v10 | 10.00 | 1.046 | 0.442 | marginal | 245 | 34.0 | 0.393 | 0.290 s | 0.170 | 1/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
