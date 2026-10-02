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
The proposed pipeline includes:

Security-Camera Video → Vehicle Detection → Vehicle Tracking →
License Plate Detection → Best-Frame Selection → Image Enhancement →
OCR → Evidence Summary

Proposed technologies include:
- YOLO
- ByteTrack
- OpenCV
- EasyOCR or PaddleOCR
- Python / PyTorch
- Google Colab

## Data Plan
**Primary dataset:** UFPR-ALPR

- 4,500 annotated images
- 150 vehicles
- 1920 × 1080 resolution
- Vehicle, license plate, and character annotations
- Dataset access requested

A small number of security-camera video samples will also be used to test the
complete application in realistic conditions.

## Success Metrics
- License Plate Detection: target ≥ 0.70 mAP@50
- OCR Accuracy: target ≥ 70% on readable plates
- Usable Plate Frame: target ≥ 80% of detected vehicles produce at least one
  usable plate frame

## Milestone Plan
- Week 10 — Blueprint
- Week 11 — First Working Demo
- Weeks 12–13 — Make It Yours
- Week 14 — Improve & Measure
- Week 15 — Package & Present

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
- Compute: Google Colab
- Estimated Cost: $0
- Models/Tools: YOLO, ByteTrack, OpenCV, OCR
- Dataset: UFPR-ALPR — access requested

## AI Usage
AI-assisted work is documented in:

`docs/AI_usage_log.md`
