# Training YOLOv4 on Custom Dataset

> This my attempt: how to train Yolo-V4 objection detection in Cloud(Colab)

#### Disclaimer
* This was only my attempt on how to train YOLOv4 on custom dataset(Not for getting high accuracy) 
* This is `NOT a Proper Guide` for training YOLO-v4
#### How-To
In order to create a custom YOLOv4 detector we will need the following:
* Labeled Custom Dataset
* Custom .cfg file
* obj.data and obj.names files
* train.txt file (test.txt is optional)

The Main steps:
* Create your own Dataset: Make sure that images and labels should be in same Directory. Then make a `zip` of that folder to make it easy to upload in Google drive.

* Upload to Cloud: Upload the zip file to Google Drive

* Open Colab(Enable GPU) & clone DarkNet
>!git clone https://github.com/AlexeyAB/darknet


* Configuring Files for Training
> GOTO: <https://github.com/AlexeyAB/darknet>

* Download Pre-Trained Weighs(YOLOv4)
> !wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.conv.137

* Train the Detector
> !./darknet detector train path/to/obj.data path/to/custom path/to/config.cfg yolov4.conv.137 -dont_show

* Run The custom Detector
> !./darknet detector test obj.data yolov4.cfg yolov4_trained.weights img.jpg 
    
#### Dataset
Kaggle Dataset: <https://www.kaggle.com/yadola/league-of-legends-champion-minimap-dataset?select=yolov3_LoL_champions.weights> (Dataset for YOLOv3 but I used it for YOLOv4)

* I have only trained the model for 2000 epoch, which have an Avg Loss of 0.3 (which is high)

#### My Gain from this Repo
Helped To know
* How to train YOLO on custom dataset
* How to use Google Colab
* handling Data in cloud(Google drive)
* Importance of Shell commands