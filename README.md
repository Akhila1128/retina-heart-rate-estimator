# 🫀 Retina HR AI — Real-Time Heart Rate Estimation using Computer Vision

## 📌 Project Overview

**Retina HR AI** is a real-time, non-contact heart rate monitoring system that estimates pulse (BPM) using only a standard webcam. It is based on the principle of **Remote Photoplethysmography (rPPG)**, which captures subtle variations in skin color caused by blood flow beneath the facial surface.

Unlike traditional wearable devices (ECG or pulse oximeters), this system uses **computer vision + signal processing** to extract physiological signals from facial video frames.

The project integrates:
- **Face landmark detection (MediaPipe FaceMesh)**
- **Region-based signal extraction (eye/face ROI)**
- **Time-domain and frequency-domain signal processing**
- **Real-time visualization and stabilization techniques**

---

## 🎯 Objective

To develop a non-invasive, real-time physiological monitoring system capable of estimating heart rate using standard RGB video input, without requiring any physical sensors or wearable devices.

---

## 🧠 Core Concept (How It Works)

The system is based on the idea that:

> Blood flow changes slightly alter the color intensity of facial skin, especially in the green channel of RGB frames.

These tiny variations are invisible to the human eye but can be extracted using computational methods.

---

## ✨ Key Features

- 🎥 Real-time webcam-based processing
- 🧠 Face landmark detection using MediaPipe FaceMesh (468 points)
- 👁️ Eye Region of Interest (ROI) extraction for stable signal capture
- ❤️ Heart rate (BPM) estimation using rPPG technique
- 😴 Blink detection using Eye Aspect Ratio (EAR)
- 📊 Live signal waveform visualization
- 🔊 Noise reduction using bandpass filtering
- 📈 FFT-based frequency analysis for pulse detection
- 🧪 Smoothed BPM output for stability and reduced fluctuations
- ⚡ Lightweight and runs on CPU in real time

---
<img width="981" height="482" alt="Screenshot 2026-06-06 202456" src="https://github.com/user-attachments/assets/a1db2636-8be5-4b4c-87f2-6faad1c0045e" />
<img width="1037" height="507" alt="Screenshot 2026-06-06 202654" src="https://github.com/user-attachments/assets/da7b249d-30b0-4f36-b7a3-998038584a5c" />


## 🏗️ Project Architecture

```text
retina_hr_ai/
│
├── detection/
│   ├── facemesh_detector.py   → Detects facial landmarks using MediaPipe FaceMesh
│   └── eye_roi.py             → Extracts eye region for signal processing
│
├── cnn/
│   └── efficientphys.py       → rPPG-inspired signal extraction module
│
├── processing/
│   ├── blink_detector.py      → Eye Aspect Ratio (EAR) based blink detection
│   ├── filter.py              → Bandpass filter (0.8–2.0 Hz) for noise removal
│   └── bpm.py                 → Heart rate estimation using FFT analysis
│
├── main.py                    → Main pipeline integrating all modules
├── requirements.txt           → Required Python dependencies
└── README.md                  → Project documentation
