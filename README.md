# Resonance-A-Plague-Tale-Legacy-AMD-Polaris-Fix
AMD Radeon RX 400/500 (Polaris) compatibility fix for Resonance: A Plague Tale Legacy. Enables gameplay and resolves black environments, missing sky, water, and other rendering issues.

<div align="center">

# Resonance: A Plague Tale Legacy
## AMD Radeon RX 400 / RX 500 Compatibility Fix

**A community-developed DirectX 12 compatibility fix for AMD Polaris GPUs.**

![GPU](https://img.shields.io/badge/GPU-AMD_RX_400_%2F_500-ED1C24?style=for-the-badge&logo=amd&logoColor=white)
![API](https://img.shields.io/badge/API-DirectX_12_%2F_Vulkan-0078D6?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Status](https://img.shields.io/badge/Status-Working-28A745?style=for-the-badge)

**Successfully developed and tested on the AMD Radeon RX 580 8GB.**

[Download Latest Release](../../releases/latest) ·
[Report an Issue](../../issues) ·
[View All Releases](../../releases)

</div>

---

## Overview

This project provides a custom compatibility fix designed to run **Resonance: A Plague Tale Legacy** on AMD Radeon RX 400 and RX 500 series graphics cards.

The fix addresses DirectX 12 compatibility limitations, Vulkan graphics pipeline failures, and shader compilation issues affecting AMD Polaris GPUs.

During development, the initial implementation successfully launched the game and enabled gameplay. However, several significant rendering problems remained:

- Large portions of the game world appeared completely black.
- The sky and water were missing.
- Certain world objects and visual effects failed to render.
- Puzzle symbols, guidebook text, and lighting elements were invisible.

After extensive debugging, shader analysis, SPIR-V experimentation, and graphics pipeline compatibility improvements, these rendering issues were successfully resolved on the RX 580.

**The game is now running with the entire game world rendering correctly, including the sky, water, lighting, and previously missing visual elements.**

---

## Features

- Enables gameplay on AMD Polaris GPUs.
- Addresses DirectX 12 compatibility limitations.
- Resolves major Vulkan graphics pipeline creation failures.
- Fixes black environments and missing visual elements.
- Restores sky and water rendering.
- Restores missing puzzle symbols and guidebook text.
- Restores previously missing lighting effects.
- Includes custom shader substitutions and compatibility improvements.
- Reduces the stuttering encountered during initial development.

---

## Rendering Fixes

The initial compatibility implementation allowed the game to launch but exposed several graphics rendering issues.

The following problems have been resolved during development and verified on the RX 580:

| Rendering Issue | Status |
|:---|:---:|
| Game startup failure | Fixed |
| Black environments | Fixed |
| Missing sky | Fixed |
| Invisible water | Fixed |
| Missing world elements | Fixed |
| Missing puzzle symbols | Fixed |
| Missing guidebook text | Fixed |
| Missing puzzle lighting | Fixed |
| Graphics pipeline failures affecting rendering | Addressed |
| Initial gameplay stuttering | Improved |

**All previously missing world elements now render correctly on the tested hardware.**

---

## Technical Background

The compatibility solution was developed through extensive investigation of the game's DirectX 12 rendering pipeline and its interaction with AMD Polaris hardware.

The development process involved:

- DirectX 12 compatibility investigation.
- Vulkan graphics pipeline debugging.
- VKD3D-Proton experimentation and customization.
- Shader analysis and SPIR-V investigation.
- Graphics pipeline state debugging.
- AMD Polaris driver compatibility workarounds.
- Targeted shader substitution.
- Rendering recovery and performance improvements.

### The Rendering Problem

The initial fix successfully enabled the game to launch and enter gameplay, but numerous graphics pipelines failed during shader compilation.

Investigation identified specific fragment shaders that the AMD Polaris Vulkan driver could not compile successfully.

These failures prevented several materials and visual effects from rendering correctly, resulting in black environments and missing world elements.

### The Solution

The compatibility fix combines DirectX 12 compatibility improvements, Vulkan translation components, graphics pipeline workarounds, and targeted shader replacements.

After multiple development iterations, the problematic rendering paths were addressed, allowing the previously missing visual elements to appear correctly.

---

## GPU Compatibility

This project targets the **AMD Radeon RX 400 and RX 500 series**, particularly GPUs based on the Polaris architecture.

| GPU | Compatibility |
|:---|:---|
| AMD Radeon RX 580 8GB | Successfully tested |
| AMD Radeon RX 570 | Targeted — additional testing welcome |
| AMD Radeon RX 560 | Targeted — additional testing welcome |
| AMD Radeon RX 550 | Not verified |
| AMD Radeon RX 480 | Targeted — additional testing welcome |
| AMD Radeon RX 470 | Targeted — additional testing welcome |
| AMD Radeon RX 460 | Targeted — additional testing welcome |
| Other AMD GPUs | Not verified |
| NVIDIA GPUs | Not verified |
| Intel GPUs | Not verified |

> [!NOTE]
> The RX 580 8GB is the primary development and testing GPU.
>
> Although the fix targets the RX 400 and RX 500 series, compatibility and performance may vary between individual GPU models and driver versions.

---

## Tested Hardware

The fix was developed and tested using the following configuration:

| Component | Specification |
|:---|:---|
| GPU | AMD Radeon RX 580 8GB |
| CPU | Intel Core i5-12400F |
| RAM | 16 GB |
| Operating System | Windows 11 |
| Graphics API | DirectX 12 / Vulkan compatibility layer |

---

## Installation

### Step 1 — Download

Download the latest version of the fix from the official GitHub [Releases](../../releases) page.

Extract the downloaded archive using 7-Zip, WinRAR, or another compatible archive manager.

### Step 2 — Locate Your Game Directory

Open the installation directory of **Resonance: A Plague Tale Legacy**.

Locate the folder containing:

`Resonance.exe`

### Step 3 — Install the Fix

Copy the following files and folders from the downloaded archive into the directory containing `Resonance.exe`:

```text
Resonance A Plague Tale Legacy/
│
├── shader-substitute/
│
├── vkd3d/
│
├── d3d12.dll
├── d3d12_resonance.dll
├── dx12bridge.ini
├── dxgi.dll
│
└── Resonance.exe
```

> [!IMPORTANT]
> `Resonance.exe` is part of your existing game installation and is **not included in the compatibility fix**.
>
> Keep the original folder structure intact. Do not move or delete files inside `shader-substitute` or `vkd3d`.
>
> Back up any existing files before replacing them.

### Step 4 — Launch the Game

After copying the files, launch the game normally using `Resonance.exe`.

The compatibility components should load automatically when the game starts.

---

## Included Components

| Component | Purpose |
|:---|:---|
| `d3d12.dll` | Custom DirectX 12 compatibility proxy |
| `d3d12_resonance.dll` | Additional DirectX 12 compatibility component |
| `dxgi.dll` | DXGI compatibility component |
| `dx12bridge.ini` | Compatibility and rendering configuration |
| `vkd3d/` | DirectX 12-to-Vulkan translation components |
| `shader-substitute/` | Targeted shader replacements |

> [!WARNING]
> All included components are part of the compatibility package.
>
> Removing or modifying individual components may cause startup failures, missing graphics, or other rendering problems.

---

## Development Status

**Current Status: Working**

The game has successfully launched, entered gameplay, and rendered the complete game world on the AMD Radeon RX 580 8GB.

The major rendering issues encountered during development have been resolved.

Future updates may include additional performance optimizations, compatibility improvements, and fixes based on community feedback.

---

## Known Limitations

- The fix has primarily been developed and tested on the RX 580 8GB.
- Compatibility with every RX 400 and RX 500 model has not been individually verified.
- Performance may vary depending on GPU model, VRAM, graphics settings, and driver version.
- Some driver versions may behave differently.
- Compatibility with other GPU architectures is not guaranteed.

---

## Bug Reports

If you encounter crashes, rendering problems, or other compatibility issues, please open a [GitHub Issue](../../issues).

When reporting a problem, include:

1. GPU model and VRAM.
2. AMD driver version.
3. Windows version.
4. Game version.
5. Fix version.
6. Steps to reproduce the problem.
7. Screenshots or relevant logs, if available.

Please check existing issues before submitting a new report.

Detailed reports are particularly helpful for investigating compatibility differences between RX 400 and RX 500 GPUs.

---

## Disclaimer

This is an independent, community-developed compatibility project.

It is not affiliated with, endorsed by, or officially supported by the game's developers, publisher, AMD, or the VKD3D-Proton development team.

All game names, trademarks, and related assets belong to their respective owners.

This project does not include the game itself. A legitimate copy of the game is required.

---

<div align="center">

### Developed by Ibrahim Khaled

**Bringing modern games to AMD Polaris hardware.**

If this project helped you, consider giving it a ⭐ on GitHub!

</div>
