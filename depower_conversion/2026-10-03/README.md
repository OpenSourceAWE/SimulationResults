# Depower identification record, 2026-10-03

The runs `examples/identify_depower_conversion.jl` (SimpleKiteControllers.jl)
replays to identify the conversion of the optimizer's tape length `l_dp` into
V3Kite's `rel_depower`.

`runs/<site>_v<wind>/` holds one reel-out run per site and wind speed: Cabauw
4–10 m/s and Maasvlakte 3.5, 4, 8, 10 and 11 m/s. Each folder has

- `<log>_opt_paths.yaml`: the paths the run installed, as returned by the optimizer;
- `<log>_opt_entries.json`: the optimizer results of these paths, so the folder
  replays without the local solution cache;
- `<log>.yaml`: the run summary.

The flight logs (`.arrow`, about 70 MB each) are not kept. The runs were flown
on 2026-10-03 with SimpleKiteControllers.jl at commit 79c74e3 and passed all
10 success criteria. They are fresh runs of the scenario set, not the archived
scenarios: runs on different machines part after the first few paths.

The findings, including why Maasvlakte 3.5 and 4 m/s do not fit the
conversion, are in `docs/power_ratio_findings.md` of SimpleKiteControllers.jl.
