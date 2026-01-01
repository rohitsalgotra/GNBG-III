# GNBG-III MATLAB Competition Harness

This repository provides a **GNBG-III compatible MATLAB competition harness** for benchmarking optimization algorithms under a single, reproducible evaluation protocol.

It includes:
- A competition runner (`GNBG_III_CompetitionHarness.m`)
- GNBG-III benchmark `.mat` file loading (problems `F1_...` to `F24_...`)
- A participant algorithm template (`runAlgorithmTemplate.m`) — replace the internal logic only
- A mandatory evaluation interface via `fitness(X, GNBG)`
- Automatic export of detailed results to **.MAT** and **.CSV**

**Full protocol document:** `GNBG_III_Competition_Protocols.pdf`

---

## Repository structure (typical)


---

## Quick start

1. Clone the repository and open MATLAB in the repository folder.
2. Ensure the benchmark `.mat` files are present in:
   - `GNBG_III_Benchmarks/`
3. Run:
   - `GNBG_III_CompetitionHarness.m`

---

## How to implement your algorithm (participants)

Edit **only** the algorithm logic inside the provided template (example: `runAlgorithmTemplate.m`):

- ✅ Keep the **function signature** unchanged:
  ```matlab
  function [BestHistory, BestValue, BestPosition, GNBG, AcceptanceReachPoint, Extra] = ...
           runAlgorithmTemplate(GNBG, params)
