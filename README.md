Tech Stack:

Frontend:

OpenCV: Captures real-time video from a webcam and handles frame processing and visualization of detections.

Backend:

Ultralytics YOLOv11: The deep learning framework used for training and inference of the action detection model.

Roboflow: Used for dataset preparation, annotation, and export in YOLO format.

NumPy: For array and image data manipulation during preprocessing and inference.

Application Workflow:

Data Handling:

A custom dataset of 2,500 images was created from scratch as no public action-specific sign language dataset was available.

Images were collected for different sign actions, covering various lighting conditions and backgrounds.

All images were manually annotated using Roboflow, with bounding boxes drawn around the hand and gesture regions, and labels assigned according to the specific action.

The dataset was split into training, validation, and testing sets in YOLO format.

Model Architecture:

Based on YOLOv11, a state-of-the-art object detection model optimized for real-time inference.

Pretrained weights (YOLOv11n) were fine-tuned on the custom action dataset to adapt the model to recognize sign language gestures.

The model predicts bounding box coordinates, confidence scores, and action class labels directly from input frames.

Training:

Model training was performed using the Ultralytics YOLO training API for 50 epochs with an image size of 640×640.

Data augmentation techniques such as flipping, scaling, and brightness adjustments were applied to improve robustness.

The Adam optimizer and default YOLO loss functions were used for bounding box regression and classification.

Real-time Action Detection:

The trained model is deployed with OpenCV for webcam-based live detection.

Each frame from the video feed is resized, passed to the YOLO model, and predictions (bounding boxes + labels) are drawn on the output.

The system displays detected sign actions in real time with minimal latency.

Model Used:

YOLOv11 (You Only Look Once v11): A fast and accurate object detection model capable of identifying multiple sign actions in a single frame. Fine-tuned specifically for sign language action recognition using the custom dataset.

Potential Applications:

Assistive communication tools: Helping deaf or hard-of-hearing individuals communicate via real-time action recognition.

Interactive learning systems: Teaching sign language through real-time feedback on performed gestures.

Human-computer interaction: Enabling gesture-based control for applications and devices.

This system demonstrates a high-speed, real-time approach to sign language action recognition and can be extended for multi-class gesture detection, integration with translation systems, or combined with NLP for complete sign-to-speech conversion.

![WhatsApp Image 2025-08-14 at 10 28 00](https://github.com/user-attachments/assets/bd2b0d51-7c53-41d7-9e19-63a8573f761e)

