# Depower conversion identification, 2026-10-05 (wing drag 0.03)

Record of the depower conversion in `SimpleKiteControllers.jl/data/depower_conversion.yaml`
for the kite with parasitic wing drag, `wing_drag_coeff = 0.03` (branch `wing_with_drag`;
see `docs/power_ratio_findings.md`, section (4)). The record of the kite without wing drag
is `../2026-10-03`.

The fit: offset 0.1076, slope 0.1392 1/m, curvature 0.2427 1/m², tape lengths 1.40–1.91 m,
pivot 1.43 m, offset fitted (`fit_offset = true`); 30 phase-4 paths of 10 base runs, weighted
RMS residual 0.0034. `points.csv` holds the per-path table, `fit.yaml` the fit and the
conversion in force while the replays were flown.

## How it was made

The kite with drag pulls more force per dynamic pressure than without (its wing pitches up),
so the conversion of 2026-10-03 gave far too little depower, and the replays at shifts of
±0.01 could not bracket the zero. The conversion was therefore iterated on base runs first:

1. Base runs (Cabauw 4–10, Maasvlakte 8, 10, 11 m/s, `simple_opt_reelout.jl` with the live
   optimizer) with a conversion interpolated between the no-drag fit and a fit for drag 0.07.
   Power ratios 0.95–1.07; 9 of 10 passed all criteria.
2. Per path a depower correction `ln(F_meas/F_pred) / 10`, fitted to a new quadratic
   (offset 0.1065, slope 0.1425, curvature 0.2387), and the base runs flown again: power
   ratios 0.94–1.03, 9 of 10 passed (Cabauw 10 m/s over the force limit in phase 5 only).
3. The second round is `runs/` here. Its paths were replayed at depower shifts −0.01, 0 and
   +0.01 with `identify_depower_conversion.jl` (`fit_offset = true`), which gave the fit above,
   within 0.001 of step 2.

The same settings as the runs were in force: the turn-rate table identified with drag 0.03,
the turn-radius request sized with `request_depower_estimate` (`seed:` section of
`traj_opt.yaml`), and the high-wind pattern box widened to ±36° and an elevation half-span
of 13°.

## Files

- `runs/<site>_v<wind>/`: per base run the summary YAML, `_opt_entries.json` (the optimizer
  results, so the runs replay without the solution cache) and `_opt_paths.yaml`. The logs
  (about 70 MB each) are not kept.
- `points.csv`, `fit.yaml`: written by `identify_depower_conversion.jl` with `save = true`.
