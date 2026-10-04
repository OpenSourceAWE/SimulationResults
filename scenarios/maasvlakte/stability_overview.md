# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.863 | 0.507 | robust | 209 | 11.9 | 0.281 | 0.369 s | 0.314 | 2/19 **← worst** |
| v04 | 4.00 | 0.920 | 0.535 | robust | 200 | 11.9 | 0.277 | 0.392 s | 0.288 | 2/19 |
| v05 | 5.00 | 1.035 | 0.586 | robust | 215 | 17.6 | 0.274 | 0.387 s | 0.275 | 4/23 |
| v06 | 6.00 | 1.153 | 0.581 | robust | 155 | 21.1 | 0.270 | 0.364 s | 0.235 | 2/23 |
| v07 | 7.00 | 1.225 | 0.600 | robust | 185 | 24.3 | 0.267 | 0.365 s | 0.231 | 3/23 |
| v08 | 8.00 | 1.246 | 0.634 | robust | 175 | 26.6 | 0.267 | 0.384 s | 0.189 | 3/23 |
| v08.25 | 8.25 | 1.250 | 0.650 | robust | 195 | 26.4 | 0.266 | 0.397 s | 0.187 | 3/23 |
| v08.5 | 8.50 | 1.249 | 0.651 | robust | 205 | 28.2 | 0.266 | 0.391 s | 0.153 | 2/23 |
| v09 | 9.00 | 1.247 | 0.635 | robust | 205 | 28.6 | 0.270 | 0.383 s | 0.190 | 2/23 |
| v10 | 10.00 | 1.207 | 0.614 | robust | 205 | 31.5 | 0.295 | 0.365 s | 0.187 | 2/23 |
| v11 | 11.00 | 1.165 | 0.579 | robust | 205 | 31.2 | 0.313 | 0.345 s | 0.189 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
