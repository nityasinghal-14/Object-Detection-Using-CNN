# Hybrid Object Detection using MobileNet and YOLO

This project demonstrates a hybrid approach to object detection by combining MobileNet for feature extraction and object detection with YOLO for refining bounding boxes. The code is implemented in Python and uses TensorFlow Hub, OpenCV, and the Ultralytics YOLO library.

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Example Output](#example-output)
- [License](#license)

## Overview
The objective of this project is to leverage the strengths of both MobileNet and YOLO:
- **MobileNet**: Performs object detection and generates bounding boxes with associated classes and scores.
- **YOLO**: Refines the bounding boxes within the regions of interest (ROIs) identified by MobileNet.

The result is a robust object detection system capable of detecting and refining object boundaries effectively.

## Prerequisites
- Python 3.7+
- TensorFlow and TensorFlow Hub
- Ultralytics YOLO library
- OpenCV
- NumPy
- Matplotlib

## Installation
1. Clone the repository or download the script.
2. Install the required Python packages:
   ```bash
   pip install tensorflow tensorflow-hub ultralytics opencv-python-headless matplotlib numpy
   ```
3. Download the YOLO model weights. Ensure the file is named `yolov5su.pt` and is available in your working directory.

## Usage
1. Prepare an image for detection (e.g., `aeroplane.jpg`) and place it in the working directory.
2. Run the script:
   ```bash
   python hybrid_object_detection.py
   ```
3. The result image with refined bounding boxes will be displayed using Matplotlib.

## Code Explanation

### Key Functions
- **`preprocess_image(image)`**: Resizes and normalizes the input image for MobileNet.
- **`detect_objects_mobilenet(image)`**: Uses MobileNet to detect objects and generate bounding boxes, classes, and scores.
- **`refine_boxes_with_yolo(image, boxes)`**: Takes the bounding boxes from MobileNet and refines them using YOLO.
- **`hybrid_object_detection(image)`**: Combines MobileNet and YOLO to detect and refine objects in the input image.

### Workflow
1. MobileNet processes the input image and outputs bounding boxes, classes, and scores.
2. High-confidence bounding boxes are passed to YOLO for refinement.
3. The refined bounding boxes are drawn on the original image for visualization.

## Example Output
Ensure your environment is set up correctly, and the example input image (e.g., `aeroplane.jpg`) is provided. The processed image will display refined bounding boxes around detected objects.
