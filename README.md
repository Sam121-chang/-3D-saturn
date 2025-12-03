# 🪐 Saturn Protocol // Interactive Particle System

> A real-time, gesture-controlled 3D visualization of a chaotic planetary system.
> 一个基于 WebGL 的实时手势交互星环粒子系统。

![Project Status](https://img.shields.io/badge/Status-Live-success)
![Tech](https://img.shields.io/badge/Tech-Three.js%20%7C%20MediaPipe%20%7C%20WebGL-blueviolet)

## 🌌 Project Overview (项目简介)

此项目是一个运行在浏览器中的高能粒子模拟系统。它利用 **Three.js** 和 **自定义着色器 (GPGPU Shaders)** 渲染了 80,000+ 个动态粒子，模拟土星环的物理运动。

核心亮点在于结合了 **Google MediaPipe** 手势识别技术，允许用户通过**摄像头**实时控制星系的演变：从有序的开普勒轨道运动，到热力学极端的混沌炸裂状态。

**✨ 在线体验 (Demo):** [点击这里进入沉浸模式](https://github.com/Sam121-chang/-3D-saturn)


## 🎮 How to Control (交互方式)

系统支持多模态交互，优先使用 AI 手势识别，并在网络受限时自动降级为光感应或鼠标控制。

| 交互模式 | 操作说明 | 视觉效果 |
| :--- | :--- | :--- |
| **👋 手势控制 (AI)** | **张开手掌** | 粒子加速、膨胀、亮度爆发，进入“混沌”状态 |
| | **握紧拳头** | 粒子坍缩、变暗，回归有序的开普勒轨道 |
| **🖱️ 鼠标/触摸** | **按住并向上拖动** | 强制接管控制权，手动触发展开效果 |
| **💡 光感应 (备用)** | **遮挡/靠近摄像头** | 利用画面亮度变化驱动粒子（当 AI 加载失败时自动激活） |

## 🛠️ Tech Stack (技术栈)

* **Core Engine:** [Three.js](https://threejs.org/) (r160)
* **Visual Effects:** Custom GLSL Shaders (Vertex & Fragment)
* **Post-Processing:** Unreal Bloom Pass (Hollywood-grade glow)
* **Computer Vision:** [Google MediaPipe](https://developers.google.com/mediapipe) (Hand Landmark Detection)
* **Physics:** Keplerian Orbit Simulation + Brownian Motion Noise

## 🚀 Key Features (核心特性)

1.  **GPGPU 级粒子渲染：** 不依赖 CPU，所有粒子位置运算、噪点生成均在 GPU 的 Vertex Shader 中完成，实现 60FPS 丝滑体验。
2.  **动态物理法则：**
    * **有序态：** 遵循 $v \propto \frac{1}{\sqrt{r}}$ 的天体运行规律。
    * **混沌态：** 引入高频正弦噪声与布朗运动模拟，打破物理轨道。
3.  **自适应回退机制 (Fallback System)：**
    * 检测到网络问题无法加载 AI 模型时，自动切换至算法更简单的“光感应模式”，确保程序永不崩溃。

## 📦 How to Run Locally (本地运行)

如果你想在本地修改代码：

1.  克隆仓库：(https://github.com/Sam121-chang/-3D-saturn)
    
    
2.  使用 **VSCode** 打开文件夹。
3.  安装 **Live Server** 插件。
4.  右键 `index.html` 选择 **"Open with Live Server"**。

---

*Created by [Chang] - 2025*
