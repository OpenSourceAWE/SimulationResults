# Stability overview, cabauw

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03 | 3.00 | 0.993 | 0.560 | robust | 219 | 11.4 | 0.288 | 0.461 s | 0.281 | 0/19 **← worst** |
| v04 | 4.00 | 1.189 | 0.622 | robust | 265 | 19.5 | 0.276 | 0.444 s | 0.186 | 1/23 (1 not flown) |
| v05 | 5.00 | 1.305 | 0.615 | robust | 215 | 23.3 | 0.274 | 0.419 s | 0.140 | 1/23 (1 not flown) |
| v05.5 | 5.50 | 1.350 | 0.644 | robust | 195 | 24.8 | 0.273 | 0.438 s | 0.138 | 1/23 (1 not flown) |
| v05.75 | 5.75 | 1.387 | 0.650 | robust | 345 | 27.0 | 0.275 | 0.436 s | 0.128 | 2/23 (2 not flown) |
| v06 | 6.00 | 1.386 | 0.652 | robust | 225 | 26.5 | 0.273 | 0.439 s | 0.132 | 1/23 (2 not flown) |
| v06.25 | 6.25 | 1.382 | 0.654 | robust | 175 | 26.4 | 0.277 | 0.442 s | 0.148 | 1/23 (2 not flown) |
| v07 | 7.00 | 1.362 | 0.662 | robust | 325 | 31.5 | 0.314 | 0.445 s | 0.176 | 2/23 (2 not flown) |
| v08 | 8.00 | 1.302 | 0.638 | robust | 205 | 31.4 | 0.335 | 0.429 s | 0.166 | 2/23 (2 not flown) |
| v09 | 9.00 | 1.258 | 0.606 | robust | 175 | 32.7 | 0.366 | 0.403 s | 0.167 | 1/23 (2 not flown) |
| v10 | 10.00 | 1.249 | 0.617 | robust | 175 | 33.9 | 0.396 | 0.410 s | 0.125 | 1/23 (1 not flown) |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
