# Vision Mechanics: HackTronix 2.0 CV Suite

**TEAM: STRIKERS**  
**OP: R TARUN RAGAV**

Official HackTronix 2.0 CV suite by TEAM:STRIKERS. Features robust multi-object ball detection and a pure-math Delaunay triangulation engine for monocular 3D face telemetry. Calculates spatial depth and deviation angles natively. 

---

## 🚀 Task 1: Ball Detection Mechanics

A high-speed tracking module designed to identify and isolate dynamic spherical objects (balls) within the camera frame in real-time. 

### 🎥 Live Demonstration
<!-- Paste your GitHub Issue video link inside the src quotes below -->
<video src="https://drive.google.com/file/d/1aqjT1zoIkju-9i1Gq9197YbBWHdFiw36/view?usp=sharing" controls="controls" muted="muted" width="100%"></video>

**Key Features:**
*   **Dynamic Object Tracking:** Isolates targets efficiently under varying lighting conditions.
*   **Real-Time Bounding Boxes:** Draws high-contrast tracking geometry on live video feeds.
*   **Optimized Compute:** Maintains high FPS without relying on heavy external processing arrays.

---

## 📐 Task 2: Monocular Face Distance Estimation

A real-time spatial awareness engine that completely bypasses standard 3D rendering engines by utilizing pure OpenCV math. It generates a dynamic Delaunay Triangulation mesh overlay while calculating precise physical depth and deviation angles from a single monocular camera feed.

### 🎥 Live Demonstration
<!-- Paste your video link inside the src quotes below -->
<video src="https://drive.google.com/file/d/1ZuOadbNGAmX5WN87aARt7kPq3R9LAiWY/view?usp=sharing" controls="controls" muted="muted" width="100%"></video>

### The Mathematical Model
The engine avoids stereoscopic requirements by utilizing known physical constants and focal length estimation.

*   **Depth ($Z$):** Calculated in meters utilizing the bounding box of the generated 3D topology map:
    $$Z = \frac{f \times W}{w_{px}}$$
*   **Angle ($\theta$):** Calculated via horizontal pixel deviation from the camera center axis:
    $$\theta = \arctan\left(\frac{x - c_x}{f}\right)$$

**Key Features:**
*   **Dynamic Delaunay Geometry:** Calculates optimal triangular topology natively on the fly, rendering a live mesh without relying on hardcoded connection maps.
*   **Multi-Target Telemetry:** Tracks up to 5 human faces simultaneously, complete with an active faces counter.
*   **Custom Dark Mode UI:** Integrated heads-up display built with Green/Blue terminal aesthetics.
---

## 🛠️ Installation & Execution

This suite is built for native deployment on **Python 3.14** using MediaPipe's modern Tasks API and OpenCV.

**1. Clone the repository:**
```bash
git clone [https://github.com/YOUR_USERNAME/vision-mechanics.git](https://github.com/YOUR_USERNAME/vision-mechanics.git)
cd vision-mechanics

**2. Install dependencies:**
pip install opencv-python mediapipe

**3. Launch the modules:**
To run the Ball Detection module:
python ap.py
To run the 3D Face Telemetry module:
python task2_face_distance.py

