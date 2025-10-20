
## ✋ **Gesture Volume Controller**

### 📘 Overview

The **Gesture Volume Controller** is an interactive computer vision project that allows users to **control the system’s audio volume using hand gestures**.
It combines **OpenCV**, **MediaPipe Hand Tracking**, and **PyCAW (Python Core Audio Windows Library)** to map hand gestures to system volume levels in real-time.

---

### ⚙️ Tech Stack

* **Python 3.x**
* **OpenCV** – for camera feed & visualization
* **MediaPipe** – for hand tracking and landmarks
* **NumPy** – for value interpolation
* **PyCAW** – for controlling Windows audio APIs

---

### 🚀 Features

* Control system volume using distance between thumb and index finger
* Real-time hand tracking and gesture detection
* Volume bar visualization for feedback
* Smooth and precise volume adjustment
* Works seamlessly on Windows systems

---

### 🧩 Working Principle

1. The webcam captures frames in real-time.
2. The **hand tracking module** detects landmarks (key points) on the hand.
3. It identifies the **tip of the thumb (ID 4)** and **index finger (ID 8)**.
4. The **Euclidean distance** between these two points is calculated.
5. The distance is mapped (interpolated) to a range between the system’s minimum and maximum volume using NumPy.
6. As you move your fingers closer or farther, the volume decreases or increases accordingly.
7. A volume bar and percentage are displayed for better visual feedback.

---

### 📦 Installation

```bash
pip install opencv-python mediapipe numpy pycaw comtypes
```

---

### ▶️ How to Run

```bash
python GestureVolumeController.py
```

---

### 🖼️ Output Example

* When you move your **thumb and index finger apart**, volume increases 🔊
* When you bring them close together, volume decreases 🔉
* A real-time volume bar and FPS counter are shown on screen

---

### 🔍 Code Flow Summary

1. Initialize camera & PyCAW audio endpoint
2. Track hand using MediaPipe
3. Detect positions of landmarks 4 (thumb tip) and 8 (index tip)
4. Calculate distance → interpolate → map to system volume
5. Update visuals with real-time feedback

---

### 💡 Future Enhancements

* Add gesture-based mute/unmute feature
* Support for both hands
* Integrate with cross-platform audio APIs
* Display hand landmarks for better visualization
