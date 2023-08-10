# Aquarium Object Detection

This repository contains object detection models trained on the [aquarium dataset](https://public.roboflow.com/object-detection/aquarium/2) to identify various aquatic species and features.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architectures and Training](#model-architectures-and-training)
- [Additional Notebooks](#additional-notebooks)
- [Results and Observations](#results-and-observations)
- [Acknowledgments](#acknowledgments)

## Introduction
The goal of this project is to develop a robust object detection model tailored for aquatic environments. By identifying and categorizing various species and features, we aim to enhance marine research and observation.

## Dataset
The dataset utilized in this project is sourced from [Roboflow's Aquarium dataset](https://public.roboflow.com/object-detection/aquarium/2). It includes high-quality images of diverse aquatic life forms, each annotated for object detection tasks.

## Model Architectures and Training
Two distinct architectures have been employed for training:

1. **SSD MobileNet V2 FPNLite 320x320** - Training notebook: [train_0.ipynb](./train_0.ipynb)
2. **SSD ResNet50 V1 FPN 640x640** - Training notebook: [train_1.ipynb](./train_1.ipynb)

Both models were chosen for their balance between accuracy and computational efficiency, with the latter being especially suitable for real-time applications.

## Additional Notebooks
- **Setting up Object Detection API** - Notebook: [set_up_object_detection_api.ipynb](./set_up_object_detection_api.ipynb)
- **Applying Model on Videos** - Notebook: [apply_model_on_video.ipynb](./apply_model_on_video.ipynb)

## Results and Observations

For the models trained using different architectures, distinct observations were made:

### SSD ResNet50 V1 FPN 640x640 ([train_1.ipynb](./train_1.ipynb))
- The model frequently produces bounding boxes that are larger than required, encompassing more area than the actual entity.
- Recall values are consistently low across multiple Intersection over Union (IoU) thresholds. Adjusting the IoU doesn't lead to significant enhancements.
- The model faces challenges distinguishing between specific aquatic species.

### SSD MobileNet V2 FPNLite 320x320 ([train_0.ipynb](./train_0.ipynb))
- Recall values show an increasing trend as the Intersection over Union (IoU) threshold is increased, indicating a better alignment of predicted bounding boxes with ground truth at higher IoU thresholds.

These results provide insights into the strengths and weaknesses of each model, guiding potential improvements and adjustments.

## Acknowledgments
Special acknowledgment to [Roboflow](https://roboflow.com/) for generously providing the dataset and continuously supporting the machine learning community with premium data resources.

