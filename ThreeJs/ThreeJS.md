<!-- ================= HEADER ================= -->

<h1 align="center">
  🌌 Three.js – Complete Developer Guide for 3D on Web
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/WebGL-3D%20Rendering-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Three.js-JavaScript%203D-000000?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Level-Frontend%20Graphics-success?style=for-the-badge" />
</p>

---

# 🚀 What is Three.js?

> Three.js is a JavaScript library used to create and display 3D graphics in the browser using WebGL.

It allows you to build:
- 3D websites
- Interactive portfolios
- Games
- 3D product showcases
- Metaverse-style UIs
- Data visualizations

---

# 🧠 Three.js Rendering Pipeline


::contentReference[oaicite:0]{index=0}


### 🔁 Rendering Flow

1. Create Scene
2. Add Camera
3. Add Objects (Mesh)
4. Add Light
5. Render using Renderer
6. Animate with render loop

> Everything starts with Scene → Camera → Renderer

---

# 📦 Installation

### Using npm

```bash
npm install three
```

### Using CDN

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
```

---

# 🏗 Basic Setup (Minimal 3D Scene)

```js
import * as THREE from "three";

// Scene
const scene = new THREE.Scene();

// Camera
const camera = new THREE.PerspectiveCamera(
  75,
  window.innerWidth / window.innerHeight,
  0.1,
  1000
);

// Renderer
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Geometry + Material + Mesh
const geometry = new THREE.BoxGeometry();
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const cube = new THREE.Mesh(geometry, material);

scene.add(cube);
camera.position.z = 5;

// Render
renderer.render(scene, camera);
```

---

# 🎬 Animation Loop

```js
function animate() {
  requestAnimationFrame(animate);

  cube.rotation.x += 0.01;
  cube.rotation.y += 0.01;

  renderer.render(scene, camera);
}

animate();
```

> `requestAnimationFrame` creates smooth animation.

---

# 🎥 Core Components

| Component | Purpose |
|------------|----------|
| Scene | Holds all objects |
| Camera | Viewpoint |
| Renderer | Draws scene |
| Geometry | Shape |
| Material | Surface appearance |
| Mesh | Geometry + Material |
| Light | Illuminates objects |

---

# 💡 Lighting Example

```js
const light = new THREE.PointLight(0xffffff, 1);
light.position.set(5, 5, 5);
scene.add(light);
```

Types of lights:
- AmbientLight
- DirectionalLight
- PointLight
- SpotLight

---

# 🧱 Geometries

```js
new THREE.BoxGeometry();
new THREE.SphereGeometry();
new THREE.ConeGeometry();
new THREE.PlaneGeometry();
new THREE.TorusGeometry();
```

---

# 🎨 Materials

```js
new THREE.MeshBasicMaterial();
new THREE.MeshStandardMaterial();
new THREE.MeshPhongMaterial();
new THREE.MeshLambertMaterial();
```

StandardMaterial supports realistic lighting.

---

# 🌍 Loading 3D Models (GLTF / GLB)

```js
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader";

const loader = new GLTFLoader();

loader.load("/model.glb", (gltf) => {
  scene.add(gltf.scene);
});
```

Supported formats:
- `.glb`
- `.gltf`
- `.obj`
- `.fbx`

---

# 🎮 Orbit Controls (User Interaction)

```js
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";

const controls = new OrbitControls(camera, renderer.domElement);
controls.enableDamping = true;
```

Allows:
- Rotate
- Zoom
- Pan

---

# 📱 Responsive Canvas

```js
window.addEventListener("resize", () => {
  camera.aspect = window.innerWidth / window.innerHeight;
  camera.updateProjectionMatrix();
  renderer.setSize(window.innerWidth, window.innerHeight);
});
```

---

# ⚡ Performance Optimization

✔ Use low-poly models  
✔ Use compressed textures  
✔ Enable frustum culling  
✔ Use instancing for repeated objects  
✔ Limit shadow calculations  

---

# 🧠 Three.js in React (React Three Fiber)

Instead of vanilla:

```bash
npm install @react-three/fiber
```

Example:

```js
import { Canvas } from "@react-three/fiber";

function App() {
  return (
    <Canvas>
      <mesh>
        <boxGeometry />
        <meshStandardMaterial color="orange" />
      </mesh>
    </Canvas>
  );
}
```

---

# 🏗 Project Structure Example

```
src/
 ├── scene/
 │     ├── camera.js
 │     ├── lights.js
 │     ├── objects.js
 │
 ├── loaders/
 ├── controls/
 └── main.js
```

---

# 🔥 Common Mistakes

❌ Forgetting animation loop  
❌ Not updating camera on resize  
❌ Heavy models without optimization  
❌ Using wrong material for lighting  
❌ Forgetting to add lights  

---

# 🧠 Interview Questions

- What is Three.js?
- How does WebGL work?
- What is rendering pipeline?
- Difference between geometry & mesh?
- What is GLTF?
- How to optimize 3D scenes?

---

# 💎 Final Thought

> Three.js brings powerful 3D experiences to the browser.  
> Master Scene → Camera → Renderer and you master Web 3D.

---

<p align="center">
  Built with 🌌 by Mihir Patel
</p>
