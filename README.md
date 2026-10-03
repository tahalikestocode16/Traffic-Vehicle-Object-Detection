# Traffic-Vehicle-Object-Detection

A PyTorch-based object detection project for detecting and localizing vehicles and license plates in traffic images.

The project uses a dataset annotated in **YOLO format**, but the detection pipeline is implemented independently using **PyTorch and TorchVision**. The goal is to understand how modern object detection systems work rather than relying on a high-level YOLO training pipeline.

## Classes

The dataset contains 7 object classes:

* Car
* Number Plate
* Blur Number Plate
* Two Wheeler
* Auto
* Bus
* Truck

## Project Goals

This project focuses on understanding the complete object detection pipeline:

* Parsing YOLO-format annotations
* Converting normalized bounding boxes to pixel coordinates
* Building a custom PyTorch `Dataset`
* Handling variable numbers of objects per image
* Creating custom `DataLoader` batching
* Image transformations and augmentation
* Transfer learning
* Object detection model architecture
* Detection losses
* Training and validation
* Intersection over Union (IoU)
* Non-Maximum Suppression (NMS)
* Mean Average Precision (mAP)
* Model evaluation
* Image inference
* Video/webcam inference

## Dataset

Each image has a corresponding annotation file.

```text
image.jpg
image.txt
```

The annotation files use the YOLO format:

```text
class_id x_center y_center width height
```

The coordinates are normalized between `0` and `1`.

The project converts these annotations into the bounding-box format used by the PyTorch detection model:

```text
[x1, y1, x2, y2]
```

## Current Pipeline

```text
Traffic Images
      ↓
YOLO Annotation Files
      ↓
Custom PyTorch Dataset
      ↓
Bounding Box Conversion
      ↓
DataLoader
      ↓
Object Detection Model
      ↓
Training
      ↓
Validation
      ↓
IoU / NMS / mAP
      ↓
Inference
```

## Project Structure

```text
traffic-vehicle-object-detection/
│
├── program.py
├── README.md
├── requirements.txt
│
├── dataset/
│   ├── images/
│   └── labels/
│
└── ...
```

The project is currently being developed incrementally. `program.py` contains the current implementation while the data pipeline is being built and tested.

## Technologies

* Python
* PyTorch
* TorchVision
* PIL
* NumPy
* Matplotlib

## Learning Focus

This project is being developed with an emphasis on understanding the underlying concepts rather than simply using a pre-built detection training pipeline.

Important concepts covered include:

* Bounding boxes
* Coordinate systems
* Dataset design
* Batching variable-length targets
* Transfer learning
* Detection heads
* Classification and box regression
* IoU
* NMS
* Precision and recall
* mAP

## Status

**In development**

Current stage:

* [x] Dataset structure
* [x] YOLO annotation parsing
* [x] Bounding-box conversion
* [x] Custom PyTorch Dataset
* [x] Custom detection `collate_fn`
* [x] Image transformations
* [x] Detection model
* [x] Training pipeline
* [x] Validation
* [x] IoU and NMS
* [x] mAP evaluation
* [x] Inference
* [x] Webcam/video detection

## Why This Project?

The goal is to build a complete object detection pipeline from the dataset level through model training and evaluation, while understanding the major components involved in modern computer vision systems.

Unlike a simple high-level detector implementation, the project explicitly handles the dataset, targets, batching, training process, losses, and evaluation metrics.



Taha Ahmed
