# Stability overview, maasvlakte

Worst disk margin per scenario (live controller settings).

| scenario | wind [m/s] | α inner | α guided | verdict | at L [m] | v_a [m/s] | depower | DM guided | τ_kite [s] | bins not rated/total |
|---|---|---|---|---|---|---|---|---|---|---|
| v03.5 | 3.50 | 0.720 | 0.312 | marginal | 156 | 15.2 | 0.294 | 0.216 s | 0.296 | 1/23 **← worst** |
| v04 | 4.00 | 0.753 | 0.347 | marginal | 165 | 16.8 | 0.289 | 0.237 s | 0.283 | 1/23 |
| v05 | 5.00 | 0.889 | 0.386 | marginal | 155 | 19.5 | 0.280 | 0.252 s | 0.232 | 1/23 |
| v06 | 6.00 | 1.072 | 0.424 | marginal | 155 | 21.1 | 0.272 | 0.271 s | 0.175 | 6/23 |
| v07 | 7.00 | 1.158 | 0.494 | marginal | 165 | 25.2 | 0.268 | 0.309 s | 0.167 | 5/23 |
| v08 | 8.00 | 1.220 | 0.513 | robust | 195 | 27.5 | 0.267 | 0.319 s | 0.109 | 6/23 |
| v08.25 | 8.25 | 1.219 | 0.513 | robust | 175 | 28.5 | 0.267 | 0.318 s | 0.154 | 6/23 |
| v08.5 | 8.50 | 1.227 | 0.521 | robust | 175 | 29.4 | 0.267 | 0.323 s | 0.158 | 4/23 |
| v09 | 9.00 | 1.196 | 0.504 | robust | 205 | 29.7 | 0.271 | 0.312 s | 0.186 | 2/23 |
| v10 | 10.00 | 1.150 | 0.471 | marginal | 195 | 31.3 | 0.305 | 0.289 s | 0.204 | 2/23 |
| v11 | 11.00 | 1.116 | 0.437 | marginal | 195 | 32.4 | 0.324 | 0.269 s | 0.206 | 2/23 |

α inner is the disk margin of the course PID closed only around the turn-rate plant (no guidance law); α guided is the disk margin of the actual flown loop, PID → guidance law → pattern-law kite dynamics, and is the value that is rated; DM guided is that same guided loop's delay margin, the extra pure delay it could absorb before going unstable. The gravity term of the turn-rate law is c2(u_d)/v_a·sin(ψ)·cos(β), with c1(u_d) and c2(u_d) of the plant identified in the low crosswind pattern (plant_coeffs, course_loop_model.jl; the gain schedule keeps the turn-rate table, as flown); all margins are the worst case over the sign of its pole.
