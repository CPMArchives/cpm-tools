# CP/M Tools

Small system-information and diagnostic utilities for CP/M 2.2-compatible
systems.

Each utility is maintained in its own directory with its source, build script,
documentation, tests, and current CP/M executable. The tools are deliberately
kept independent so that users can build or copy only the programs they need.

## Available tools

### [SYSINFO](sysinfo/)

A read-only system-information utility. SYSINFO reports documented,
application-visible CP/M state, including memory vectors, disk parameters,
drive allocation, free space, the standard BIOS jump table, and structural
health checks.

The current development release is
[`SYSINFO 1.0.0-dev7`](https://github.com/CPMArchives/cpm-tools/releases/tag/v1.0.0-dev7).

## Planned tools

The collection is intended to grow with focused utilities such as MEMINFO and
DISKINFO. Their directories will be added when their behavior and interfaces
are ready to be maintained publicly.

## Building

Enter a tool's directory and run its build script. For SYSINFO:

```text
cd sysinfo
./build.sh
```

See the README in each tool directory for its requirements and command-line
interface.

## License

Unless otherwise noted, original source code and documentation in this
repository are licensed under the GNU General Public License, version 2 or,
at your option, any later version (`GPL-2.0-or-later`). See `LICENSE`.
