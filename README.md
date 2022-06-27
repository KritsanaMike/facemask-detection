# facemask-detection
Imagery analysis for mask detection developed with YOLOv5 to detect and identify different types of mask wearers: 
- surgical
- N95
- homemade
- incorrect warn
- no mask

## Dataset
- 1108 facemask images collected from the internet 
- augmentated facemask images based on dataset form https://gtanisik.github.io/projects/hii.html and using MaskTheFace technique https://github.com/aqeelanwar/MaskTheFace to create new images.

Example of the real images

<img width="720" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/f2f5647c230cc2f4d508ef4d12ec76228b9b3714/Example%20Images/realmask2.png">

Example of the augmented images

<img width="720" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/03ca3e8c25f25af2bcdff02e42a606f4733d6dc9/Example%20Images/augment.JPG">

## Install
Clone repo and install requirements.txt in a Python>=3.6.0 environment, including PyTorch>=1.7.
```
git clone https://github.com/KritsanaMike/facemask-detection.git #clone project
cd facemask-detection
pip install -r requirements.txt #install library
```
## Training
1. Label the dataset using Makesence.AI https://www.makesense.ai/ before training. Example images below.

<img width="520" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/2cfe63a9fce03868f3fc5c411f104be366892d55/Example%20Images/surgical.png">
<img width="520" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/2cfe63a9fce03868f3fc5c411f104be366892d55/Example%20Images/n95.png">
<img width="520" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/2cfe63a9fce03868f3fc5c411f104be366892d55/Example%20Images/homemade.png">
<img width="520" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/2cfe63a9fce03868f3fc5c411f104be366892d55/Example%20Images/incorrect.png">
<img width="520" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/2cfe63a9fce03868f3fc5c411f104be366892d55/Example%20Images/nomask.png">




2. Create the new derectory in foder "data" to put the dataset in
```
|- data
    |-- dataset
        |-- images
             |-- train
                |-- img01.jpg
                |-- img02.jpg
             |-- test
                |-- img03.jpg
             |-- val
                |-- img04.jpg
        |-- labels
             |-- train
                |-- img01.txt
                |-- img02.txt
             |-- test
                |-- img03.txt
             |-- val
                |-- img04.txt
 ```
3. Train the models by following the command below. In this project we use facmask.yaml to call dataset and train with yolov5s. The weight from the best training is used. Batch size is 16 and image size is 640 px. If you want to train with custom data, you can follow this documentation https://docs.ultralytics.com/tutorials/train-custom-datasets/
 ```
python train.py --epoch 50 --data facemask.yaml --cfg yolov5s.yaml --weights runs/train/50epoch_real_image_model_s/weights/best.pt --batch-size 16 --img 640
                                           
 ```
4. After finishing with the model training, we will get the new weight in the train folder. The result from training are confusion_matrix, precision, recall graph, etc.
<img width="640" alt="portfolio_view" src="https://github.com/KritsanaMike/facemask-detection/blob/e43e1248905a55c13193d17fcdd37e866f30f0ed/Example%20Images/weight.PNG">
