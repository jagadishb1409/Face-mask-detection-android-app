# Face-mask-detection-android-app

Real time face detection using Yolov5 deployed on android


## Dataset preparation 

You can get dataset from kaggle competition [Face Mask Detection](https://www.kaggle.com/andrewmvd/face-mask-detection).
This dataset contains Images and Annotation folder, which we convert to YOLOV5 required form.

The format of annotation required is:

```
<class> <x> <y> <width> <height>
ex 0 2.0 12.0 240 320
```
We convert xml files to text files. Then we can split the dataset into Train, Test, Val

Create Folders as shown below

    
    Images
    ├── Train
    ├── Test
    └──  Val
    
    Annotations
    ├── Train
    ├── Test
    └──  Val


Then change the directories path in pre proess data.py and run the file.

## Train the model

Lets start by cloning yolov5 and installing requirements 

```
$git clone https://github.com/ultralytics/yolov5
$pip install -r requirements.txt
```

Create a data.yaml file and change the path, nc (number of classes) and names 

Organize Directories as shown below

    Project
    ├── yolov5
    ├── Train
        ├── images
        ├── labels
    ├── Test
        ├── images
        ├── labels
    ├── Val
        ├── images
        ├── labels
    ├── mask_yolovs.yaml
    └── data.yaml 
 
Run the command

 ```
# Train yolov5 on our dataset
$python yolov5/train.py --batch 16 --epoch 5 --data data.yaml --cfg mask_yolov5s.yaml --weights yolov5s.pt --name masks_yolov5_result
```
 
 Test the model on single image
 ```
 $cd yolov5
 $python detect.py --source test.png --weights runs/train/mask_yolov5_result/weights/best.pt
 ```
 
 Export ptl file for android app run export.py
 
 Before running the code edit export.py line 80 '.torchscript.pt' to '.torchscript.ptl
 ```
 $python export.py --weights runs/train/mask_yolov5_result/weights/best.pt --batch 1
 ```
 
 ## Android app
 
 Create a classes.txt file and write down the class name in newline
 
 Go to this directory 
 
 "\ObjectDetection\app\src\main\assets"
 
 Add your .ptl and txt files and build the app in android studio
 
 
 
 
 
 
 
 
