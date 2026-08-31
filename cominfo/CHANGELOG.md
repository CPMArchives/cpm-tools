# Changelog

## 0.1.0-dev1 — 2026-08-31

- Read COM files sequentially through standard CP/M 2.2 BDOS calls.
- Report logical records, logical bytes, and the 0100H load range.
- Count direct CALL 0005H, JMP 0000H, and other page-zero address patterns.
- Report Z80 prefix bytes as heuristic rather than definite findings.
- Add concise and `/V` or `/VERBOSE` detailed output.
- Add common help, information, and version commands.
