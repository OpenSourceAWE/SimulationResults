# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.940 | 0.602 | robust | 210 | 12.8 | 0.279 | 0.436 s | 0.259 | 4/19 |
| v04 | 4.00 | 1.114 | 0.562 | robust | 165 | 20.8 | 0.271 | 0.351 s | 0.179 | 7/23 |
| v05 | 5.00 | 1.223 | 0.604 | robust | 185 | 24.4 | 0.268 | 0.368 s | 0.157 | 4/23 |
| v05.5 | 5.50 | 1.247 | 0.626 | robust | 195 | 26.5 | 0.267 | 0.380 s | 0.154 | 6/23 |
| v05.75 | 5.75 | 1.251 | 0.646 | robust | 195 | 27.7 | 0.266 | 0.390 s | 0.139 | 4/23 |
| v06 | 6.00 | 1.259 | 0.651 | robust | 195 | 28.4 | 0.267 | 0.392 s | 0.146 | 4/23 |
| v06.25 | 6.25 | 1.231 | 0.635 | robust | 225 | 30.0 | 0.273 | 0.381 s | 0.126 | 2/23 |
| v07 | 7.00 | 1.214 | 0.643 | robust | 245 | 33.9 | 0.295 | 0.384 s | 0.203 | 4/23 |
| v08 | 8.00 | 1.168 | 0.594 | robust | 175 | 33.5 | 0.317 | 0.354 s | 0.173 | 2/23 |
| v09 | 9.00 | 1.096 | 0.559 | robust | 175 | 35.3 | 0.342 | 0.331 s | 0.169 | 2/23 |
| v10 | 10.00 | 1.011 | 0.514 | robust | 175 | 36.1 | 0.365 | 0.303 s | 0.159 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
