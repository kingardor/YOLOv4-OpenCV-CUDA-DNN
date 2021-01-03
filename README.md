# YOLOv4 OpenCV DNN

Run YOLOv4 directly with OpenCV using the DNN module.

![<span>Photo by <a href="https://unsplash.com/@christopher__burns?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Christopher Burns</a> on <a href="https://unsplash.com/s/photos/people?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>](resources/cover.jpg)

## Index

1. [Clone the repository](#Clone-the-repository)
2. [Install pip packages](#Install-pip-packages)
3. [Run the code](#Run-the-code)

## Clone the repository

This is a straightforward step, however, if you are new to git or git-lfs, I recommend glancing threw the steps.

First, install git and git-lfs

```sh
sudo apt install git git-lfs
```

Next, clone the repository

```sh
# Using HTTPS
git clone https://github.com/aj-ames/YOLOv4-OpenCV-DNN.git
# Using SSH
git clone git@github.com:aj-ames/YOLOv4-OpenCV-DNN.git
```

Finally, enable lfs and pull the yolo weights

```sh
git lfs install
git lfs pull
```

## Install pip packages

First, we need to install python dependencies. Make sure you have a working build of python3.7/3.8

```sh
sudo apt install python3-dev python3-pip
```

The dependencies needed are the following:

```sh
numpy==1.19.4
opencv-contrib-python==4.5.1.48
opencv-python==4.5.1.48
```

You can either install them with pip command or use the requirements.txt file.

```sh
# For individial packages
pip3 install <packagename>

# For requirements.txt
pip3 install -r requirements.txt
```

## Running the code

The code supports a number of command line arguments. Use help to see all supported arguments

```sh
❯ python3 dnn_inference.py --help

usage: dnn_inference.py [-h] [--image IMAGE] [--stream STREAM] [--cfg CFG] [--weights WEIGHTS] [--namesfile NAMESFILE] [--input_size INPUT_SIZE]

Object Detection using YOLOv4 and OpenCV4

optional arguments:
  -h, --help            show this help message and exit
  --image IMAGE         Path to use images
  --stream STREAM       Path to use video stream
  --cfg CFG             Path to cfg to use
  --weights WEIGHTS     Path to weights to use
  --namesfile NAMESFILE
                        Path to names to use
  --input_size INPUT_SIZE
                        Input size
```

To pass an image, run the script in the following way:

```sh
python3 dnn_infernece.py --image images/example.jpg
```

To run a stream, run the script this way:

```sh
# Video
python3 dnn_inference.py --stream video.mp4

# RTSP
python3 dnn_inference.py --stream rtsp://192.168.1.1:554/stream

# Webcam
python3 dnn_inference.py --stream webcam
```
