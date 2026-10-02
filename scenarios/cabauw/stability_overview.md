# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.923 | 0.635 | robust | 210 | 13.1 | 0.285 | 0.461 s | 0.271 | 8/19 |
| v04 | 4.00 | 1.106 | 0.615 | robust | 165 | 18.7 | 0.275 | 0.404 s | 0.150 | 7/23 |
| v05 | 5.00 | 1.225 | 0.631 | robust | 165 | 25.0 | 0.268 | 0.388 s | 0.125 | 10/23 |
| v05.5 | 5.50 | 1.248 | 0.642 | robust | 175 | 26.3 | 0.267 | 0.393 s | 0.126 | 6/23 |
| v05.75 | 5.75 | 1.260 | 0.656 | robust | 175 | 27.2 | 0.266 | 0.398 s | 0.131 | 6/23 |
| v06 | 6.00 | 1.259 | 0.653 | robust | 175 | 28.1 | 0.267 | 0.394 s | 0.141 | 4/23 |
| v06.25 | 6.25 | 1.204 | 0.646 | robust | 175 | 29.5 | 0.268 | 0.387 s | 0.181 | 2/23 |
| v07 | 7.00 | 1.179 | 0.617 | robust | 175 | 31.1 | 0.300 | 0.371 s | 0.197 | 2/23 |
| v08 | 8.00 | 1.159 | 0.577 | robust | 175 | 33.6 | 0.326 | 0.344 s | 0.196 | 2/23 |
| v09 | 9.00 | 1.076 | 0.550 | robust | 175 | 35.0 | 0.346 | 0.327 s | 0.157 | 2/23 |
| v10 | 10.00 | 1.033 | 0.523 | robust | 195 | 38.0 | 0.364 | 0.306 s | 0.167 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
