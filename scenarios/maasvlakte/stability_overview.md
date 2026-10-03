# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.859 | 0.578 | robust | 200 | 9.2 | 0.281 | 0.455 s | 0.349 | 8/19 |
| v04 | 4.00 | 0.914 | 0.571 | robust | 200 | 12.1 | 0.277 | 0.418 s | 0.300 | 4/19 |
| v05 | 5.00 | 1.026 | 0.529 | robust | 155 | 16.9 | 0.274 | 0.346 s | 0.229 | 6/23 **← worst** |
| v06 | 6.00 | 1.143 | 0.529 | robust | 155 | 21.1 | 0.270 | 0.326 s | 0.151 | 4/23 |
| v07 | 7.00 | 1.227 | 0.605 | robust | 185 | 24.6 | 0.267 | 0.368 s | 0.113 | 9/23 |
| v08 | 8.00 | 1.232 | 0.620 | robust | 175 | 26.8 | 0.267 | 0.375 s | 0.123 | 7/23 |
| v08.25 | 8.25 | 1.241 | 0.649 | robust | 175 | 28.3 | 0.266 | 0.391 s | 0.109 | 7/23 |
| v08.5 | 8.50 | 1.240 | 0.649 | robust | 175 | 28.9 | 0.266 | 0.389 s | 0.095 | 4/23 |
| v09 | 9.00 | 1.244 | 0.649 | robust | 205 | 29.8 | 0.270 | 0.389 s | 0.172 | 2/23 |
| v10 | 10.00 | 1.203 | 0.615 | robust | 175 | 32.0 | 0.295 | 0.366 s | 0.216 | 2/23 |
| v11 | 11.00 | 1.162 | 0.579 | robust | 205 | 32.6 | 0.313 | 0.343 s | 0.185 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
