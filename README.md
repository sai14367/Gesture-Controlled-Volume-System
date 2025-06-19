
---

## 📢 Hand Gesture Volume Control System 🎚️🖐️

Control your system volume using just your fingers!
This Python project uses your webcam to detect hand gestures and adjust the system volume based on the distance between your **thumb** and **index finger**—like magic ✨.

---

### 📷 Demo
https://www.linkedin.com/posts/venkata-sai-kumar-masanam-56458a27b_python-opencv-mediapipe-activity-7341384819785797634-OC68?utm_source=social_share_send&utm_medium=android_app&rcm=ACoAAERAOpwBNo7c8a6Q5dip7uOx1bPoRVrRDIQ&utm_campaign=copy_link

---

## 🔧 Technologies Used

* **Python**
* **OpenCV** – Image processing & webcam
* **MediaPipe** – Hand tracking
* **Pycaw** – Control system volume
* **NumPy** – For calculations

---

## ⚙️ Features

* 📸 Real-time webcam-based hand tracking
* ✋ Detects thumb and index finger positions
* 📏 Calculates distance between fingers
* 🔊 Dynamically adjusts system volume
* 📈 Displays live FPS
* 🟩 Visual volume bar shown on screen

---

## 🛠️ Installation

1. **Clone this repository**

   ```bash
   git clone https://github.com/your-username/gesture-volume-control.git
   cd gesture-volume-control
   ```

2. **Install the required packages**
   Make sure you're using Python 3.7+:

   ```bash
   pip install opencv-python mediapipe numpy comtypes pycaw
   ```

---

## ▶️ How to Run

1. Make sure your webcam is connected.
2. Run the Python script:

   ```bash
   python volume_control.py
   ```
3. Show your hand to the camera.
4. Move your thumb and index finger closer/farther to adjust volume.
5. Press `q` to quit the application.

---

## 🖼️ How It Works

* Uses **MediaPipe Hands** to detect 21 key hand landmarks
* Tracks only:

  * **Landmark 4** (Thumb tip)
  * **Landmark 8** (Index finger tip)
* Measures distance between these two points
* Maps the distance to system volume using Pycaw
* Uses interpolation to scale the distance into the audio range
* Displays a visual feedback bar for volume level

---

## 📌 Requirements

* Windows OS (PyCaw is Windows-specific)
* Python 3.7 or later
* Webcam

---

## 📁 File Structure

```
gesture-volume-control/
├── volume_control.py       # Main script
├── README.md               # Project readme
```

---

## 📈 Distance-Volume Mapping Logic

```python
length = np.hypot(x2 - x1, y2 - y1)
volume = np.interp(length, [20, 200], [min_vol, max_vol])
volume.SetMasterVolumeLevel(volume, None)
```

---

## 📌 Tips

* Make sure **no other app is using the webcam**
* If camera doesn't work, change this line:

  ```python
  cap = cv2.VideoCapture(0)  # try cap = cv2.VideoCapture(1)
  ```
* Lighting matters! Use in a well-lit environment for best results.

---

## 👨‍💻 Author

**Venkata Sai Kumar Masanam**
💼 Python Developer
🧠 Passionate about AI, CV, and Automation

---
