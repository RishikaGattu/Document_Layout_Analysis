# Document_Layout_Analysis
Project Objective
This project aims to develop a Document Layout Analysis System using Python and computer vision libraries. The system processes document images to identify layout components such as:

Text blocks

Tables

Images

It then extracts structural information to improve document understanding, organization, and digitization.

What is Document Layout Analysis Used For?
Document Layout Analysis helps in understanding document structure and extracting meaningful information. It enables:

Automated data extraction

Content organization

Document digitization (e.g., for forms, invoices, reports)

Benefits include:

Streamlined workflows

Enhanced searchability

Better accessibility across industries like finance, healthcare, and education

Key Algorithmic Steps
We used a YOLOv10 object detection model to identify layout components.

YOLO Object Detection:
Divides the image into a grid

Predicts bounding boxes and class probabilities

Uses a CNN-based deep learning backbone

Applies Non-Maximum Suppression (NMS) to remove redundant detections

Specific Algorithmic Components
Component	Description
Confidence Filtering	Detections with confidence < 0.2 are removed
IoU Filtering	Bounding boxes with IoU < 0.8 are discarded
Bounding Box Annotation	Draws rectangles around detected objects
Label Annotation	Adds class labels to detected regions

Approach
1. YOLOv10 Object Detection
YOLO (You Only Look Once) is a real-time object detection algorithm.

Single-stage Detection: Processes the entire image in one pass.

Anchor Boxes: Predefined boxes help detect varied shapes (e.g., text, tables, images).

Feature Pyramids: Captures features at multiple scales.

2. Bounding Box Regression
YOLO predicts bounding box coordinates for each detected component.

Refines location and size using regression techniques.

Essential for accurately detecting layout components like paragraphs, images, and tables.

3. Non-Maximum Suppression (NMS)
Eliminates overlapping bounding boxes.

Keeps only the most confident detection per object.

Tuned using:

conf = 0.2
iou = 0.8

4. IoU (Intersection over Union) Filtering
Measures overlap between predicted and actual bounding boxes.

Keeps only those with IoU ≥ 0.8 to ensure precise detection.

5. Confidence Thresholding
Filters out predictions with low confidence (< 0.2).

Ensures only reliable detections are annotated.

Results and Observations
The system effectively detects and annotates various layout components.

YOLOv10 offered a balance between speed and accuracy, making it well-suited for real-time applications.

Suitable for use cases such as automated data entry, digital archiving, and intelligent document processing.
