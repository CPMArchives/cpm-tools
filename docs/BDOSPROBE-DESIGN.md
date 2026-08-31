# BDOSPROBE safety and probe design

BDOSPROBE is an observation harness, not a conformance verdict generator. A
probe records inputs, immediate machine-level returns, and a conservative
interpretation. It does not infer that an incidental register value is part of
the BDOS contract.

The CP/M executable is `BDOSPRB.COM`, shortened to fit the 8.3 filename limit.

## Probe admission matrix

| Class | Examples | Initial policy |
|---|---|---|
| Pure observation | 11 console status; 12 version; 24 login vector; 25 current disk; 27 allocation vector; 29 read-only vector; 31 DPB address | Admit one at a time after documenting inputs and official outputs. |
| Query with sentinel | 32 get user number with E=FFH | Admit only in the documented query form. |
| Reversible process state | select disk, set DMA, set user | Defer until the harness captures the old value, restores it on every exit, and tests restoration. |
| Filesystem activity | search, open, read, close | Defer; use named disposable fixtures and document directory/FCB side effects. |
| Persistent write | create, write, delete, rename, set attributes | Excluded from ordinary probes. Any future destructive suite must be separate, explicit, and run only on disposable media. |
| Termination or reset | warm boot, terminate, reset disk system | Excluded until an isolated child-probe design can preserve and report results safely. |

## Dev2 boundary

Dev1 established function 12. Dev2 also admits functions 11, 24, 25, 27, 29,
and 31, grouped as `/CONSOLE`, `/DISK`, and `/MEM`. Before each call it records
the intended inputs
`C=0CH` and `DE=0000H`. Immediately after return it saves A, HL, BC, DE, flags,
and the balanced stack pointer. A and HL are shown as the documented version
results; BC, DE, flags, and SP are raw harness observations.

The source uses only 8080 instructions despite Zilog assembly spelling. The
same executable is tested under z80pack's Z80 and Intel 8080 modes.

No dev2 call writes a disk or intentionally changes BDOS process state.

## Planned sequence

1. Compare the observational returns across several CP/M-compatible systems.
2. Add query-sentinel calls such as function 32 only after exact input-state
   display and unchanged-state tests exist.
3. Design save/restore guards before admitting any reversible state change.
4. Keep persistent writes, termination, and reset outside the ordinary probe.
