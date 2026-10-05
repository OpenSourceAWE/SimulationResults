# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.963 | 0.515 | robust | 200 | 8.7 | 0.291 | 0.521 s | 0.391 | 4/19 **← worst** |
| v04 | 4.00 | 0.975 | 0.537 | robust | 229 | 12.0 | 0.286 | 0.438 s | 0.294 | 1/19 |
| v05 | 5.00 | 1.053 | 0.580 | robust | 205 | 16.4 | 0.282 | 0.436 s | 0.257 | 2/23 |
| v06 | 6.00 | 1.175 | 0.585 | robust | 185 | 20.6 | 0.278 | 0.416 s | 0.207 | 4/23 |
| v07 | 7.00 | 1.235 | 0.619 | robust | 195 | 22.4 | 0.274 | 0.437 s | 0.181 | 2/23 |
| v08 | 8.00 | 1.290 | 0.657 | robust | 175 | 24.9 | 0.273 | 0.463 s | 0.143 | 3/23 |
| v08.25 | 8.25 | 1.292 | 0.669 | robust | 195 | 25.9 | 0.273 | 0.469 s | 0.163 | 2/23 |
| v08.5 | 8.50 | 1.281 | 0.674 | robust | 175 | 26.6 | 0.273 | 0.471 s | 0.161 | 2/23 |
| v09 | 9.00 | 1.286 | 0.667 | robust | 205 | 26.9 | 0.280 | 0.466 s | 0.137 | 2/23 |
| v10 | 10.00 | 1.246 | 0.618 | robust | 175 | 28.6 | 0.307 | 0.429 s | 0.153 | 3/23 |
| v11 | 11.00 | 1.145 | 0.582 | robust | 175 | 28.7 | 0.330 | 0.402 s | 0.168 | 1/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
