# 🫀 Retina HR AI — Real-Time Heart Rate Estimation using Face & Eye Analysis

## 📌 Overview
Retina HR AI is a real-time computer vision project that estimates human heart rate (BPM) using a webcam. It uses **Face Mesh detection, eye region tracking, and rPPG (remote photoplethysmography)** principles to extract subtle color changes from facial skin and convert them into a pulse signal.

The system also includes **blink detection (EAR method)** to remove unstable frames and improve accuracy.

---

## 🎯 Project Goal
To estimate heart rate in real-time using only a standard webcam without any wearable devices.

---

## 🚀 Features
- 🎥 Real-time webcam processing
- 🧠 MediaPipe FaceMesh landmark detection
- 👁️ Eye region extraction for signal stability
- ❤️ Heart rate estimation (BPM)
- 📊 Live signal visualization graph
- 😴 Blink detection using Eye Aspect Ratio (EAR)
- 🔊 Noise reduction using filters
- 📈 FFT-based frequency analysis
- 🧪 Signal smoothing for stable BPM output

---

## 🏗️ Project Structure

```text
retina_hr_ai/
│
├── detection/
│   ├── facemesh_detector.py     # Detects face landmarks using MediaPipe
│   └── eye_roi.py               # Extracts eye region of interest (ROI)
│
├── cnn/
│   └── efficientphys.py         # Extracts rPPG-like pulse signal from ROI
│
├── processing/
│   ├── blink_detector.py        # EAR (Eye Aspect Ratio) calculation
│   ├── filter.py                # Bandpass filtering (0.8–2.0 Hz)
│   └── bpm.py                   # FFT-based BPM calculation
│
├── main.py                      # Main application (webcam pipeline)
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation

<img width="981" height="482" alt="Screenshot 2026-06-06 202456" src="https://github.com/user-attachments/assets/5886ba7e-f64a-4214-b6cb-d3dbaae2ccdb" />
<img width="1037" height="507" alt="Screenshot 2026-06-06 202654" src="https://github.com/user-attachments/assets/c67c01ff-b4bd-42e4-9f17-efa19670759a" />
