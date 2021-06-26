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
    └── data.yaml 
 
Run the command

 ```
# Train yolov5 on our dataset
$python train.py --batch 16 --epoch 5 --data data.yaml --weights yolov5s.pt
```
 
 
 
 
 
 
 
 
 
 
 
 
 
