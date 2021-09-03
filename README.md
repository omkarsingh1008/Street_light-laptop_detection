# Street_light-laptop_detection

the aim of the is to detect a street light and laptop from image/video

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

for training yolov5 you have to three file 
1. data.yaml:- data related information
2. yolov5m.yaml:- it's a configuration file
3. (optional) yolov5m.pt:- it's weight file

yolov5m.pt file is used for transfer learning.

I train a model on 300 epochs and the batch size is 2
