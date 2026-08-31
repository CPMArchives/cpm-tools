# BDOSPROBE changelog

## 0.1.0-dev2 — 2026-08-31

- Added `/DISK` probes for the login vector, current disk, and read-only vector.
- Added `/MEM` probes for the allocation-vector and DPB addresses.
- Added `/CONSOLE` using the observational console-status call.
- Reused the dev1 raw result-capture harness for every call.
- Validated all dev2 groups on Montezuma Micro CP/M 2.2 and under z80pack in
  Z80 and Intel 8080 modes.

## 0.1.0-dev1 — 2026-08-31

- Added the reusable post-BDOS register capture harness.
- Added `/CPM`, using only BDOS function 12 (Return Version Number).
- Reported raw A, BC, DE, HL, flags, and SP, while distinguishing documented
  results from incidental observations.
- Added Z80 and Intel 8080 execution tests.
