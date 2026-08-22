# SimulationResults

Results of AWE simulations

## `scenarios/`

Archived runs of the 150 m reel-out optimizer scenario from
[SimpleKiteControllers.jl](https://github.com/OpenSourceAWE/SimpleKiteControllers.jl)
(`examples/simple_opt_reelout.jl`), one subfolder per **wind speed**: `vNN` is a mean
wind speed at 6m height of `NN` m/s, not a version counter. Each folder holds the latest run at that
wind speed. `SimpleKiteControllers.jl/output/scenarios` is a symlink into this folder,
so the two paths refer to the same data.

| folder | wind speed | mean reel-out power | peak    | run date   |
| ------ | ---------- | -------------------- | ------- | ---------- |
| `v03`  | 3 m/s      | 463 W                 | 1.2 kW  | 2026-08-21 |
| `v04`  | 4 m/s      | 1.6 kW                | 2.5 kW  | 2026-08-21 |
| `v05`  | 5 m/s      | 3.9 kW                | 4.6 kW  | 2026-08-21 |
| `v06`  | 6 m/s      | 7.3 kW                | 8.2 kW  | 2026-08-20 |
| `v07`  | 7 m/s      | 12.0 kW               | 13.2 kW | 2026-08-21 |
| `v08`  | 8 m/s      | 17.7 kW               | 21.4 kW | 2026-08-21 |
| `v09`  | 9 m/s      | 26.0 kW               | 31.5 kW | 2026-08-20 |
| `v10`  | 10 m/s     | 35.0 kW               | 53.8 kW | 2026-08-20 |

Each folder is a self-contained record of one run:

- `reelout_150m_opt.arrow` — the flight log (the simulation trace).
- `reelout_150m_opt.yaml` — a run summary written at the end of the run: git hash/dirty
  status, wind/turbulence settings, wall-clock time, `fig8_metrics` (cross-track error,
  elevation, tether force, turn rate, lap count, pattern extent vs. commanded amplitude,
  etc.) and measured vs. predicted power — read this first instead of loading the Arrow
  file.
- `fc_settings_reelout.yaml`, `settings_reelout_150m.yaml`, `system_reelout_150m.yaml`,
  `traj_opt.yaml`, `wc_settings.yaml`, `gui.yaml` — copies of every settings file that
  fed the run, so each archive is reproducible independent of whatever `data/` in
  SimpleKiteControllers.jl currently holds.

The runs come from different commits of SimpleKiteControllers.jl (`git_hash` in the
summary), so a comparison across wind speeds is not necessarily a comparison at one
fixed tuning — check the settings copies before reading a trend into the table.

`SimpleKiteControllers.jl`'s `output/` is overwritten by every new run, so these folders
are the durable record — read a run's numbers from its archive here, not from `output/`.
