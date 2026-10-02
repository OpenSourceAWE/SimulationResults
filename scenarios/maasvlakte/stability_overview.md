# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.747 | 0.414 | marginal | 155 | 10.7 | 0.294 | 0.316 s | 0.322 | 1/23 **← worst** |
| v04 | 4.00 | 0.760 | 0.436 | marginal | 156 | 10.9 | 0.289 | 0.332 s | 0.300 | 1/23 |
| v05 | 5.00 | 0.917 | 0.508 | robust | 155 | 16.9 | 0.280 | 0.344 s | 0.231 | 2/23 |
| v06 | 6.00 | 1.078 | 0.570 | robust | 155 | 21.2 | 0.272 | 0.363 s | 0.170 | 7/23 |
| v07 | 7.00 | 1.157 | 0.594 | robust | 165 | 25.2 | 0.268 | 0.364 s | 0.127 | 8/23 |
| v08 | 8.00 | 1.181 | 0.574 | robust | 175 | 27.1 | 0.267 | 0.348 s | 0.148 | 6/23 |
| v08.25 | 8.25 | 1.194 | 0.599 | robust | 175 | 28.6 | 0.267 | 0.359 s | 0.110 | 6/23 |
| v08.5 | 8.50 | 1.200 | 0.600 | robust | 175 | 29.4 | 0.267 | 0.358 s | 0.139 | 7/23 |
| v09 | 9.00 | 1.178 | 0.547 | robust | 175 | 30.0 | 0.273 | 0.325 s | 0.171 | 2/23 |
| v10 | 10.00 | 1.118 | 0.495 | marginal | 175 | 30.7 | 0.305 | 0.292 s | 0.201 | 2/23 |
| v11 | 11.00 | 1.073 | 0.481 | marginal | 175 | 31.9 | 0.324 | 0.283 s | 0.190 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
