# Cancer Instance Segmentation and Classification Project

This project aims to perform instance segmentation and classification on cancer datasets. The dataset used in this project is from Kaggle and can be found [here](https://www.kaggle.com/datasets/andrewmvd/cancer-instance-segmentation-and-classification-3).

## Dataset Description

The dataset consists of images of cancer cells with corresponding segmentation masks. The goal is to classify and segment these cells to assist in cancer detection and research.

## Dataset Conversion Process

### 1. Converting Annotations to Binary
The dataset initially contains image annotations that are not in YOLO format. The first step is to convert these annotations to a binary mask format. This is done by processing the instance segmentation masks provided in the dataset.

### 2. Converting Binary to COCO Format
After converting the annotations to binary masks, the next step is to convert these masks into the COCO format. The COCO format is a common format for object detection tasks, and it is required to make the dataset compatible with YOLO.

The process involves:
- Creating bounding boxes for each segmented region.
- Storing these boxes along with their class labels in a COCO-compliant JSON format.

### 3. Converting COCO to YAML for YOLO
Finally, to use the dataset for training a YOLO model, the COCO format is further converted into YOLO's format, which uses a YAML configuration file. This YAML file defines the training and validation dataset paths and the number of classes.

Below is an example of the YAML configuration:

```yaml
train: /path/to/train/images
val: /path/to/val/images

nc: 6  # number of classes
names: ['c1','c2','c3','c4','c5','c6']
``` 
## Training the Model

The model was trained using YOLO for 20 epochs, which is a relatively small number of training iterations.
For improved accuracy and better results, it is recommended to train the model for a higher number of epochs (e.g., 100-200 epochs).
This will allow the model to learn the dataset more thoroughly and improve its performance on segmentation and classification tasks.

