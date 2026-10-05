# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.991 | 0.542 | robust | 209 | 13.9 | 0.288 | 0.425 s | 0.281 | 1/19 |
| v04 | 4.00 | 1.141 | 0.578 | robust | 265 | 19.5 | 0.276 | 0.414 s | 0.186 | 2/23 |
| v05 | 5.00 | 1.248 | 0.602 | robust | 175 | 21.0 | 0.274 | 0.428 s | 0.136 | 2/23 |
| v05.5 | 5.50 | 1.119 | 0.642 | robust | 195 | 24.8 | 0.273 | 0.450 s | 0.156 | 2/23 |
| v05.75 | 5.75 | 1.297 | 0.653 | robust | 195 | 25.1 | 0.273 | 0.459 s | 0.126 | 1/23 |
| v06 | 6.00 | 1.271 | 0.660 | robust | 295 | 27.7 | 0.281 | 0.458 s | 0.131 | 2/23 |
| v06.25 | 6.25 | 1.311 | 0.660 | robust | 305 | 28.8 | 0.290 | 0.458 s | 0.148 | 1/23 |
| v07 | 7.00 | 1.116 | 0.642 | robust | 315 | 31.5 | 0.315 | 0.445 s | 0.193 | 2/23 |
| v08 | 8.00 | 1.116 | 0.589 | robust | 345 | 32.5 | 0.339 | 0.402 s | 0.162 | 2/23 |
| v09 | 9.00 | 1.079 | 0.536 | robust | 175 | 32.7 | 0.366 | 0.366 s | 0.166 | 2/23 (1 not flown) |
| v10 | 10.00 | 1.066 | 0.525 | robust | 175 | 33.9 | 0.396 | 0.358 s | 0.130 | 1/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
