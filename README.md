# Aizawa Attractor Visualization

## Overview
This repository contains an interactive 3D web visualization of the **Aizawa attractor**, a classic chaotic system from chaos theory. The attractor is rendered with **Three.js** and features:

- Smooth 3D curve generated from the Aizawa ODE system.
- Color gradient (deep blue → cyan → magenta) that indicates the flow direction.
- Bloom post‑processing for a glowing, energy‑field look.
- OrbitControls for rotation, zoom, and pan.
- Live UI controls (via `lil‑gui`) to adjust the attractor parameters `a, b, c, d, f` in real time.
- Animation of a glowing sphere traveling along the trajectory, with a fading trail.
- Simple explanatory side panel describing the attractor and its mathematics.

The project is built with modern JavaScript (ES modules) and uses **Vite** as the development server and build tool.

## Features
- **Accurate mathematics**: Implements the continuous‑time Aizawa ODE with classic parameter values.
- **Dynamic visualization**: Real‑time updates when parameters change.
- **Performance‑focused**: Uses a single `BufferGeometry` and reuses materials to avoid per‑frame allocations.
- **Responsive UI**: Sliders, randomize/reset buttons, and toggles for trail/full‑curve modes.
- **Adjustable animation speed**.

## Installation
```bash
# Clone the repository (if you haven't already)
git clone https://github.com/Ramakm/aizawa-attractor.git
cd aizawa-attractor

# Install dependencies
npm install
```

## Development
Start the development server:
```bash
npm run dev
```
Open the URL shown in the terminal (usually `http://localhost:5173`). The visualization will load automatically.

## Build for Production
```bash
npm run build
```
The built files are placed in the `dist/` directory and can be served by any static web server.

## Usage
- **OrbitControls**: Left‑drag to rotate, scroll to zoom, right‑drag to pan.
- **Parameter sliders**: Adjust `a, b, c, d, f` to explore different chaotic shapes.
- **Randomize**: Click the *Randomize Parameters* button for nearby values.
- **Reset**: Restores the classic parameter set (`a=0.95, b=0.7, c=0.6, d=3.5, f=0.1`).
- **Trail / Full Curve**: Toggle between showing only the moving point with a short trail or the entire attractor curve.
- **Play / Pause**: Control the animation of the traveling sphere.
- **Speed**: Choose *slow*, *normal*, or *fast* animation speed.

## Math Details
The attractor follows the continuous‑time ODE system:
```
dx/dt = (z - b) * x - d * y
dy/dt = d * x + (z - b) * y
dz/dt = c + a * z - (z³ / 3) - x² + f * z * x³
```
Classic parameters:
- `a = 0.95`
- `b = 0.7`
- `c = 0.6`
- `d = 3.5`
- `f = 0.1`

Initial point: `(x0, y0, z0) = (0.1, 0.0, 0.0)`
Integration uses a fixed time step (`dt ≈ 0.01`) to generate tens of thousands of points.

## Project Structure
```
aizawa-attractor/
├─ index.html          # Entry HTML file
├─ src/
│   ├─ main.js        # Entry point, wires everything together
│   ├─ scene.js       # Three.js scene, camera, renderer, post‑processing
│   ├─ math.js        # ODE integration logic
│   ├─ attractor.js   # Geometry creation, animation, color gradient
│   ├─ ui.js          # lil‑gui controls and UI handling
│   └─ style.css      # Global styling
├─ package.json        # npm scripts and dependencies
└─ README.md           # This document
```

## Contributing
Feel free to open issues or submit pull requests for improvements, bug fixes, or new features (e.g., alternative attractors, additional visual effects, etc.).

## License
This project is licensed under the ISC license.

## Check out my social profiles here:
[Instagram](https://www.instagram.com/techwith.ram/)
[X](https://x.com/techwith_ram)
[LinkedIn](https://www.linkedin.com/in/ramakrushnamohapatra/)
[GitHub](https://github.com/Ramakm)