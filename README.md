# 🪐 TITAN 3D — Interactive Solid Geometry Studio
<p align="center">
  <strong>A high-performance, precision 3D computational geometry laboratory and educational studio engineered in 100% pure native Rust.</strong>
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License: MIT" /></a>
  <img src="https://img.shields.io/badge/Language-Rust%202024-orange.svg" alt="Rust 2024" />
  <img src="https://img.shields.io/badge/Graphics-wgpu%2030%20(DX12%2FVulkan)-indigo.svg" alt="wgpu 30" />
  <img src="https://img.shields.io/badge/GUI-egui%200.36-darkgreen.svg" alt="egui 0.36" />
  <img src="https://img.shields.io/badge/Status-BETA%20v1.0.0-gold.svg" alt="Beta v1.0.0" />
  <img src="https://img.shields.io/badge/Platform-Windows%20x64-blue.svg" alt="Windows x64" />
  <img src="https://img.shields.io/badge/Privacy-100%25%20Offline-brightgreen.svg" alt="100% Offline" />
</p>
---
> **“SEE IT. ROTATE IT. EXPLORE IT. UNDERSTAND IT.”**  
> *TITAN 3D bridges the gap between abstract solid geometry formulas and visceral spatial understanding.*
---
## 📖 Overview
**TITAN 3D** is an open-source, interactive desktop environment designed for learning, visualizing, and exploring spatial geometry (stereometry), 3D vector algebra, and mathematical surfaces.
Unlike browser-based viewers or heavy hybrid desktop wrappers (Electron, Chromium, CEF), TITAN 3D is built from the ground up in native **Rust** with direct GPU hardware acceleration via **DirectX 12 / Vulkan** using **wgpu 30** and **egui 0.36**. This guarantees near-instant startup, zero input lag, low RAM consumption, and a standalone executable size of only **~15 MB**.
The application is **100% offline**, contains no telemetry or data harvesting, and is licensed under the permissive **MIT License** — free forever for students, educators, and schools.
---
## ✨ Key Features & Educational Laboratories
### 🏛️ 1. 3D Geometric Solids Laboratory (22 Parametric Primitives)
- Real-time procedural tessellation and dynamic parameter resizing:
  - **Platonic Solids:** Regular Tetrahedron, Cube, Regular Octahedron, Regular Dodecahedron, Regular Icosahedron.
  - **Prisms & Pyramids:** Rectangular Cuboid, Triangular to Regular $N$-Gon Prisms, Pyramids, Frustums, Bipyramids.
  - **Solids of Revolution:** Cylinder, Cone, Sphere, Hemisphere, Torus, Ellipsoid.
- **3D Ray-Picking:** Point and click on solid faces directly in the viewport to inspect topological face metrics.
- **CAD-Style Free Movement:** Grab and reposition solids in 3D space with your mouse (hotkey `G`).
- **Exploded View:** Smoothly separate polygonal faces outward from the solid's centroid to inspect inner structures.
### 🧮 2. Closed-Form Analytical Mathematics
- Exact real-time calculation of Volume ($V$), Total Surface Area ($S$), Lateral Area ($S_{\text{lat}}$), and Base Area ($S_{\text{base}}$).
- **Step-by-Step Derivations:** Formatted mathematical formulas displaying exact values substituted into algebraic equations.
- **Euler’s Polyhedral Characteristic:** Real-time verification of $\chi = V - E + F = 2$.
- **Isoperimetric Quotient:** Measure solid sphericity and deviation from an optimal sphere.
- **Unit Systems:** Seamlessly toggle between Meters ($\text{m}$), Centimeters ($\text{cm}$), Millimeters ($\text{mm}$), and Inches ($\text{in}$).
### 🧭 3. 3D Spatial Vector Laboratory & Octants
- Manage vectors as first-class scene entities with dedicated inspectors and origin anchors.
- Interactive closed-form calculation & visualization:
  - Vector Addition ($\vec{u} + \vec{v}$) and Vector Subtraction ($\vec{u} - \vec{v}$).
  - Dot Product ($\vec{u} \cdot \vec{v}$) with angle $\theta$ readout (acute, right, or obtuse detection).
  - Cross Product ($\vec{u} \times \vec{v}$) with orthogonal normal vector and spanned parallelogram area.
  - Direction cosines, unit normalization ($\hat{v}$), and orthogonal projections.
- Full 3D Cartesian Coordinate System (**XYZ axes**) and spatial **8 Octants (I–VIII)** with sign conventions.
### ✂️ 4. Analytical 2D Planar Cross-Sections
- True polygon clipping of 3D meshes along an adjustable cutting plane computed on the CPU.
- Interactive 2D cross-section diagram plotter in the side inspector.
- Exact perimeter and cross-sectional area integration using the **Shoelace formula**.
- Real-time synchronization with GPU fragment-level clipping shaders.
### 📈 5. Mathematical Functions $z = f(x, y)$ (GeoGebra 3D Style)
- Built-in algebraic expression parser and real-time evaluator for 3D scalar fields.
- Procedural heightfield mesh generation with adaptive color palettes (Turbo, Viridis, Cool-to-Warm).
- 18 mathematical presets including wave interference, hyperbolic paraboloids (saddles), Gaussian bells, and relativistic functions.
### 🖥️ 6. Fullscreen Presentation Mode
- Toggle with `Alt + F1` or `Esc`.
- Designed for classroom projectors and interactive whiteboards: hides side navigation bars while presenting a clean 3D canvas with floating glassmorphism control docks.
### 💾 7. Export & CAD Interoperability
- Export 3D solids to clean **Wavefront OBJ** (`.obj`).
- Export ready-to-print 3D models to **Stereolithography STL** (`.stl`).
- Export full analytical calculation reports to **CSV** (`.csv`).
---
## ⌨️ Keyboard Shortcuts
| Shortcut | Action |
|---|---|
| `Alt + F1` / `Esc` | Toggle Fullscreen Presentation Mode |
| `Ctrl + Z` / `Ctrl + Y` | Undo / Redo last action |
| `G` / `Alt + Drag` | Free CAD translate/move selected solid |
| `Ctrl + Mouse Wheel` | Smooth camera zoom in/out |
| `Left Mouse Button` | Orbit / Rotate scene |
| `Right Mouse / Middle Mouse` | Pan camera |
---
## 📦 Download & Installation (Windows x64)
### 1. Portable Version (Recommended for quick testing)
1. Download `TITAN3D-v1.0.0-Windows-x64.zip` from the latest [Releases](../../releases).
2. Extract the archive anywhere (or onto a USB drive).
3. Run `titan3d.exe`. No installation or administrator rights required!
### 2. User-Level Windows Installation
- Inside the extracted folder, right-click `install.ps1` and select *Run with PowerShell*.
- Installs the app into `%LOCALAPPDATA%\Programs\TITAN3D`, adds Start Menu and Desktop shortcuts with high-resolution icons, and registers the app in *Windows Settings > Installed Apps* for clean uninstallation.
---
## 🛠️ Building from Source
To compile TITAN 3D from source, ensure you have [Rust & Cargo](https://rustup.rs/) (version 1.85+) installed:
```bash
# 1. Clone the repository
git clone https://github.com/your-username/titan3d.git
cd titan3d
# 2. Run in development mode
cargo run
# 3. Build optimized native release binary for Windows
cargo build --release

  

The compiled release binary will be available at target/release/titan3d.exe.


🧪 Testing and Code Quality

The codebase enforces strict quality checks and safety invariants:

bash
# Run unit and integration test suite
cargo test
# Run strict Clippy linter (0 warnings enforced)
cargo clippy --all-targets --all-features -- -D warnings
# Verify formatting
cargo fmt --all -- --check

  
👥 Authors & Acknowledgments

Karel Janoušek and Matyáš Řehoř


This project is an ongoing student/educational initiative aimed at modernizing geometry education in schools. It is currently in BETA testing. Suggestions, bug reports, and pull requests are warmly welcome!


📄 License

This project is licensed under the MIT License. You are free to use, modify, distribute, and integrate it into educational environments without restriction.
