## YOLO Object Detection Model on Vehicles Dataset
### Project Overview
This project involves training a YOLOv5 and Yolov8 model on Vehicle-OpenImages dataset from Roboflow. It also includes comparison of training results from YOLOv8 and YOLOv5 model and also the imapct of using a pre-trained 
model.
### Training Options
 - img : Size of image. The image is a square one. The original image is resized while maintaining the aspect ratio. The longer side of the image is resized to this number. The shorter side is padded with grey color.
 - batch: The batch size
 - epochs: Number of epochs to train for
 - data: Data YAML file that contains information about the dataset (path of images, labels)
 - workers: Number of CPU workers
 - cfg: Model architecture. There are 4 choices available: yolo5s.yaml, yolov5m.yaml, yolov5l.yaml, yolov5x.yaml. The size and complexity of these models increases in the ascending order and you can choose a model which suits the complexity of your object detection task. In case you want to work with a custom architecture, you will have to define a YAML file in the models folder specifying the network architecture.
 - weights: Pretrained weights you want to start training from. If you want to train from scratch, use --weights ' '
 - name: Various things about training such as train logs. Training weights would be stored in a folder named runs/train/name
 - hyp: YAML file that describes hyperparameter choices. For examples of how to define hyperparameters, see data/hyp.scratch.yaml. If unspecified, the file data/hyp.scratch.yaml is used.

### Data Config File
Details for the dataset you want to train your model on are defined by the data config YAML file. The following parameters have to be defined in a data config file:
 - train, test, and val: Locations of train, test, and validation images.
 - nc: Number of classes in the dataset.
 - names: Names of the classes in the dataset. The index of the classes in this list would be used as an identifier for the class names in the code.
