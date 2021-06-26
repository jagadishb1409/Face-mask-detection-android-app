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

Create Folders 

    
    Images
    ├── Train
    ├── Test
    └──  Val
    
    Annotations
    ├── Train
    ├── Test
    └──  Val


## Quick start

Lets start by cloning yolov5 and installing requirements 

```
$git clone https://github.com/ultralytics/yolov5
$cd yolov5
$pip install -r requirements.txt
```

