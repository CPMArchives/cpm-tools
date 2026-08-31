# COMINFO

Future development is tracked in the suite-wide `../ROADMAP.md`.

COMINFO dev1 is a read-only static inspector for CP/M transient programs. It
reports a COM file's logical CP/M length and load range, direct references to
the public warm-boot and BDOS entries, other direct page-zero references, and
heuristic Z80 prefix-byte findings.

The complete suite user manual is `../docs/TOOLS.DOC`.

## Use

```text
COMINFO file.COM
COMINFO file.COM /V
COMINFO /HELP
COMINFO /INFO
COMINFO /VERSION
```

`/V` and `/VERBOSE` print the file offset of each finding. Static byte-pattern
analysis cannot prove that bytes are executable instructions, so COMINFO keeps
its definite address-pattern results separate from heuristic Z80 prefix bytes.

## Native CP/M build

Keep `COMINFO.MAC`, `BUILD.SUB`, `ZSM4.COM`, and `LINK.COM` on one drive, then
run `SUBMIT BUILD COMINFO`.

## License

GPL-2.0-or-later. See the repository `LICENSE`.
