# PlateVision Midterm Blueprint
Midterm Project Computer Vision

## Team Members
- Camila Ferreira da Silva
- Kim Nguyen
- Faizan Razzaq
- Rida Kashan
- Oman Malek

## Project Tier
**Tier 2 — Advanced**

PlateVision is a Tier 2 project because it combines multiple computer vision
components, including object detection, vehicle tracking, image processing,
and OCR.

## Problem Statement
Security-camera footage may contain useful vehicle and license plate evidence,
but manually reviewing many video frames to find the clearest view can be
time-consuming and difficult.

PlateVision was inspired by a real situation in which security-camera footage
captured a vehicle of interest, but locating a clear view of the license plate
across the video frames was difficult.

## Solution Overview
PlateVision is an AI-assisted application that analyzes security-camera footage
to locate vehicles and license plates, select the clearest available plate
frames, and organize the results for human review.

The system is designed as an evidence-assistance tool rather than a system that
guarantees vehicle identification.

## Technical Approach

The proposed final pipeline includes:

Security-Camera Video → Vehicle Detection → Vehicle Tracking → License Plate Detection → Best-Frame Selection → Image Enhancement → OCR → Evidence Summary

**Selected technologies:**

- **Vehicle Detection:** YOLOv8 pretrained on COCO, selected for its ability to detect common vehicle classes without initial training.
- **License Plate Detection:** YOLOv8 with plate-specific weights, selected for bounding-box localization. The weights will be selected and evaluated during development.
- **Vehicle Tracking:** ByteTrack, used to associate vehicle detections across video frames.
- **Image Processing:** OpenCV, used for frame extraction, enhancement, and best-frame selection.
- **OCR:** EasyOCR, selected to extract candidate plate characters for human verification.
- **Framework:** Python and PyTorch.
- **Development Environment:** Google Colab.

**First Working Demo:**

The initial prototype will focus on a simplified pipeline:

Video Input → License Plate Detection → Bounding Box Output

Vehicle tracking, best-frame selection, enhancement, and OCR will be integrated after the basic detection pipeline is working.


## Data Plan
**Primary dataset:** UFPR-ALPR

- 4,500 annotated images
- 150 vehicles
- 1920 × 1080 resolution
- Vehicle, license plate, and character annotations
- Dataset access requested

A small number of security-camera video samples will also be used to test the
complete application in realistic conditions.

**Backup dataset:** [Kaggle — License Plate Detection Dataset](https://www.kaggle.com/datasets/barkataliarbab/license-plate-detection-dataset-10125-images)

Available on Drive: https://drive.google.com/file/d/12IZLoBxhzAEO9SBdvU4Q0lsSPQ3jDGoe/view?usp=sharing 

- Approximately 10,125 images
- YOLO-format license plate bounding-box annotations
- Downloaded locally
- Intended for plate detection training and evaluation if UFPR-ALPR access is delayed
- OCR evaluation will require separate character-level ground truth


Additional dataset documentation is available in `data/README.md`.

## Success Metrics
- License Plate Detection: target ≥ 0.70 mAP@50
- OCR Accuracy: target ≥ 70% on readable plates
- Usable Plate Frame: target ≥ 80% of detected vehicles produce at least one
  usable plate frame

## Milestone Plan

- **Week 10 — Blueprint:** Finalize the project scope, datasets, technical approach, and success metrics.
- **Week 11 — First Working Demo:** Process a sample video and display detected license plate bounding boxes.
- **Weeks 12–13 — Make It Yours:** Integrate vehicle detection, ByteTrack tracking, best-frame selection, image enhancement, and EasyOCR.
- **Week 14 — Improve & Measure:** Evaluate detection and OCR performance, analyze errors, and document limitations.
- **Week 15 — Package & Present:** Finalize the application, documentation, demonstration, and presentation.


## Risks and Plan B

### Risk 1 — Poor Video Quality
License plates may be too small, blurry, dark, or partially visible.

**Plan B:** Focus on vehicle detection, tracking, and best-frame selection.
Unreadable plates will be flagged rather than forcing an OCR result.

### Risk 2 — Inconsistent OCR Results
OCR may produce different plate readings across video frames.

**Plan B:** Compare OCR results from multiple high-quality frames and present
the best candidate with confidence information for human verification.

## Resources
- **Compute:** Google Colab
- **Estimated Cost:** $0
- **Models/Tools:** YOLOv8, ByteTrack, OpenCV, EasyOCR, Python, PyTorch
- **Primary Dataset:** UFPR-ALPR — access requested
- **Backup Dataset:** Kaggle License Plate Detection Dataset — downloaded locally


## AI Usage
AI-assisted work is documented in:

`docs/AI_usage_log.md`
