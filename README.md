# Dodge

An endless-scroller mobile game made with Unity where the player controls a ball and dodges obstacles. This repository contains the Unity project files, scenes, and C# scripts for a simple, mobile-oriented prototype (MainMenu + Game scenes). It uses the Universal Render Pipeline (URP) and includes several third-party assets (LeanTween, TextMesh Pro, Stylized Water, and others).

---

## Table of Contents

| Section | Description |
|---|---|
| [What this project is](#what-this-project-is) | Short summary and purpose |
| [Screenshots (placeholders)](#screenshots-placeholders) | Image placeholders to replace with real screenshots |
| [Features](#features) | Core gameplay features |
| [Project status](#project-status) | Current development status |
| [Recommended environment](#recommended-environment) | Unity version & tooling notes |
| [Quick start (open & run)](#quick-start-open--run) | How to open and play in the Editor |
| [Building for Android](#building-for-android) | Brief Android build steps |
| [Building for iOS](#building-for-ios) | Brief iOS build steps |
| [Project structure (top-level, annotated)](#project-structure-top-level-annotated) | Top-level folders and roles |
| [Script & gameplay breakdown (key files)](#script--gameplay-breakdown-key-files) | Roles of main C# scripts |
| [Assets & 3rd-party packages included](#assets--3rd-party-packages-included) | Bundled asset packages |
| [Known issues & conflict cleanup](#known-issues--conflict-cleanup) | Merge artifacts and fixes |
| [Development workflow & contribution guide](#development-workflow--contribution-guide) | How to contribute & branch workflow |
| [Testing, debugging, and profiling](#testing-debugging-and-profiling) | Debugging and performance tips |
| [Art & audio pipeline](#art--audio-pipeline) | Asset import / audio notes |
| [Suggested enhancements & roadmap](#suggested-enhancements--roadmap) | Ideas & next steps |
| [FAQ / Troubleshooting](#faq--troubleshooting) | Common issues & fixes |
| [License & credits](#license--credits) | Licensing and attribution |
| [How you can help](#how-you-can-help) | Ways to improve the project |
| [Change log / versioning](#change-log--versioning) | Changelog template |

---

## What this project is
Dodge is a minimal endless-runner-style game implemented in Unity where a ball automatically moves forward and the player moves it horizontally to avoid obstacles. It’s designed as a prototype or learning project for mobile gameplay mechanics, simple object spawning, and UI-driven game states.

---

## Screenshots
(Replace these placeholders with actual screenshots in `docs/screenshots/` and link them here.)

- Main Menu
- Game (in-play)
- Game Over / High Score

---

## Features
- Automatic forward movement with player-controlled horizontal movement (keyboard + touch input).
- Procedural obstacle spawning (configurable spawn frequency and variety).
- Game over flow with UI (panel + animation) and return to main menu.
- Simple scoring system and high score display.
- Viewport helper that adapts to different aspect ratios for consistent gameplay on mobile.
- Uses URP assets and third-party visual/audio assets for easier visuals and UI.

---

## Project status
- Prototype: core mechanics implemented (movement, spawning, game-over).
- Scenes: MainMenu and Game are present and playable in the editor.
- Not production-ready: contains conflict markers and may lack explicit Package/ProjectSettings versions. Some assets (URP & packages) may require reimport or update to your local Unity Editor version.

---

## Recommended environment
- Unity Editor: Use a recent LTS release. The project was created with a URP-enabled setup — Unity 2020.3 LTS or newer is recommended (2021.3 / 2022.3 LTS are commonly used). If you see package version or serialization warnings, try opening with an LTS release close to the project's creation date.
- Modules: If building for Android/iOS, install Android Build Support / iOS Build Support and associated SDKs through Unity Hub.
- Packages: TextMesh Pro (usually included by default in modern Unity), Universal Render Pipeline (URP) via Package Manager. LeanTween and other assets are included in the repo, but you may need to reimport them.

---

## Quick start — open and run in the Editor
1. Clone the repository:
   git clone https://github.com/OG-Enoch/Dodge.git
2. Open Unity Hub, click "Add", and select the repository folder (the folder containing the `Assets` and `ProjectSettings`, or the root repo if they are present).
3. Open the project in Unity (select a compatible Editor version if prompted).
4. Open the scene `Scenes/MainMenu.unity` (or `Scenes/Game.unity`).
5. Press Play in the Unity Editor to run.

Notes:
- If the project prompts to upgrade packages or convert materials for URP, allow Unity to make safe upgrades or import URP if you intend to use URP rendering.
- If you see missing script references in the Inspector, re-import the corresponding asset or confirm the compile errors are resolved first.

---

## Building for Android (brief)
1. Ensure Android Build Support + SDK & NDK are installed via Unity Hub.
2. File → Build Settings → Select "Android", click "Switch Platform".
3. Optionally, set your package name (Player Settings → Other Settings → Package Name) and set a keystore for release builds.
4. Configure resolution / Graphics (make sure URP & shaders are compatible with target device).
5. Click "Build" or "Build and Run".

Tips:
- Test frequently in the Editor before building.
- Use Development Build + Autoconnect Profiler for debug builds to profile on device.

Building for iOS:
- Install iOS Build Support.
- Switch platform to iOS in Build Settings.
- Build will produce an Xcode project — open in Xcode and sign/provision for device.

---

## Project structure (top-level, annotated)
```text
Animation/                   Unity animation assets (clips, animator controllers)
AnyUI/                       UI assets or imported UI packages
LeanTween/                   LeanTween tweening library (third-party)
Materials/                   Scene and object material assets
Music/                       Audio files used in the game
Prefabs/                     Prefabs for player, obstacles, ground, UI elements
Plugins/                     Native plugins or vendor code
Samples/                     Sample assets provided by imported packages
Scenes/                      Unity scenes: MainMenu.unity, Game.unity
Script/                      C# gameplay scripts (ball, obstacles, UI, manager)
Stylized Water For URP/      URP water shader assets
TextMesh Pro/                TextMesh Pro assets (UI text)
UI Elements/                 UI prefabs/assets
_Heathen Engineering/        Third-party asset content
UniversalRenderPipelineAsset.* URP asset settings and renderer
README.md                    This document (recommended)
New Unity Project.sln        Visual Studio solution
