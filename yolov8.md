
# YOLOv8 Object Detection on Custom Dataset

This guide will help you train a YOLOv8 object detection model on your custom dataset using Google Colab.

### Requirements
1. **Google Colab** with GPU enabled.
2. **Roboflow** for dataset management.
3. **Ultralytics YOLOv8** for model training.

### Steps to Train YOLOv8 on Custom Dataset

#### 1. Setup Google Colab
- Open Google Colab and ensure the GPU is enabled.
    - Go to `Runtime > Change runtime type` and select `GPU`.

#### 2. Install Required Libraries
Run the following commands to install the necessary libraries:

```bash
!pip install ultralytics
!pip install roboflow
```

#### 3. Get Dataset from Roboflow
- Go to [Roboflow](https://roboflow.com/), sign up or log in.
- Upload your dataset and create a project (for example, "sign-language").
- Export the dataset for YOLO format and get the dataset's YAML file.

#### 4. Load the Dataset in Colab
Upload the dataset YAML file from Roboflow to your Google Colab environment.
or just used credential provide by roboflow to upload dataset 

#### 5. Train the YOLOv8 Model
Use the following command to start training:

```bash
!yolo task=detect mode=train model=yolov8n.pt data=/content/sign-languagee-7/data.yaml epochs=5 imgsz=640
```

- `task=detect` - This is for object detection.
- `mode=train` - This sets the mode to training.
- `model=yolov8n.pt` - Specifies the base YOLOv8 model (YOLOv8 nano).
- `data=/content/sign-languagee-7/data.yaml` - Path to your dataset YAML file.
- `epochs=5` - Number of training epochs.
- `imgsz=640` - Image size for training (adjust as needed).

#### 6. Output
- Once the training is done, a folder named `runs` will be created. Inside the `runs` folder, you'll find a subfolder named `detect`(task), containing everything you need, including model weights, training logs, and more.
