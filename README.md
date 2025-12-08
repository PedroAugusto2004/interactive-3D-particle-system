<![CDATA[<div align="center">

# 🌌 Interactive 3D Particle System

### Real-Time Hand Gesture Control with AI-Powered Tracking

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-Try_Now-00d2ff?style=for-the-badge&labelColor=050505)](https://pedroaugusto2004.github.io/interactive-3D-particle-system/)
[![Three.js](https://img.shields.io/badge/Three.js-0.160.0-black?style=for-the-badge&logo=threedotjs&logoColor=white)](https://threejs.org/)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Hands-00897B?style=for-the-badge&logo=google&logoColor=white)](https://mediapipe.dev/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

<br>

<img src="https://img.shields.io/badge/WebGL-990000?style=flat&logo=webgl&logoColor=white" alt="WebGL" />
<img src="https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat&logo=javascript&logoColor=black" alt="JavaScript" />
<img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white" alt="HTML5" />
<img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white" alt="CSS3" />

---

**An immersive 3D particle visualization that responds to your hand movements in real-time.**  
Control 25,000 particles with natural gestures through your webcam.

[**🎮 Try it Live**](https://pedroaugusto2004.github.io/interactive-3D-particle-system/) · [Report Bug](https://github.com/PedroAugusto2004/interactive-3D-particle-system/issues) · [Request Feature](https://github.com/PedroAugusto2004/interactive-3D-particle-system/issues)

</div>

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🖐️ **Hand Gesture Recognition**
Real-time hand tracking powered by Google's MediaPipe AI. Move your hand to rotate the particle field, make a fist to compress, and open your palm to expand.

### 🎨 **Dynamic Particle Shapes**
Switch between 5 stunning templates:
- ❤️ **Heart** - Classic love symbol
- 🌸 **Flower** - Organic petal patterns
- 🪐 **Saturn** - Planet with orbital rings
- 🧘 **Buddha** - Spiritual meditation figure
- 🎆 **Fireworks** - Explosive sphere distribution

</td>
<td width="50%">

### ⚡ **High-Performance Rendering**
- 25,000 particles with smooth animations
- WebGL-accelerated graphics via Three.js
- Additive blending for vibrant glow effects
- Fog effects for depth perception

### 🎛️ **Customizable Controls**
- Real-time color picker
- Adjustable particle size (0.01 - 1.0)
- Mouse/trackpad OrbitControls fallback
- Auto-rotation when hands not detected

</td>
</tr>
</table>

---

## 🎮 How to Use

### Gesture Guide

| Gesture | Action | Description |
|:-------:|:------:|:------------|
| 🖐️ **Move Hand** | Rotate View | Position your hand in the camera to control the 3D rotation |
| ✊ **Make Fist** | Compress | Close your hand to shrink the particle formation |
| ✋ **Open Palm** | Expand | Spread your fingers to let particles relax outward |

### Getting Started

1. **Open the application** in a modern browser (Chrome/Edge recommended)
2. **Allow camera access** when prompted
3. **Position your hand** in view of the webcam
4. **Experiment with gestures** to control the particles

> 💡 **Tip:** Ensure good lighting conditions for optimal hand detection accuracy.

---

## 🚀 Quick Start

### Option 1: Live Demo (Recommended)
Simply visit the live deployment:

**👉 [https://pedroaugusto2004.github.io/interactive-3D-particle-system/](https://pedroaugusto2004.github.io/interactive-3D-particle-system/)**

### Option 2: Run Locally

```bash
# Clone the repository
git clone https://github.com/PedroAugusto2004/interactive-3D-particle-system.git

# Navigate to the project directory
cd interactive-3D-particle-system

# Serve with any static file server (required for ES modules)
# Using Python 3:
python -m http.server 8000

# Or using Node.js:
npx serve .

# Open in browser
# Navigate to http://localhost:8000
```

> ⚠️ **Note:** Due to ES6 modules and camera access requirements, you must serve the files through a local server (not by opening the HTML file directly).

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| [**Three.js**](https://threejs.org/) `v0.160.0` | 3D graphics rendering & WebGL abstraction |
| [**MediaPipe Hands**](https://google.github.io/mediapipe/solutions/hands.html) | AI-powered hand landmark detection |
| [**lil-gui**](https://lil-gui.georgealways.com/) `v0.19.1` | Lightweight GUI controls |
| **OrbitControls** | Camera rotation & zoom interactions |
| **WebGL** | Hardware-accelerated graphics |

---

## 📁 Project Structure

```
interactive-3D-particle-system/
│
├── index.html          # Main application (single-file architecture)
│   ├── Styles          # Embedded CSS for UI components
│   ├── Three.js Scene  # 3D rendering setup
│   ├── Particle System # 25,000 particle management
│   ├── Shape Generator # Mathematical shape algorithms
│   ├── MediaPipe Setup # Hand tracking configuration
│   └── GUI Controls    # User interface panel
│
└── README.md           # Project documentation
```

---

## 🔧 Configuration

The application includes configurable parameters that can be modified:

```javascript
const CONFIG = {
    particleCount: 25000,       // Number of particles
    baseColor: '#00d2ff',       // Default cyan color
    glowIntensity: 1.5,         // Particle brightness
    particleSize: 0.29403,      // Individual particle size
    shape: 'Heart',             // Default shape template
    cameraZ: 30,                // Camera distance
    tensionSensitivity: 2.0     // Hand gesture sensitivity
};
```

---

## 🧮 Shape Algorithms

The particle system uses mathematical formulas to create each shape:

<details>
<summary><b>❤️ Heart Shape</b></summary>

Uses the parametric heart equation:
```
x = 16 * sin³(t)
y = 13*cos(t) - 5*cos(2t) - 2*cos(3t) - cos(4t)
```
With added Z-depth for 3D volume.

</details>

<details>
<summary><b>🌸 Flower Shape</b></summary>

Rose curve (rhodonea) with 4 petals:
```
r = 10 * cos(4θ)
x = r * cos(θ)
y = r * sin(θ)
```

</details>

<details>
<summary><b>🪐 Saturn Shape</b></summary>

Combines a spherical core (70% of particles) with a tilted ring system (30% of particles) using trigonometric rotation matrices.

</details>

<details>
<summary><b>🧘 Buddha Shape</b></summary>

Composite shape with:
- Spherical head (15% of particles)
- Cylindrical body (45% of particles)  
- Cross-legged base (40% of particles)

</details>

<details>
<summary><b>🎆 Fireworks Shape</b></summary>

Volumetric sphere with cube-root radial distribution for uniform density:
```
r = 15 * ∛(random)
```

</details>

---

## 🌐 Browser Compatibility

| Browser | Support | Notes |
|---------|:-------:|-------|
| Chrome | ✅ | Recommended - Best performance |
| Edge | ✅ | Full support |
| Firefox | ✅ | Full support |
| Safari | ⚠️ | WebGL support varies by version |
| Mobile Chrome | ✅ | Touch + Camera supported |
| Mobile Safari | ⚠️ | Limited camera access |

### Requirements
- Modern browser with **WebGL** support
- **Webcam** for hand tracking features
- **HTTPS** connection (required for camera access on deployed sites)

---

## 📊 Performance

The application is optimized for smooth performance:

- **Particle Count:** 25,000 particles with position interpolation
- **Frame Rate:** Targets 60 FPS on modern hardware  
- **Pixel Ratio:** Capped at 2x for Retina displays
- **Hand Detection:** Runs at camera frame rate (~30 FPS)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Ideas for Contributions
- [ ] Add more particle shape templates
- [ ] Implement two-hand gesture support
- [ ] Add audio reactive mode
- [ ] Create shape morphing transitions
- [ ] Add particle trail effects

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [**Three.js**](https://threejs.org/) - The incredible 3D library that makes this possible
- [**MediaPipe**](https://mediapipe.dev/) - Google's machine learning solutions for hand tracking
- [**lil-gui**](https://lil-gui.georgealways.com/) - Beautiful, lightweight GUI library

---

<div align="center">

### ⭐ Star this repo if you found it interesting!

Made with ❤️ by [Pedro Augusto](https://github.com/PedroAugusto2004)

[![GitHub followers](https://img.shields.io/github/followers/PedroAugusto2004?style=social)](https://github.com/PedroAugusto2004)

</div>
]]>
