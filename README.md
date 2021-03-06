# License Plate Detection

## Introduction
This repository can be used to detect the registration number of vehicles in robust scenarios. 
**It uses YOLOv3 for vehicle detection, FAST-YOLOv3 for license plate detection and a CNN for character recognition.**

## Requirements
This project uses AlexyAB's darknet framework. The Darknet framework is self-contained in the "darknet" folder
and must be compiled before running the tests. To build Darknet just type "make" in "darknet" folder:

```shellscript
$ cd darknet && make
```

if you wish to use GPU you can use Makefile in GPU folder inside the darknet folder or you can make necessary changes in Makefile.

**This code was tested in an Ubuntu 18.04.4 LTS machine with Python 3.6.9 and Opencv 3.4.9**

## Download models
Run the following shell script to download the network.
```shellscript
$ bash get-networks.sh
```

## Running on images
Use script run.sh to run LPD on images. It requires 3 arguments:
* __Input directory (-i):__ should contain at least 1 image in JPG or PNG format;
* __Output directory (-o):__ will be used to store temporary and final results.
* __CSV file (-c):__ will save License plate information of each image.

**Example**
```shellscript
$ bash run.sh -i  samples/input -o  samples/output -c samples/output/result.csv
```

## Running on Video
Use script video.sh to run LPD on videos. It requires 3 arguments:
* __Input path (-i):__ Path to video file;
* __Output directory (-o):__ Will be used to save the output video.
* __CSV file (-c):__ will save License plate information of each frame.

**Example**
```shellscript
bash video.sh  -i samples/video/test.mp4 -o samples/output -c samples/output/result.csv
```
## Runnig on webcam
Use webcam.sh script to run LPD on webcam.

**Example**
```shellscript
$ bash webcam.sh
```

## Using OpenCV with multiple threads
Use mthread.py script to run LPD using OpenCV. It will use OpenCV's dnn module. It require one argument if you wish to process video file other no argument to use webcam.

**For video**
```shellscript
$ python mthread.py --video samples/video/test.mp4
```
**For webcam**
```shellscript
$ python mthread.py
```


## Results
![Exmaple result](/output.png)



## References
1. https://github.com/AlexeyAB/darknet
