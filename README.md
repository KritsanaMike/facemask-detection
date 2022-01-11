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
