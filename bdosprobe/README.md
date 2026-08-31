# BDOSPROBE

BDOSPROBE is a CP/M-resident harness for observing documented BDOS calls and
recording their complete returned register state. Its CP/M command and files
are named `BDOSPRB` to fit the CP/M 8.3 filename limit.

Development release `0.1.0-dev2` adds observational console, disk-state, and
memory-address groups to the function 12 version probe. Every call reports A,
BC, DE, HL, flags, and SP, but interprets only documented results.

```text
BDOSPRB
BDOSPRB /CPM
BDOSPRB /DISK
BDOSPRB /MEM
BDOSPRB /CONSOLE
BDOSPRB /H[ELP]
BDOSPRB /INFO
BDOSPRB /VER[SION]
```

Run `./build.sh` to assemble with ZSM4 and Digital Research LINK and exercise
the result under z80pack in both Z80 and Intel 8080 modes. Dev2 has also been
tested on Montezuma Micro CP/M 2.2 in the TRS-80 emulator.

The probe-selection rules and future sequence are in
[`docs/BDOSPROBE-DESIGN.md`](../docs/BDOSPROBE-DESIGN.md).
