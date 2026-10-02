# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.839 | 0.596 | robust | 210 | 10.1 | 0.288 | 0.459 s | 0.343 | 6/19 |
| v04 | 4.00 | 0.898 | 0.608 | robust | 200 | 11.8 | 0.284 | 0.451 s | 0.306 | 6/19 |
| v05 | 5.00 | 1.008 | 0.588 | robust | 155 | 16.9 | 0.280 | 0.394 s | 0.235 | 8/23 |
| v06 | 6.00 | 1.124 | 0.607 | robust | 155 | 21.2 | 0.272 | 0.386 s | 0.169 | 9/23 |
| v07 | 7.00 | 1.190 | 0.622 | robust | 165 | 25.2 | 0.268 | 0.380 s | 0.109 | 9/23 |
| v08 | 8.00 | 1.236 | 0.627 | robust | 175 | 27.1 | 0.267 | 0.379 s | 0.144 | 8/23 |
| v08.25 | 8.25 | 1.242 | 0.653 | robust | 175 | 28.6 | 0.267 | 0.393 s | 0.116 | 8/23 |
| v08.5 | 8.50 | 1.246 | 0.660 | robust | 175 | 29.4 | 0.267 | 0.396 s | 0.139 | 7/23 |
| v09 | 9.00 | 1.249 | 0.638 | robust | 175 | 30.0 | 0.273 | 0.381 s | 0.173 | 2/23 |
| v10 | 10.00 | 1.167 | 0.584 | robust | 175 | 30.8 | 0.305 | 0.349 s | 0.199 | 2/23 |
| v11 | 11.00 | 1.116 | 0.565 | robust | 175 | 32.0 | 0.324 | 0.337 s | 0.196 | 5/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
