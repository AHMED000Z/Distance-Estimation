# 🧠 Stereo Object Distance Estimation using YOLO

This project provides a Python-based solution for estimating object distances using stereo image pairs and the YOLO object detection model. By comparing left and right eye images, the system calculates horizontal disparities and uses a geometric model to estimate real-world distances.

---

## 🚀 Features

- 🧭 **Stereo Image Inference** using YOLO for both left and right views.
- 🎯 **Object Detection** with bounding boxes, class labels, and segmentation masks.
- 🧮 **Geometric Calculations** including bounding box centers, corners, and areas.
- 📐 **Distance Metrics**: Calculates vertical/horizontal displacement, size differences, and object class penalties.
- 🔍 **Optimal Object Matching** using the Hungarian algorithm.
- 📏 **Distance Estimation** for specified objects based on disparity and triangulation geometry.

---

## 📦 Installation

Install the required packages:

```bash
pip install torch opencv-python numpy scipy ultralytics
Make sure your YOLO model is compatible with the ultralytics package.

distance = recognise_distance(
    "/path/to/left_image.jpg",
    "/path/to/right_image.jpg",
    "bottle"
)
print(f"Distance to bottle: {distance} cm")

# 📸 Assumptions
Stereo images are horizontally aligned.

The YOLO model is pre-trained or fine-tuned for your classes.

Focal length and stereo baseline are known or approximated.

📏 Camera Geometry Example
Modify based on your stereo setup:

python
Copy
Edit
fl = 30 - 37.9 * 50 / 68.2459
tantheta = (1 / (50 - fl)) * (7.05 / 2) * sz1 / 37.9
fl: effective focal length

tantheta: tangent of angle between cameras

sz1: image width in pixels
