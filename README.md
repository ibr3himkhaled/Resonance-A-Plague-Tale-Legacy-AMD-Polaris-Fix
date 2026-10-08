<div align="center">

# Resonance: A Plague Tale Legacy
## AMD Radeon RX 500 Compatibility Fix

**A community-developed DirectX 12 compatibility fix for AMD Polaris GPUs.**

![GPU](https://img.shields.io/badge/GPU-AMD_RX_500-ED1C24?style=for-the-badge&logo=amd&logoColor=white)
![API](https://img.shields.io/badge/API-DirectX_12_%2F_Vulkan-0078D6?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Status](https://img.shields.io/badge/Status-Working-28A745?style=for-the-badge)

**Successfully developed and tested on the AMD Radeon RX 580 8GB.**

[Download from Mediafire](https://stly.link/resonancepolaris) ·
[Report an Issue](../../issues)

---

## ❤️ Support My Work

Hi, I'm **Ibrahim Khaled**, an independent developer creating compatibility fixes that help older AMD graphics cards run modern games.

Developing these fixes involves extensive reverse engineering, shader analysis, debugging, and testing.

If this project helped you enjoy a game that wouldn't otherwise run on your hardware, please consider supporting the development of future compatibility fixes.

### ☕ Support Development

[![GitHub Sponsors](https://img.shields.io/badge/GitHub-Sponsor-EA4AAA?style=for-the-badge&logo=githubsponsors&logoColor=white)](https://github.com/sponsors/ibr3himkhaled)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support_Me-FF5E5B?style=for-the-badge&logo=kofi&logoColor=white)](https://ko-fi.com/ibr3himkhaled)

[![Buy Me a Coffee](https://img.shields.io/badge/Buy_Me_a_Coffee-Support-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/ibr3himkhap)
[![PayPal](https://img.shields.io/badge/PayPal-Donate-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/IbrahimKhaled)

**All donations are completely optional. My compatibility fixes remain free and publicly available.**

Your support helps me continue researching, developing, and improving compatibility solutions for older GPUs.

**Thank you for supporting independent development!**

</div>

---

## Overview

This project provides a custom compatibility fix designed to run **Resonance: A Plague Tale Legacy** on AMD Radeon RX 500 series graphics cards, particularly GPUs based on the Polaris architecture.

The fix addresses DirectX 12 compatibility limitations, Vulkan graphics pipeline failures, and shader compilation issues affecting AMD Polaris GPUs.

During development, the initial implementation successfully launched the game and enabled gameplay. However, several significant rendering problems remained:

- Large portions of the game world appeared completely black.
- The sky and water were missing.
- Certain world objects and visual effects failed to render.
- Puzzle symbols, guidebook text, and lighting elements were invisible.

After extensive debugging, shader analysis, SPIR-V experimentation, and graphics pipeline compatibility improvements, these rendering issues were successfully resolved on the RX 580.

**The game is now running with the entire game world rendering correctly, including the sky, water, lighting, and previously missing visual elements.**

**Full Game Playability:** The complete campaign is playable from start to finish on the tested AMD Radeon RX 580 8GB, all the way through to the ending.

---

## ⚠️ Important VRAM Compatibility Notice

**The game requires at least 6GB of VRAM.**

Graphics cards with only **4GB of VRAM cannot run the game successfully with this fix**. On these configurations, the game encounters a black screen during startup.

This limitation is related to the game's VRAM requirements and engine behavior. The compatibility fix addresses DirectX 12 compatibility and rendering issues, but it cannot overcome the game's minimum VRAM requirement on 4GB graphics cards.

**Recommended configuration: An AMD Radeon RX 500 series GPU with 8GB of VRAM.**

The RX 580 8GB is the confirmed test configuration. Other GPUs with 8GB of VRAM may vary depending on their hardware and driver compatibility.

---

## Features

- Enables gameplay on compatible AMD Polaris GPUs.
- Supports playing the complete campaign from start to finish on the tested RX 580 8GB.
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

This project targets compatible **AMD Radeon RX 500 series GPUs**, particularly GPUs based on the Polaris architecture.

| GPU | Compatibility |
|:---|:---|
| AMD Radeon RX 580 8GB | Successfully tested |
| AMD Radeon RX 570 4GB | Not working — black screen |
| AMD Radeon RX 560 4GB | Not working — black screen |
| AMD Radeon RX 550 4GB | Not working — black screen |
| Other AMD Radeon RX 500 GPUs with 4GB VRAM | Not working — black screen |
| Other AMD Radeon RX 500 GPUs with 8GB VRAM | Worked |
| Other AMD GPUs | Not verified |
| NVIDIA GPUs | Not verified |
| Intel GPUs | Not verified |

> [!NOTE]
> The RX 580 8GB is the primary development and testing GPU.
>
> **GPUs with only 4GB of VRAM encounter a black screen and are not supported by this fix.** The game requires at least 6GB of VRAM, and the compatibility fix cannot bypass this limitation.
>
> The RX 580 8GB is the confirmed test configuration. Compatibility and performance on other GPUs may vary depending on the GPU model, driver version, and system configuration.

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

Download the latest version of the fix from one of the download links at the top of this README.

- **[Download Mirror — MediaFire](https://stly.link/resonancepolaris)**

Extract the downloaded archive using 7-Zip, WinRAR, or another compatible archive manager.

### Step 2 — Locate Your Game Directory

Open the installation directory of **Resonance: A Plague Tale Legacy**.

Locate the folder containing:

`Resonance.exe`

### Step 3 — Install the Fix

Copy the included files and folders from the downloaded archive into the directory containing `Resonance.exe`.

The game directory should contain the required compatibility files, including:

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
