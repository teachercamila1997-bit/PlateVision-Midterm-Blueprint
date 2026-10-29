# Data Plan

## Primary Dataset

We plan to use the UFPR-ALPR dataset.

Dataset information:

- Approximately 4,500 annotated images
- 150 vehicles
- Image resolution: 1920 × 1080
- Vehicle, license plate, and character annotations
- Dataset access has been requested

## Additional Testing Data

We will use a small number of security-camera video samples to test the complete PlateVision pipeline under realistic conditions.

Any personal or identifiable footage will remain private and will not be shared publicly in this repository.

## Dataset Link

UFPR-ALPR: https://web.inf.ufpr.br/vri/databases/ufpr-alpr/

## Backup Dataset — License Plate Detection

**Source:** Kaggle — License Plate Detection Dataset (10,125 Images)

**Original dataset reference:** Roboflow Universe — License Plate Recognition v11

**Status:** Downloaded; available locally.

**Dataset details:**

Total images: 10,125

Training: 7,057 images

Validation: 2,048 images

Testing: 1,020 images

Annotation format: YOLO

Classes: 1 (License_Plate)

License: CC BY 4.0, as declared in the downloaded dataset metadata.

**Purpose:**

This dataset will serve as a backup if access to UFPR-ALPR is delayed. Its annotated license plate images can support plate detection training, testing, and evaluation during the First Working Demo.

**Limitations:**

The dataset contains license plate bounding-box annotations, not verified plate-character transcriptions for OCR evaluation. OCR performance will require additional labeled data or separate evaluation.

Dataset files will be kept outside the public GitHub repository.
