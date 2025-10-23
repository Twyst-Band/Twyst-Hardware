# Twyst — Intelligent Motion Tracking & Exercise Feedback System

## Overview

Twyst is a wearable motion analysis system that integrates sensor-embedded bandanas with an intuitive mobile application to monitor, evaluate, and improve human movement. Designed for sports, fitness, rehabilitation, and physical therapy, Twyst provides real-time feedback on exercise execution accuracy using advanced motion analysis and AI-based comparison algorithms.

Developed by students from the National College of Computer Science “Grigore Moisil” Brașov, Twyst combines embedded engineering, data science, and mobile app design to create a seamless hardware-software ecosystem that makes motion tracking accessible and engaging.
 
## Objectives

Twyst aims to:
- Provide precise motion analysis using distributed wearable sensors.
- Deliver live, data-driven feedback for form correction and performance improvement.
- Develop a machine-learning framework that learns from professionals and guides beginners.
- Support medical rehabilitation by tracking therapeutic exercises and preventing re-injury.
- Offer a comfortable, modular, and scalable hardware system adaptable to various body types and activities.

Key operational goals include:
- <2° RMS error in orientation estimation.
- 95% exercise recognition accuracy.
- Real-time posture correction feedback.
- 8+ hours battery life and automatic calibration.

## How It Works

The system operates in two main phases:
1.	Training Phase – A professional user performs multiple repetitions of an exercise wearing several Twyst bandanas. The algorithm identifies the most relevant sensors and stores their motion data as a reference.
2.	User Phase – A beginner attaches bandanas to the same body parts and performs the exercise. Twyst compares their movement to the reference model, scoring accuracy and providing corrective suggestions.

Twyst uses sensor fusion (Kalman filters) to combine gyroscope, accelerometer, and magnetometer data. Movement analysis and comparison are based on Principal Component Analysis (PCA) for segmentation and Bézier curve modeling for motion representation, ensuring precise yet efficient feedback.

## Related Work

Twyst draws inspiration from several existing systems:
- SlimeVR: Open-source IMU-based full-body tracker for VR; lacks exercise integration and suffers from drift.
- OptiTrack: High-precision optical tracking used in professional environments; too costly and complex for personal use.
- Oculus Insight: Inside-out tracking with 6DoF accuracy; limited to upper-body movement and headset constraints.

Twyst bridges the gap — delivering OptiTrack-like accuracy with SlimeVR’s affordability and Oculus’ simplicity, optimized for fitness and rehabilitation.

## Software Architecture

Mobile Application
- Built in SwiftUI (iOS), with an Android version in development.
- Features include:
- Exercise browsing and categorization.
- Live activity tracking and performance analytics.
- Gamified UI inspired by Duolingo, featuring progress visualization, rewards, and motivational feedback.
- Mascot: Twy — a friendly athletic fox serving as a motivational guide and branding symbol.

Embedded Software
- Runs on ESP32-C3 using the Arduino framework (C).
- Handles sensor communication (SPI/I²C), data fusion, calibration, and Bluetooth data transfer.
- Implements local Kalman filtering before aggregating data to the main bandana and mobile app for analysis.

## Hardware Design

Bandana Types
- Main Bandana: Acts as the master node; equipped with a touchscreen, pulse oximeter, and temperature sensor.
- Secondary Bandanas: Smaller, lightweight, and communicate with the main unit via UWB and Bluetooth.

## Components

Component	Model / Description
Microcontroller	ESP32-C3
IMU	MPU9250
UWB Module	Ai-Thinker BU03 DW3000
Display	Waveshare Round TFT (GC9A01 driver)
Pulse Oximeter	GY-MAX30100
Temperature Sensor	MF52
Battery	Li-Po with Boost Regulator HW626
Material	PETG 3D-printed enclosures, nylon straps


## Electronics & Prototyping
- Designed using KiCad for PCB schematics.
- 3D-printed casings optimized for comfort and modular assembly.
- Built for durability, skin safety, and easy debugging.

## Business Model

Twyst’s business strategy focuses on:
- Selling hardware kits (bandanas + mobile app).
- Generating secondary revenue from anonymized motion data used in research, medicine, and biomechanics.
- Promoting accessibility and personalization to encourage wide adoption across fitness, rehabilitation, and research markets.

Business Plan
Research Paper

## Research & Algorithms

Twyst’s research focuses on mathematical modeling for accurate motion comparison:
- Sensor Model: Quaternion-based orientation estimation via Kalman filtering.
- Segmentation: PCA identifies repetitions and removes noise.
- Motion Representation: Bézier curves smooth motion data for scalable comparison.
- Evaluation Metrics: Curve distance, amplitude, and phase alignment define feedback precision.

These techniques ensure low drift, real-time responsiveness, and robust cross-user comparison.

## License

This project is currently in research and prototype stage under educational use. Future licensing will be determined upon commercial release.
 presentation)?