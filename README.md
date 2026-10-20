# Ninja-Gaiden-III---The-Ancient-Ship-of-Doom-USA NESRecomp output

This folder contains cycle backend C source generated from `Ninja Gaiden III - The Ancient Ship of Doom (USA).nes`.

## Build the generated source

Windows PowerShell:

```powershell
.\build.ps1
```

macOS or Linux:

```sh
./build.sh
```

The build creates the `nesrecomp_game` static library. This confirms that the
generated source compiles; it is not a complete playable port by itself.

To make a playable port, add game-specific configuration and integrate with
the corresponding NESRecomp runner. Cycle projects use
`runner/cyc/project.cmake` and `nesrecomp_add_cycle_game`; see
https://github.com/mstan/nesrecomp/blob/master/runner/cyc/PROJECTS.md.
Existing game repositories are also useful starting points.
