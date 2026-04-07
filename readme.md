# Liquid Optics — Pebble & Void 🌑✨

**Vol. 02 of the UX/UI Archive**

A frontend study of soft geometry, heavy spring physics, and real-time refractive optics. This project explores a "dark space" aesthetic using deep contrast, glowing ambient orbs, and a custom liquid-glass engine built entirely in Vanilla Web Technologies.

## 🌟 Overview

"Pebble & Void" attempts to bridge the gap between digital interfaces and physical objects. By utilizing custom mathematical surface curves (convex squircles), robust spring physics, and SVG displacement maps, the UI components behave like dense blocks of liquid glass that refract the light and objects behind them.

**Zero external dependencies.** No React, no Three.js, no external physics libraries. Just pure HTML, CSS, and mathematical JavaScript.

## ✨ Features

* **Custom Physics Engine:** Built-in 1D/2D `Spring` class handling velocity, stiffness, and damping for ultra-smooth, organic interactions.
* **Real-time Glass Refraction:** Generates dynamic SVG `<feDisplacementMap>` layers mathematically, simulating the exact refractive index and thickness of physical glass.
* **Dynamic Specular Highlights:** Canvas-based lighting engine that computes specular light distribution based on the simulated 3D curve of the glass elements.
* **Backdrop-Filter Fallback System:** Uses native CSS `-webkit-backdrop-filter` where supported, and gracefully falls back to cloned-DOM SVG masking for browsers that don't support complex backdrop filters.
* **Squircle Mathematics:** Replaces standard border-radii with continuous convex curves to eliminate harsh light-catching corners.

## 🧩 Component Library (The Exhibits)

The exhibition features 15 distinct, interactive liquid components:

1. **Precision Lens:** A draggable magnifying glass that bends visual space over an image.
2. **Fluid Slider:** A horizontal squishy pill that reacts dynamically to drag velocity.
3. **Tactile Switch:** A spring-loaded toggle that sinks into the canvas upon interaction.
4. **Drag Dock:** A kinematic, sliding MacOS-style dock with snapping bubbles.
5. **Cursor Optics:** A custom liquid cursor that tracks mouse movement and morphs over targets.
6. **Liquid Button:** A tactile button where hover/click dynamics push and stretch the glass mesh.
7. **Segment Control:** A pill indicator that rapidly stretches and snaps between tab items.
8. **Rotation Dial:** A circular knob where drag interactions spin the underlying glass mesh.
9. **Fluid Input:** A text field that triggers micro-vibrations across the glass bounding box while typing.
10. **Squish Volume:** A vertical volume slider featuring Y-axis bounds scaling during over-drag.
11. **Layered FAB:** A Floating Action Button where elements physically push each other during expansion.
12. **Magnetic Stepper:** A +/- counter with a kinematic mass that shifts heavily upon tap.
13. **Liquid Checkbox:** A block of glass that squishes deeply into the canvas to reveal a glowing mark.
14. **Fluid Progress Bar:** A liquid expansion bar that bulges the container as it loads.
15. **Glass Tooltip:** A hover discovery element that springs organically into open space.

## 🚀 Usage & Installation

Because the project is entirely vanilla, there is no build step required.

1. Clone or download the repository.
2. Open `index.html` in any modern web browser.
3. Interact with the components using a mouse or touch device.

```bash
# Clone the repository
git clone https://github.com/yourusername/liquid-optics.git

# Open directly in browser
open index.html
🛠 Technical Details
The Refraction Engine
The core of the visual style relies on generating a 2D displacement map using the calculateDisplacementMap2D function. This function uses a mathematical equation:
f(x) = (1 - (1 - x)^4)^(1/4)
to calculate the depth of the glass at any given pixel, applying Snell's law to map how much the pixels behind it should be displaced.
The Physics Engine
Every interaction (hover, click, drag) is piped through a custom Spring class:
code
JavaScript
class Spring { 
    constructor(val, stiffness = 300, damping = 20) { ... }
    update(dt) { ... }
}
Instead of CSS transitions, the requestAnimationFrame loop calculates the exact physical velocity and tension of the UI element, resulting in heavy, gelatinous movements.
🌐 Browser Compatibility
For the best experience, a Chromium-based browser (Chrome, Edge, Arc, Brave) or Safari is recommended.
Supported: Chrome, Safari, Edge, Firefox (Fallbacks applied).
Mobile: Fully touch-optimized (Touch events natively mapped to the physics engine).
📄 License
This project is open-source and available under the MIT License. Feel free to pull apart the engine and use the physics/SVG filters in your own projects!
