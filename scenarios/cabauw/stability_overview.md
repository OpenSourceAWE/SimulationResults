# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.745 | 0.417 | marginal | 165 | 11.8 | 0.290 | 0.313 s | 0.265 | 1/23 **← worst** |
| v04 | 4.00 | 1.034 | 0.559 | robust | 165 | 18.7 | 0.275 | 0.371 s | 0.188 | 3/23 |
| v05 | 5.00 | 1.177 | 0.592 | robust | 165 | 25.0 | 0.268 | 0.365 s | 0.126 | 8/23 |
| v05.5 | 5.50 | 1.215 | 0.617 | robust | 175 | 26.3 | 0.267 | 0.378 s | 0.149 | 6/23 |
| v05.75 | 5.75 | 1.226 | 0.613 | robust | 175 | 28.7 | 0.266 | 0.368 s | 0.156 | 4/23 |
| v06 | 6.00 | 1.220 | 0.600 | robust | 175 | 28.1 | 0.267 | 0.360 s | 0.140 | 2/23 |
| v06.25 | 6.25 | 1.135 | 0.550 | robust | 175 | 29.5 | 0.268 | 0.328 s | 0.172 | 2/23 |
| v07 | 7.00 | 1.128 | 0.526 | robust | 175 | 31.1 | 0.300 | 0.313 s | 0.179 | 2/23 |
| v08 | 8.00 | 1.133 | 0.508 | robust | 175 | 33.5 | 0.326 | 0.298 s | 0.196 | 2/23 |
| v09 | 9.00 | 1.050 | 0.471 | marginal | 175 | 35.0 | 0.346 | 0.276 s | 0.165 | 2/23 |
| v10 | 10.00 | 1.005 | 0.438 | marginal | 195 | 37.6 | 0.364 | 0.253 s | 0.153 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
