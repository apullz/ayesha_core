# Ayesha Core - Mobile App

A chaotic multi-personality AI chatbot with three distinct character modes: Computer (logical), Otacon (panicky genius), and Win95 (nostalgic glitches).

## Building the APK

### Option 1: GitHub Actions (Recommended - Cloud Build)
1. Push this repo to GitHub
2. Go to **Actions** tab → Watch the workflow run
3. Download the APK from **Artifacts** or **Releases**

The workflow automatically builds on every push. Tag releases with `v1.0.0` format to create GitHub releases.

### Option 2: Local Build (WSL2 Ubuntu Required)
```bash
# In WSL2 Ubuntu:
sudo apt-get update
sudo apt-get install -y openjdk-11-jdk android-sdk python3-dev
pip install buildozer cython

# Then:
buildozer android debug
```

The APK will be in `bin/`.

### Option 3: Quick Test (Windows - Desktop Version)
```powershell
pip install kivy
python mobile_app.py
```

## Project Structure
- `mobile_app.py` - Main Kivy app with three personality modes
- `buildozer.spec` - Android build configuration
- `.github/workflows/build-apk.yml` - CI/CD for automated builds
- `manifest.json` - App metadata
- `Modelfile` - LLM personality definition

## Personality Modes
- **Computer**: Logical, analytical responses ("analysis complete. result: nominal, desu.")
- **Otacon**: Excitable genius ("senpai!! this is unbelievable!!")
- **Win95**: Retro glitchy responses ("error 0x800... not found in registry.")

Each message cycles through the modes automatically.

## Requirements
- Python 3.8+
- Kivy 2.3.1
- Buildozer (for APK builds)
- Android SDK/NDK (for local builds)
