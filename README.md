# Virtual Mouse & Gesture Control System

A real-time human-computer interaction system that allows mouse and
selected system controls using hand gestures, voice commands, and eye
tracking.

![Virtual Mouse Overview](assets/virtual-mouse-overview.png)

## Overview

The system uses a webcam to detect hand and facial landmarks and maps
recognized gestures, eye movements, and voice commands to mouse and
system actions.

The application provides three control modes:

1. Hand Gesture Mode
2. Gesture + Voice Mode
3. Eye Tracking Mode

## Features

### 1. Hand Gesture Mode

Uses webcam-based hand landmark detection to control the mouse and
selected system functions.

- Cursor movement using hand position
- Left click
- Right click
- Double click
- Drag and drop
- Scrolling
- Volume control
- Brightness control

### 2. Gesture + Voice Mode

Combines hand gestures with voice commands for additional control.

Supported commands include:

- Left click
- Right click
- Double click
- Scroll up
- Scroll down
- Increase volume
- Decrease volume

### 3. Eye Tracking Mode

Uses facial and iris landmarks to provide an alternative method of
controlling the cursor.

- Cursor movement using eye position
- Blink-based clicking

## How It Works

The application starts with a mode-selection interface.

```text
                    Mode Selector
                         |
             +-----------+-----------+
             |           |           |
             v           v           v
         Gesture    Gesture + Voice  Eye
             |           |           |
             +-----------+-----------+
                         |
                 Landmark Detection
                         |
                 Gesture / Eye State
                         |
                   Action Mapping
                         |
                         v
                  OS-level Control
