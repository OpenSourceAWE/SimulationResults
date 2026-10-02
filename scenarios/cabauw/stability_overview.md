# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.734 | 0.334 | marginal | 165 | 11.9 | 0.290 | 0.247 s | 0.262 | 1/23 **← worst** |
| v04 | 4.00 | 1.029 | 0.469 | marginal | 165 | 18.7 | 0.275 | 0.303 s | 0.196 | 3/23 |
| v05 | 5.00 | 1.180 | 0.532 | robust | 165 | 25.0 | 0.268 | 0.319 s | 0.122 | 5/23 |
| v05.5 | 5.50 | 1.204 | 0.554 | robust | 175 | 26.3 | 0.267 | 0.332 s | 0.112 | 6/23 |
| v05.75 | 5.75 | 1.241 | 0.573 | robust | 195 | 27.7 | 0.266 | 0.340 s | 0.132 | 4/23 |
| v06 | 6.00 | 1.196 | 0.551 | robust | 195 | 28.3 | 0.267 | 0.327 s | 0.151 | 2/23 |
| v06.25 | 6.25 | 1.143 | 0.538 | robust | 195 | 29.0 | 0.268 | 0.317 s | 0.176 | 2/23 |
| v07 | 7.00 | 1.122 | 0.519 | robust | 175 | 31.1 | 0.300 | 0.309 s | 0.206 | 2/23 |
| v08 | 8.00 | 1.132 | 0.508 | robust | 175 | 33.5 | 0.326 | 0.298 s | 0.194 | 2/23 |
| v09 | 9.00 | 1.045 | 0.460 | marginal | 175 | 35.0 | 0.346 | 0.270 s | 0.171 | 2/23 |
| v10 | 10.00 | 0.994 | 0.420 | marginal | 195 | 37.6 | 0.364 | 0.244 s | 0.174 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
