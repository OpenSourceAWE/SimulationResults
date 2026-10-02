# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.839 | 0.596 | robust | 210 | 10.1 | 0.288 | 0.459 s | 0.343 | 6/19 |
| v04 | 4.00 | 0.898 | 0.608 | robust | 200 | 11.8 | 0.284 | 0.451 s | 0.306 | 6/19 |
| v05 | 5.00 | 1.005 | 0.583 | robust | 155 | 16.9 | 0.280 | 0.391 s | 0.231 | 6/23 |
| v06 | 6.00 | 1.122 | 0.606 | robust | 155 | 21.2 | 0.272 | 0.385 s | 0.170 | 9/23 |
| v07 | 7.00 | 1.191 | 0.622 | robust | 165 | 25.2 | 0.268 | 0.380 s | 0.127 | 9/23 |
| v08 | 8.00 | 1.239 | 0.623 | robust | 175 | 27.1 | 0.267 | 0.376 s | 0.148 | 9/23 |
| v08.25 | 8.25 | 1.242 | 0.641 | robust | 175 | 28.6 | 0.267 | 0.383 s | 0.110 | 8/23 |
| v08.5 | 8.50 | 1.244 | 0.639 | robust | 175 | 29.4 | 0.267 | 0.380 s | 0.139 | 7/23 |
| v09 | 9.00 | 1.244 | 0.608 | robust | 175 | 30.0 | 0.273 | 0.359 s | 0.171 | 2/23 |
| v10 | 10.00 | 1.167 | 0.544 | robust | 175 | 30.7 | 0.305 | 0.319 s | 0.201 | 2/23 |
| v11 | 11.00 | 1.116 | 0.525 | robust | 175 | 31.9 | 0.324 | 0.308 s | 0.190 | 3/23 **← worst** |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (the turn-rate table, data/turn_rate_coeffs.yaml, which the gain schedule uses too); all margins are the worst case over the sign of its pole.
