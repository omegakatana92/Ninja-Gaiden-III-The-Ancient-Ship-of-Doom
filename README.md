# Ninja Gaiden III: The Ancient Ship of Doom — NES Native Recompilation

You are an expert in C/C++, NES 6502 assembly, static recompilation, CMake, SDL2, debugging, and Windows native development.

Your task is to develop a playable native Windows x64 recompilation of Ninja Gaiden III: The Ancient Ship of Doom (USA), using mstan's NESRecomp framework.

## Project Information

Framework repository:
https://github.com/mstan/nesrecomp

Installed NESRecomp CLI:
`C:\Users\omega\Documents\tools\nesrecomp-cli-windows-x86_64`

Source ROM:
`C:\Users\omega\Documents\tools\nesrecomp-cli-windows-x86_64\game\Ninja Gaiden III - The Ancient Ship of Doom (USA).nes`

Project directory:
`C:\Users\omega\Documents\tools\nesrecomp-cli-windows-x86_64\NinjaGaidenIIIRecomp`

Target executable:
`NinjaGaidenIIIRecomp.exe`

Release archive:
`NinjaGaidenIIIRecomp-Windows-x64.zip`

Target platform: Windows 10/11 x64.

## Phase 1 — Inspect the Environment

1. Inspect the installed NESRecomp CLI and verify its available commands.
2. Read the NESRecomp README, AGENTS.md, relevant runner documentation, and working game projects.
3. Verify that the ROM exists.
4. Inspect the ROM's iNES header, mapper, PRG-ROM/CHR-ROM sizes, and SHA-256 hash.
5. Confirm whether the framework supports the cartridge mapper.
6. Check for CMake, Visual Studio Build Tools/MSVC, SDL2, and other required dependencies.
7. Create a separate project directory without modifying the Ninja Gaiden I or II projects.

Do not assume unsupported features work.

## Phase 2 — Generate Recompiled Source

Run the following command from the NESRecomp CLI directory:

```powershell
.\nesrecomp.exe build `
  --rom "C:\Users\omega\Documents\tools\nesrecomp-cli-windows-x86_64\game\Ninja Gaiden III - The Ancient Ship of Doom (USA).nes" `
  --output "C:\Users\omega\Documents\tools\nesrecomp-cli-windows-x86_64\NinjaGaidenIIIRecomp"
```

Use the framework's default cycle-accurate backend.

Inspect the generated C files, game.toml, CMake configuration, and build scripts.

Resolve generation and compilation errors using actual diagnostics.

Do not confuse a successful static-library build with a playable executable.

## Phase 3 — Configure the Native Runner

Integrate the generated code with NESRecomp's native game runner and SDL2.

Validate:

- 6502 CPU execution and native dispatch
- Mapper-specific bank switching
- PPU rendering and sprite handling
- CHR-ROM/CHR-RAM behavior
- APU music and sound effects
- NMI and IRQ synchronization
- Frame timing
- Controller input
- Runtime initialization and shutdown

Use working NESRecomp game projects as implementation references.

Do not copy game-specific function addresses or configurations from Ninja Gaiden I or II without verification.

## Phase 4 — Ninja Gaiden III Gameplay Support

Preserve the original gameplay and mechanics, including:

- Ryu Hayabusa's movement and jumping
- Wall climbing and wall jumping
- Dragon Sword combat
- Sword-extension power-up
- Ninja special weapons and Ninpo
- Enemy AI and collision
- Moving platforms and environmental hazards
- Stage scrolling
- Boss encounters
- Cinematic storytelling sequences
- Health, lives, and continues
- Original music and sound effects

Pay particular attention to the USA version's gameplay difficulty and continue behavior.

Do not accidentally substitute Japanese-version game logic or balancing.

## Phase 5 — Build the Windows Executable

Create:

`NinjaGaidenIIIRecomp.exe`

Use CMake and a verified Windows x64 compiler toolchain.

Link the generated native game code with NESRecomp's runner and SDL2.

Ensure the executable can initialize the game and display its graphics correctly.

Do not stop after producing only a static library.

## Phase 6 — ROM-Selection Launcher

Create a functional Windows launcher titled:

Ninja Gaiden III — NES Recomp

Include:

- Select ROM
- Start Game
- Settings
- Exit
- `.nes` file browser
- ROM compatibility checking
- Clear error messages
- Optional last-used ROM location

The launcher must accept a user-supplied compatible Ninja Gaiden III ROM.

Validate the selected ROM against the supported USA release using verified cartridge metadata and hash.

Do not embed or distribute copyrighted ROM data.

## Phase 7 — Graphics, Audio, and Controls

Support keyboard and SDL-compatible gamepads.

Use NESRecomp's existing control configuration where possible.

Preserve the original game's timing, visual proportions, sprite behavior, audio, and music.

Provide fullscreen and windowed modes.

Avoid distorted aspect ratios and unnecessary graphical modifications.

## Phase 8 — Debugging and Testing

Test:

1. Game boot and title screen
2. Introductory cinematic
3. Act 1 gameplay
4. Sword combat and power-ups
5. Wall jumping and climbing
6. Enemy interactions
7. Scrolling stages
8. Environmental hazards
9. Boss encounters
10. Stage transitions
11. Later stages and final boss
12. Ending cinematic

Compare results against a reliable NES reference implementation.

Use smoke tests, dispatch-miss telemetry, fallback logs, and other supported framework debugging tools.

Investigate crashes, freezes, graphics corruption, missing audio, and timing problems.

Regenerate generated code when configuration changes rather than patching generated artifacts directly.

Report precisely which gameplay sections have been verified.

## Phase 9 — ROM-Free Release Packaging

After validating a playable executable, create:

`NinjaGaidenIIIRecomp-Windows-x64.zip`

Include:

- NinjaGaidenIIIRecomp.exe
- Required runtime DLLs
- Launcher resources
- Configuration files
- README.md
- License and attribution notices
- Instructions for selecting a legally obtained ROM

Exclude:

- Copyrighted ROM files
- Extracted proprietary game assets
- Temporary build files
- Developer-specific absolute paths

Audit generated source and compiled binaries for embedded ROM data before publication. A ROM-selection launcher alone does not establish that the package is ROM-free.

## Phase 10 — GitHub Preparation

Prepare a clean repository containing legally redistributable source code, project configuration, build scripts, launcher source, documentation, and required license notices.

Create a README covering project features, build instructions, compatible ROM versions, controls, limitations, and framework credits.

Do not upload the copyrighted ROM or generated proprietary game content.

Keep the source repository separate from the Windows binary release.

## Final Requirements

The intended final deliverable is a genuinely playable Windows x64 recompilation of Ninja Gaiden III with a ROM-selection launcher.

Work sequentially, diagnose actual errors, and validate gameplay rather than stopping at successful compilation.

Do not claim complete playability without sufficient testing.

When finished, report:

- Project directory
- ROM hash and mapper
- Framework version
- Build status
- Executable location
- Gameplay testing results
- Known issues
- Release ZIP location, if successfully created
