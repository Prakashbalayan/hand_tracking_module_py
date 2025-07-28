# hand_tracking_module_py
This module enables real-time hand tracking using a webcam feed. Built with Python, OpenCV, and MediaPipe, it detects hands, identifies key landmarks, and provides their coordinates for gesture-based applications like sign language recognition, virtual mouse control, or gaming.


# ✋ Hand Tracking Module using Python & OpenCV

This project provides a simple and efficient Python module (`hand_tracking_module.py`) to detect and track hands in real-time using a webcam. It uses **MediaPipe** for hand landmark detection and **OpenCV** for video processing and visualization.

## 🔍 Features

- Real-time hand tracking from webcam
- Detects and tracks multiple hands
- Extracts 21 landmarks for each hand (fingertips, joints, etc.)
- Provides landmark positions (x, y, z coordinates)
- Draws hand landmarks and connections on video frames
- Easy to integrate into gesture recognition or control systems

---

## 🛠️ Technologies Used

- Python
- OpenCV
- MediaPipe

---

## 📦 Installation

1. **Clone this repository**
   ```bash
   git clone https://github.com/your-username/hand_tracking_module.git
   cd hand_tracking_module

   pip install opencv-python mediapipe
import cv2
from hand_tracking_module import HandDetector

cap = cv2.VideoCapture(0)
detector = HandDetector(detection_confidence=0.7)

while True:
    success, img = cap.read()
    img = detector.find_hands(img)
    lm_list = detector.find_position(img)

    if lm_list:
        print(lm_list[4])  # Tip of thumb, example

    cv2.imshow("Hand Tracking", img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

