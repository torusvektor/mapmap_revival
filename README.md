# MapMap Revival (Android)

> **Professional Projection Mapping & Spatial Augmented Reality Studio for Android**
> Ported and rewritten in modern Kotlin & Jetpack Compose from the original C++/Qt MapMap project.

MapMap is open-source projection mapping and video mapping software. Projection mapping is used to turn objects, often irregularly shaped, into a display surface for video projection.

## Features Ported & Implemented

- **Surface Warping & Shapes:**
  - **Quads**: 4-point homography and projective perspective deformation.
  - **Triangles**: 3-point affine projection for triangular surfaces and architectural facets.
  - **Meshes**: NxM control vertex grids (from 2x2 up to 8x8) for non-linear warping onto cylinders, spheres, and irregular 3D objects using hardware-accelerated bitmap mesh rendering.
  - **Ellipses / Circles**: Circular mapping shapes with center and radius controls.

- **Paints & Media Sources:**
  - **Video Synthesizers**: Real-time generative video loops (Cyber Tunnel, Waveform Spectrum, Kaleidoscope, Strobe Beats) with play/pause/rewind controls.
  - **Test Signals & Calibration**: SMPTE/PAL color bars, 10% alignment crosshairs, concentric circle calibration, checkerboard grid, and classic broadcast test cards.
  - **Image Paints**: Bundled MapMap branding graphics and custom bitmap assets.
  - **Color Paints**: Solid RGBA color swatches and black mask barriers.
  - **Live Camera Feed**: Support for mapping live camera video streams onto projection geometries.

- **Projection Studio & Dual Viewport:**
  - **Output Viewport**: Multi-layer composited warping with interactive node dragging, boundary wireframes, and control handles.
  - **Input Viewport**: Texture coordinate cropping and sub-region selection.
  - **Touch Magnifier Loupe**: Precision crosshair floating above the user's touch point to prevent finger occlusion during calibration.
  - **Precision D-Pad Nudge**: 1px, 5px, and 20px 4-way arrow controls for sub-pixel alignment in dark projection environments.
  - **Sticky Vertex Snapping**: Automatic magnetic snapping to neighboring vertices and alignment grid lines.

- **Layer Management:**
  - Layer stack ordering (move up / down).
  - Solo mode ('S') to isolate individual layers during calibration.
  - Visibility toggles (eye icon) and lock toggles to prevent accidental edits.
  - Real-time layer opacity blending sliders (0% - 100%).
  - Layer duplication and deletion.

- **Open Sound Control (OSC) Remote:**
  - UDP port 12345 listener and dispatcher.
  - Commands: `/mapmap/play`, `/mapmap/pause`, `/mapmap/rewind`, `/mapmap/blackout <0|1>`, `/mapmap/testsignal <0|1>`, `/mapmap/mapping/opacity <id> <val>`, `/mapmap/mapping/solo <id> <val>`, `/mapmap/mapping/visible <id> <val>`, `/mapmap/mapping/locked <id> <val>`.
  - Built-in interactive OSC testing console and live activity event monitor.

- **Project Management & Presets:**
  - Save and load project shows.
  - Pre-configured mapping presets:
    - *Architectural Facade* (pediment triangle, central mesh, column quads)
    - *3D Isometric Cube* (3-face isometric cube optical illusion)
    - *Curved Column Mesh* (5x5 grid calibrated for cylindrical surfaces)
    - *Multi-Surface Stage* (central diamond quad flanked by stage wings)
  - JSON project import / export to clipboard.

- **Projector Presentation Mode:**
  - Fullscreen borderless output view for direct projection to external beamers and secondary displays via HDMI, USB-C, or Cast.

## Technology Stack

- **Framework**: Android SDK 36, Kotlin 2.2, Jetpack Compose, Material 3
- **Rendering**: Hardware-accelerated Canvas with projective homography, `drawBitmapMesh`, and custom shader mathematics
- **Architecture**: MVVM with Kotlin Coroutines & StateFlow

## License

GPL v3 (inherited from MapMap project)
