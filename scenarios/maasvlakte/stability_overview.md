# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.839 | 0.602 | robust | 210 | 12.0 | 0.287 | 0.446 s | 0.342 | 6/19 |
| v04 | 4.00 | 0.898 | 0.606 | robust | 200 | 11.9 | 0.282 | 0.449 s | 0.297 | 8/19 |
| v05 | 5.00 | 1.007 | 0.586 | robust | 155 | 16.9 | 0.278 | 0.393 s | 0.218 | 4/23 |
| v06 | 6.00 | 1.152 | 0.609 | robust | 155 | 21.1 | 0.271 | 0.387 s | 0.160 | 9/23 |
| v07 | 7.00 | 1.220 | 0.622 | robust | 165 | 25.2 | 0.268 | 0.380 s | 0.116 | 10/23 |
| v08 | 8.00 | 1.243 | 0.650 | robust | 175 | 27.8 | 0.266 | 0.392 s | 0.101 | 9/23 |
| v08.25 | 8.25 | 1.245 | 0.653 | robust | 175 | 28.4 | 0.266 | 0.393 s | 0.147 | 9/23 |
| v08.5 | 8.50 | 1.246 | 0.657 | robust | 175 | 29.2 | 0.266 | 0.395 s | 0.141 | 7/23 |
| v09 | 9.00 | 1.249 | 0.655 | robust | 175 | 28.1 | 0.272 | 0.399 s | 0.174 | 2/23 |
| v10 | 10.00 | 1.213 | 0.608 | robust | 175 | 27.4 | 0.278 | 0.361 s | 0.194 | 5/23 |
| v11 | 11.00 | 1.150 | 0.571 | robust | 195 | 31.8 | 0.319 | 0.341 s | 0.188 | 3/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
