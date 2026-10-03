# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.923 | 0.654 | robust | 210 | 13.1 | 0.283 | 0.474 s | 0.268 | 7/19 |
| v04 | 4.00 | 1.113 | 0.621 | robust | 165 | 18.7 | 0.273 | 0.409 s | 0.177 | 10/23 |
| v05 | 5.00 | 1.227 | 0.632 | robust | 165 | 25.0 | 0.268 | 0.389 s | 0.114 | 9/23 |
| v05.5 | 5.50 | 1.246 | 0.642 | robust | 175 | 26.3 | 0.267 | 0.392 s | 0.086 | 8/23 |
| v05.75 | 5.75 | 1.289 | 0.659 | robust | 175 | 27.2 | 0.266 | 0.400 s | 0.131 | 4/23 |
| v06 | 6.00 | 1.260 | 0.653 | robust | 175 | 28.3 | 0.267 | 0.393 s | 0.124 | 2/23 |
| v06.25 | 6.25 | 1.237 | 0.650 | robust | 175 | 28.8 | 0.270 | 0.390 s | 0.185 | 2/23 |
| v07 | 7.00 | 1.182 | 0.626 | robust | 185 | 31.9 | 0.298 | 0.375 s | 0.227 | 3/23 |
| v08 | 8.00 | 1.165 | 0.584 | robust | 195 | 33.8 | 0.321 | 0.348 s | 0.190 | 2/23 |
| v09 | 9.00 | 1.112 | 0.566 | robust | 175 | 35.2 | 0.339 | 0.335 s | 0.161 | 2/23 |
| v10 | 10.00 | 1.033 | 0.523 | robust | 195 | 38.0 | 0.364 | 0.306 s | 0.167 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
