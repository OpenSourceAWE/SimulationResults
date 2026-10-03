# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.858 | 0.515 | robust | 239 | 11.2 | 0.282 | 0.382 s | 0.326 | 4/19 **← worst** |
| v04 | 4.00 | 0.917 | 0.538 | robust | 200 | 12.1 | 0.277 | 0.391 s | 0.292 | 6/19 |
| v05 | 5.00 | 1.025 | 0.580 | robust | 215 | 17.7 | 0.274 | 0.382 s | 0.245 | 3/23 |
| v06 | 6.00 | 1.146 | 0.578 | robust | 155 | 21.1 | 0.270 | 0.363 s | 0.173 | 5/23 |
| v07 | 7.00 | 1.222 | 0.601 | robust | 185 | 24.6 | 0.267 | 0.365 s | 0.124 | 6/23 |
| v08 | 8.00 | 1.239 | 0.627 | robust | 175 | 26.8 | 0.267 | 0.379 s | 0.160 | 2/23 |
| v08.25 | 8.25 | 1.244 | 0.642 | robust | 195 | 26.8 | 0.266 | 0.391 s | 0.131 | 6/23 |
| v08.5 | 8.50 | 1.246 | 0.653 | robust | 205 | 28.9 | 0.266 | 0.392 s | 0.151 | 3/23 |
| v09 | 9.00 | 1.242 | 0.647 | robust | 205 | 29.8 | 0.270 | 0.388 s | 0.183 | 2/23 |
| v10 | 10.00 | 1.205 | 0.617 | robust | 175 | 32.0 | 0.295 | 0.367 s | 0.199 | 2/23 |
| v11 | 11.00 | 1.163 | 0.580 | robust | 205 | 32.7 | 0.313 | 0.344 s | 0.185 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
