# Smart Parking System with YOLO and Jetson Nano

This project implements a smart parking system using a YOLO model to detect cars and determine the availability of parking slots in a live or recorded video feed. The system includes a graphical user interface (GUI) created using Tkinter and is optimized to run efficiently on a Jetson Nano device with CUDA support.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [How It Works](#how-it-works)
  - [Step 1: Capture Parking Lot](#step-1-capture-parking-lot)
  - [Step 2: Identify Coordinates](#step-2-identify-coordinates)
  - [Step 3: Load YOLO Model](#step-3-load-yolo-model)
  - [Step 4: Test the System](#step-4-test-the-system)
- [Jetson Nano Optimization](#jetson-nano-optimization)
- [Model Performance](#model-performance)
  - [Metrics](#metrics)
- [Challenges and Solutions](#challenges-and-solutions)
- [Installation](#installation)
- [Usage](#usage)
- [Demo](#demo)
- [License](#license)

---

## Overview

The Smart Parking System leverages object detection to identify cars and determine their position within predefined parking lot coordinates. By integrating bounding box predictions with polygon testing, the system tracks parking slot availability in real time.

---

## Features

- YOLO-based object detection.
- Tkinter GUI for an interactive user experience.
- Compatibility with live camera feeds and recorded videos.
- Integration with Jetson Nano for optimized performance.
- CUDA support for faster computation on GPU-enabled devices.

---

## How It Works

### Step 1: Capture Parking Lot
The system allows the user to capture parking lot images either from a live camera or a recorded video. 

### Step 2: Identify Coordinates
Using the captured image, the user can define the coordinates of each parking slot. This step ensures accurate parking slot identification during detection.

### Step 3: Load YOLO Model
The user loads a pre-trained YOLO model for car detection.

### Step 4: Test the System
The system predicts parking slot availability in real time by testing on a live feed or recorded video. Occupied slots are highlighted in red, and free slots remain unmarked.

---

## Jetson Nano Optimization

The system is optimized for the Jetson Nano by:
1. Enabling CUDA support for GPU acceleration.
2. Downsizing images and frames to reduce computational overhead.

---

## Model Performance

### Metrics
- **Car Detection Accuracy**: 95%
- **Free Slot Detection Accuracy**: 91%
- **Background Detection Accuracy**: 63%

The confusion matrix and performance metrics, including precision-recall curves and F1 score, provide insights into the model's capabilities. Optimal performance was achieved at a confidence threshold of **0.469**, with an F1 score of **0.88**.

---

## Challenges and Solutions

1. **Computational Resource Limitations**:
   - Solution: Trained the YOLO model on a workstation and used pre-trained weights for the Jetson Nano.

2. **Package Compatibility Issues**:
   - Solution: Adjusted Python and package versions to meet Jetson Nano's CUDA requirements.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/smart-parking-system.git
   cd smart-parking-system
