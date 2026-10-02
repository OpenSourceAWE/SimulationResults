# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.923 | 0.635 | robust | 210 | 13.1 | 0.285 | 0.461 s | 0.271 | 8/19 |
| v04 | 4.00 | 1.103 | 0.614 | robust | 165 | 18.7 | 0.275 | 0.404 s | 0.188 | 8/23 |
| v05 | 5.00 | 1.221 | 0.628 | robust | 165 | 25.0 | 0.268 | 0.386 s | 0.126 | 9/23 |
| v05.5 | 5.50 | 1.248 | 0.643 | robust | 175 | 26.3 | 0.267 | 0.393 s | 0.149 | 7/23 |
| v05.75 | 5.75 | 1.260 | 0.645 | robust | 175 | 28.7 | 0.266 | 0.386 s | 0.156 | 6/23 |
| v06 | 6.00 | 1.261 | 0.638 | robust | 175 | 28.1 | 0.267 | 0.382 s | 0.140 | 4/23 |
| v06.25 | 6.25 | 1.205 | 0.624 | robust | 175 | 29.5 | 0.268 | 0.369 s | 0.172 | 2/23 |
| v07 | 7.00 | 1.175 | 0.576 | robust | 175 | 31.1 | 0.300 | 0.340 s | 0.179 | 2/23 |
| v08 | 8.00 | 1.160 | 0.538 | robust | 175 | 33.5 | 0.326 | 0.314 s | 0.196 | 2/23 |
| v09 | 9.00 | 1.076 | 0.508 | robust | 175 | 35.0 | 0.346 | 0.296 s | 0.165 | 2/23 |
| v10 | 10.00 | 1.031 | 0.477 | marginal | 195 | 37.6 | 0.364 | 0.274 s | 0.153 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
