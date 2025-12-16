# 🚗 Real-Time Object Detection with CARLA & YOLOv11

![Python](https://img.shields.io/badge/Python-3.8-blue?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-CUDA%2012.1-red?logo=pytorch&logoColor=white)
![CARLA](https://img.shields.io/badge/Simulator-CARLA%200.9.13-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

**A real-time perception system for autonomous driving using CARLA Simulator and YOLOv11.**

This project demonstrates real-time object detection (vehicles, pedestrians, traffic signs) inside a realistic simulation environment using **CARLA Simulator** integrated with **YOLOv11**. The system is optimized for **NVIDIA GPUs** and uses **Synchronous Mode** to ensure stable performance, zero lag, and high FPS.

---

## 📷 Demo Results

| **Detection View** | **Simulator View** |
|:---:|:---:|
| ![Detection Output](image_9faf66.jpg) | ![CARLA View](image_a00995.jpg) |
*(Real-time bounding boxes showing high confidence scores)*

---

## 📋 Prerequisites

Before you begin, ensure you have the following:
- **OS:** Windows 10 / 11
- **GPU:** NVIDIA RTX/GTX Series (Tested on **RTX 3050 Ti**)
- **Simulator:** CARLA 0.9.13 (or newer)
- **Environment:** Anaconda / Miniconda

---

## 🛠️ Installation & Setup

### 1️⃣ Download CARLA Simulator
1. Download CARLA (Windows version) from the [Official Releases Page](https://github.com/carla-simulator/carla/releases).
2. Extract the folder to a short path (e.g., `C:\CARLA`).
3. **Important:** On Windows, you must run CARLA with DirectX 11.

### 2️⃣ Create Anaconda Environment
Open your **Anaconda Prompt** and run the following commands:

```bash
# Create a new environment with Python 3.8 (Recommended for CARLA)
conda create -n FinalProject python=3.8

# Activate the environment
conda activate FinalProject

3️⃣ Install PyTorch (GPU Support)
To utilize your NVIDIA GPU, install the CUDA-enabled version of PyTorch:
pip install torch torchvision torchaudio --index-url [https://download.pytorch.org/whl/cu121](https://download.pytorch.org/whl/cu121)

4️⃣ Install Dependencies
Install YOLO (Ultralytics), OpenCV, and the CARLA Python API:
pip install ultralytics opencv-python numpy
pip install carla

🚀 How to Run
Step 1: Start CARLA Server
Navigate to your CARLA folder and run the executable with the -dx11 flag:
C:\CARLA\CarlaUE4.exe -dx11
Wait until the simulator opens and the city map loads completely.

Step 2: Run the Detection Script
Open a new Anaconda Prompt window, navigate to your project folder, and run:
conda activate FinalProject
python run_project.py

🌟 Key Features
⚡ Synchronous Mode: Locks the simulator step to the model inference to prevent frame drops and application freezing.

🗺️ Map Layer Optimization: Programmatically hides buildings and foliage to boost FPS on laptop GPUs.

🚀 GPU Acceleration: Native PyTorch (.pt) inference running on CUDA cores.

🛡️ Robust Error Handling: Auto-recovery from connection timeouts.

👨‍💻 Developed By
Khaled Ahmed