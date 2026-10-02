# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.765 | 0.389 | marginal | 156 | 15.6 | 0.293 | 0.255 s | 0.315 | 2/23 **← worst** |
| v04 | 4.00 | 0.784 | 0.418 | marginal | 165 | 16.8 | 0.289 | 0.273 s | 0.300 | 1/23 |
| v05 | 5.00 | 0.935 | 0.465 | marginal | 155 | 19.5 | 0.280 | 0.289 s | 0.237 | 1/23 |
| v06 | 6.00 | 1.064 | 0.495 | marginal | 155 | 21.1 | 0.272 | 0.300 s | 0.175 | 4/23 |
| v07 | 7.00 | 1.132 | 0.536 | robust | 165 | 25.2 | 0.268 | 0.319 s | 0.153 | 4/23 |
| v08 | 8.00 | 1.177 | 0.546 | robust | 175 | 27.1 | 0.267 | 0.323 s | 0.122 | 5/23 |
| v08.25 | 8.25 | 1.186 | 0.574 | robust | 175 | 28.5 | 0.267 | 0.339 s | 0.104 | 6/23 |
| v08.5 | 8.50 | 1.198 | 0.587 | robust | 175 | 29.4 | 0.267 | 0.346 s | 0.142 | 4/23 |
| v09 | 9.00 | 1.188 | 0.546 | robust | 205 | 29.7 | 0.273 | 0.321 s | 0.175 | 2/23 |
| v10 | 10.00 | 1.122 | 0.503 | robust | 175 | 30.7 | 0.305 | 0.296 s | 0.199 | 2/23 |
| v11 | 11.00 | 1.071 | 0.479 | marginal | 195 | 32.7 | 0.324 | 0.281 s | 0.193 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
