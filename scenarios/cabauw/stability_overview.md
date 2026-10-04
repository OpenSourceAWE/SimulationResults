# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.943 | 0.537 | robust | 210 | 12.5 | 0.279 | 0.387 s | 0.260 | 2/19 |
| v04 | 4.00 | 1.113 | 0.582 | robust | 295 | 21.0 | 0.269 | 0.365 s | 0.209 | 2/23 |
| v05 | 5.00 | 1.225 | 0.597 | robust | 185 | 24.3 | 0.268 | 0.363 s | 0.161 | 2/23 |
| v05.5 | 5.50 | 1.250 | 0.624 | robust | 195 | 26.4 | 0.267 | 0.378 s | 0.156 | 2/23 |
| v05.75 | 5.75 | 1.258 | 0.641 | robust | 365 | 28.5 | 0.268 | 0.384 s | 0.158 | 2/23 |
| v06 | 6.00 | 1.264 | 0.631 | robust | 275 | 29.4 | 0.272 | 0.377 s | 0.209 | 2/23 |
| v06.25 | 6.25 | 1.235 | 0.633 | robust | 225 | 30.0 | 0.273 | 0.379 s | 0.119 | 2/23 |
| v07 | 7.00 | 1.217 | 0.640 | robust | 355 | 33.3 | 0.302 | 0.383 s | 0.243 | 2/23 |
| v08 | 8.00 | 1.168 | 0.596 | robust | 175 | 33.3 | 0.317 | 0.356 s | 0.192 | 2/23 |
| v09 | 9.00 | 1.094 | 0.559 | robust | 175 | 35.3 | 0.342 | 0.331 s | 0.194 | 2/23 |
| v10 | 10.00 | 0.999 | 0.519 | robust | 175 | 35.8 | 0.365 | 0.307 s | 0.149 | 2/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
