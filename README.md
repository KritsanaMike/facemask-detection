# facemask-detection
Imagery Analysis for Mask Detection Develop with YOLOv5 using Deep Learning to detect facemask and identify type of mask in 5 class. 
- Surgical
- N95
- Homemade
- Incorrect
- No_mask

## Dataset
- Real facemask images from internet 1108 images
- Augmentation facemask images base on dataset form https://gtanisik.github.io/projects/hii.html and using MaskTheFace technique https://github.com/aqeelanwar/MaskTheFace to make new facemask images.

Example Real images

![realmask2](https://github.com/KritsanaMike/facemask-detection/blob/f2f5647c230cc2f4d508ef4d12ec76228b9b3714/Example%20Images/realmask2.png)

Example Augmentation images

![Picture1](https://github.com/KritsanaMike/facemask-detection/blob/36c7974a7b78ec583d5b627dffbbe11c0521f4fd/Example%20Images/Picture1.png)

## Install
Clone repo and install requirements.txt in a Python>=3.6.0 environment, including PyTorch>=1.7.
```
git clone https://github.com/KritsanaMike/facemask-detection.git #clone project
cd facemask-detection
pip install -r requirement.txt #install library
```
## Training
1. Before trainig we have to create the new derectory in foder "data" to put the dataset
```
|- data
    |-- dataset
        |-- images
             |-- train
             |-- test
             |-- val
        |-- labels
             |-- train
             |-- test
             |-- val
 ```
 2. Train model follow command below. In this project we use facmask.yaml to call dataset ans train on yolov5s. And use weight from best training. Batch sizes is 16 and images sizes is 640 px 
 ```
python train.py --data facemask.yaml --cfg yolov5s.yaml --weights 'runs/train/50epoch_real_image_model_s/weights/best.pt' --batch-size 16 --img 640
                                           
 ```
 3. After finished trainig the model we will get the new weight in train folder. and result from trining such as confusion_matrix, precision, recall graph etc.
<img width="720" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/e43e1248905a55c13193d17fcdd37e866f30f0ed/Example%20Images/weight.PNG">

<img width="720" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/bf60af9d32b3776b469762cefb2dda44f8352347/runs/train/50epoch_real_image_model_s/confusion_matrix.png">

<img width="720" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/bf60af9d32b3776b469762cefb2dda44f8352347/runs/train/50epoch_real_image_model_s/P_curve.png">

<img width="720" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/bf60af9d32b3776b469762cefb2dda44f8352347/runs/train/50epoch_real_image_model_s/R_curve.png">
 
