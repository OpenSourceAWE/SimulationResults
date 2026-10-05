# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.955 | 0.508 | robust | 200 | 8.7 | 0.291 | 0.515 s | 0.388 | 4/19 **← worst** |
| v04 | 4.00 | 0.969 | 0.531 | robust | 229 | 12.0 | 0.286 | 0.434 s | 0.294 | 1/19 |
| v05 | 5.00 | 1.047 | 0.573 | robust | 185 | 16.0 | 0.283 | 0.434 s | 0.257 | 2/23 |
| v06 | 6.00 | 1.169 | 0.578 | robust | 185 | 20.6 | 0.278 | 0.412 s | 0.207 | 4/23 |
| v07 | 7.00 | 1.229 | 0.567 | robust | 195 | 22.4 | 0.274 | 0.392 s | 0.183 | 2/23 |
| v08 | 8.00 | 1.289 | 0.588 | robust | 175 | 24.9 | 0.273 | 0.402 s | 0.157 | 2/23 |
| v08.25 | 8.25 | 1.291 | 0.601 | robust | 195 | 25.7 | 0.273 | 0.409 s | 0.168 | 2/23 |
| v08.5 | 8.50 | 1.280 | 0.608 | robust | 175 | 26.6 | 0.273 | 0.412 s | 0.161 | 2/23 |
| v09 | 9.00 | 1.284 | 0.600 | robust | 175 | 27.2 | 0.280 | 0.406 s | 0.137 | 2/23 |
| v10 | 10.00 | 1.245 | 0.548 | robust | 175 | 28.5 | 0.307 | 0.369 s | 0.156 | 4/23 (1 not flown) |
| v11 | 11.00 | 1.166 | 0.509 | robust | 175 | 28.7 | 0.329 | 0.341 s | 0.169 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
