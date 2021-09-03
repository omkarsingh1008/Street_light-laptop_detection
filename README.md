# Street_light-laptop_detection

the aim of the is to detect a street light and laptop from image/video
## demo
demo on video :- [laptop](https://drive.google.com/file/d/1JYJ8wWcUNEL9pzmpdizlTx14MEXPQVTU/view?usp=sharing) video link,[street_light](https://drive.google.com/file/d/1EjPp3LqrsLYLiYqILxYw3lFYk1WG8QsF/view?usp=sharing)video link.

demo on images:-
</div>
  <br>
  <div align="center">
    <a >
        <img src="https://github.com/omkarsingh1008/Street_light-laptop_detection/blob/main/frp-pole-500x500_jpg.rf.a4bbe158c139722c37a90bf2b42a9f43.jpg" width="50%"/>
    </a>
    <img width="50%" />
    <a >
        <img src="https://github.com/omkarsingh1008/Street_light-laptop_detection/blob/main/young-attractive-man-sitting-on-260nw-1105215596_jpg.rf.082b88b3f994f2b030dd558c3b3c999c.jpg" width="50%"/>
    </a>
    <img width="50%" />
    </div>

## data collection

I used web scraping for data collection.

install beualtfull soup

```bash
pip install bs4
```
And i also create one script which can extract images from websites.

the size of dataset is 150 per label

## data annotaions

for data annotations. I use LabelImg
After using a tool LabelImg to label your images, export your labels to YOLO format, with one *.txt file per image (if no objects in image, no *.txt file is required). The *.txt file specifications are:

* One row per object
* Each row is class x_center y_center width height format.
* Box coordinates must be in normalized xywh format (from 0 - 1). If your boxes are in pixels, divide x_center and width by image width, and y_center and height by image height.
* Class numbers are zero-indexed (start from 0).

## train

For training. I used yolov5m PyTorch. m instance for medium.
yolov5 have different model-like small, medium and large 

we need 3 files to train yolov5 model

1. data.yaml:- data related information
2. yolov5m.yaml:- it's a configuration file
3. (optional) yolov5m.pt:- it's weight file

yolov5m.pt file is used for transfer learning.

I train on 300 epochs and the batch size is 2

## reults

after 300 epoch we get 0.90 mAP (mean aevrage percision)

## setup 

setup on loacl machine.

Clone repo and install requirements.txt in a Python>=3.6.0 environment, including PyTorch>=1.7.
```bash
git clone https://github.com/omkarsingh1008/Street_light-laptop_detection.git
```
```bash
cd Street_light-laptop_detection
```

```bash
pip install -r requirements.txt
```
## demo
demo on video

```bash
python3 detect.py --weight best.pt --source video_path
```
demo on image
```bash
python3 detect.py --weight best.pt --source image_path
```

demo on webcam
```bash
python3 detect.py --weight best.pt --source 0
```
