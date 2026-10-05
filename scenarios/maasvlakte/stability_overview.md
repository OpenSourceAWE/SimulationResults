# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.942 | 0.506 | robust | 200 | 8.7 | 0.291 | 0.509 s | 0.391 | 4/19 **← worst** |
| v04 | 4.00 | 0.947 | 0.538 | robust | 210 | 10.8 | 0.286 | 0.448 s | 0.294 | 1/19 |
| v05 | 5.00 | 1.067 | 0.606 | robust | 185 | 16.0 | 0.283 | 0.457 s | 0.257 | 2/23 |
| v06 | 6.00 | 1.229 | 0.631 | robust | 165 | 18.7 | 0.278 | 0.457 s | 0.207 | 4/23 |
| v07 | 7.00 | 1.294 | 0.621 | robust | 195 | 22.4 | 0.274 | 0.428 s | 0.182 | 2/23 |
| v08 | 8.00 | 1.350 | 0.654 | robust | 195 | 25.7 | 0.273 | 0.444 s | 0.156 | 1/23 |
| v08.25 | 8.25 | 1.383 | 0.657 | robust | 195 | 25.7 | 0.273 | 0.446 s | 0.168 | 2/23 |
| v08.5 | 8.50 | 1.347 | 0.661 | robust | 175 | 26.6 | 0.273 | 0.448 s | 0.158 | 2/23 |
| v09 | 9.00 | 1.344 | 0.654 | robust | 175 | 27.2 | 0.280 | 0.442 s | 0.137 | 2/23 |
| v10 | 10.00 | 1.346 | 0.631 | robust | 175 | 28.5 | 0.307 | 0.424 s | 0.155 | 4/23 (1 not flown) |
| v11 | 11.00 | 1.280 | 0.617 | robust | 175 | 30.4 | 0.330 | 0.411 s | 0.168 | 1/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
