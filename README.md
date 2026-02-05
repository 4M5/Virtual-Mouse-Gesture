# 🖱 Project Overview: Virtual Mouse & Gesture Control System

## Introduction
The **Virtual Mouse & Gesture Control System** is a human-computer interaction (HCI) project designed to replace or augment traditional input devices (mouse and keyboard) using computer vision and voice recognition. It allows users to control their computer interface completely hands-free or through intuitive hand movements, making it ideal for accessibility purposes or futuristic control interfaces.

## Key Features

### 🖐 1. Hand Gesture Mode (`Gesture Controller`)
Uses the webcam to track hand landmarks and map specific gestures to system actions.
- **Cursor Movement**: Tracks the index finger to move the mouse pointer.
- **Left Click**: "Pinch" gesture (Index finger + Thumb) or specifically mapped internal logic.
- **Right Click**: Two-finger gesture (Index + Middle finger).
- **Double Click**: Two fingers closed.
- **Scroll**: Pinch gesture with the minor hand (non-dominant).
- **System Controls**:
  - **Volume Control**: Pinch gesture with the major hand.
  - **Brightness Control**: Pinch gesture variations.

### 🎙 2. Voice & Gesture Mode
Combines the hand tracking capabilities with voice commands for a multimodal interface.
- **Supported Commands**:
  - "Right click", "Left click", "Double click"
  - "Scroll up", "Scroll down"
  - "Increase volume", "Decrease volume"

### 👁 3. Eye Tracking Mode (`Eye Controller`)
Enables mouse control implementation using facial landmark detection.
- **Cursor Movement**: Tracks the iris/center of the eye to move the mouse cursor.
- **Clicking**: Detects intentional blinks to trigger mouse clicks.
- **Calibration**: Includes basic dynamic calibration to map eye range to screen resolution.

## 🧠 Technology Stack
- **Language**: Python
- **Computer Vision**:
  - `OpenCV`: For image processing and camera feed handling.
  - `MediaPipe`: Google's framework for robust structural tracking (Hands, Face Mesh).
- **Automation**: `PyAutoGUI` (for controlling mouse/keyboard events).
- **Audio/Voice**: `SpeechRecognition` (Google Speech API), `pycaw` (Windows Audio Control).
- **GUI**: `CustomTkinter` (Modern UI for mode selection).

## ⚙ System Architecture
- **Entry Point**: `Final.py` serves as the main application hub, launching a Mode Selector GUI.
- **Processing**: Real-time frame analysis is performed to extract landmarks (Hand 21 points, Face mesh 468 points).
- **Mapping**: Relative distances between landmarks (e.g., thumb tip vs index tip) determine the state (Open, Closed, Pinch) which then triggers the corresponding OS-level event.
