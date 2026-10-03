# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.947 | 0.544 | robust | 210 | 12.7 | 0.279 | 0.390 s | 0.259 | 6/19 |
| v04 | 4.00 | 1.114 | 0.579 | robust | 315 | 21.2 | 0.269 | 0.363 s | 0.183 | 3/23 |
| v05 | 5.00 | 1.226 | 0.599 | robust | 185 | 24.4 | 0.268 | 0.364 s | 0.119 | 2/23 |
| v05.5 | 5.50 | 1.245 | 0.625 | robust | 195 | 26.5 | 0.267 | 0.379 s | 0.117 | 2/23 |
| v05.75 | 5.75 | 1.253 | 0.642 | robust | 315 | 28.7 | 0.267 | 0.384 s | 0.131 | 3/23 |
| v06 | 6.00 | 1.262 | 0.636 | robust | 345 | 30.6 | 0.276 | 0.380 s | 0.150 | 4/23 |
| v06.25 | 6.25 | 1.229 | 0.631 | robust | 225 | 30.0 | 0.273 | 0.378 s | 0.120 | 2/23 |
| v07 | 7.00 | 1.215 | 0.631 | robust | 355 | 33.1 | 0.301 | 0.376 s | 0.194 | 4/23 |
| v08 | 8.00 | 1.168 | 0.594 | robust | 175 | 33.5 | 0.317 | 0.354 s | 0.173 | 2/23 |
| v09 | 9.00 | 1.097 | 0.558 | robust | 175 | 35.3 | 0.342 | 0.331 s | 0.151 | 2/23 |
| v10 | 10.00 | 1.011 | 0.514 | robust | 175 | 36.1 | 0.365 | 0.303 s | 0.159 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
