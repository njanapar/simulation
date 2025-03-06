# CARLA Simulator Installation Guide

## Overview
This guide provides instructions for installing and setting up the CARLA simulator, a high-fidelity open-source autonomous driving simulator. The setup includes the installation of CARLA with Unreal Engine and setting up the Python API to control and interact with the simulation.

---

## System Requirements

### Hardware Requirements
- **Operating System:** 64-bit Windows
- **Disk Space:** 200 GB SSD (32 GB for CARLA + 133 GB for Unreal Engine and related installations)
- **Graphics Card:** 
  - Minimum 6 GB dedicated GPU (8 GB recommended).
  - Ensure you have a high-end dedicated GPU for machine learning or the simulator may crash.
- **Network:** Good internet connection required with ports 2000 and 2001 open.
- **TCP Ports:** Ensure ports 2000 and 2001 are open and not blocked by firewalls.

### Software Requirements
- **CMake** (version 3.15+)
- **Git** (version control system)
- **Make** (version 3.81+)
- **7Zip** (for extracting large asset files)
- **Python 3.x64** (ensure you have the x64 version to avoid conflicts with the x32 version)
- **Visual Studio 2019** (with the following components):
  - Windows 8.1 SDK
  - x64 Visual C++ Toolset
  - .NET Framework 4.6.2
- **Unreal Engine** (Modified version of UE4.26)

---

## Installation Steps

### Step 1: Install Dependencies

1. **Install CMake** (version 3.15 or higher) from [CMake](https://cmake.org/download/).
2. **Install Git** from [Git](https://git-scm.com/download/win).
3. **Install 7Zip** from [7Zip](https://www.7-zip.org/download.html).
4. **Install Python 3.x64** from [Python](https://www.python.org/downloads/). Make sure it’s the x64 version.
   - Run `pip3 install --upgrade pip` to ensure you have the latest pip.
   - Install required Python packages:
     ```bash
     pip3 install --user setuptools
     pip3 install --user wheel
     ```

5. **Install Visual Studio 2019** (or 2022) from [Visual Studio](https://visualstudio.microsoft.com/downloads/). During installation, select:
   - Windows 8.1 SDK
   - x64 Visual C++ Toolset
   - .NET Framework 4.6.2

### Step 2: Install Unreal Engine

1. **Clone the modified Unreal Engine** for CARLA from GitHub:
   ```bash
   git clone --depth 1 -b carla https://github.com/CarlaUnreal/UnrealEngine.git .

2.Run setup scripts to configure Unreal Engine:
   ```bash
   Setup.bat
GenerateProjectFiles.bat



