# TensorFlow_Lite_Face_Mask_Jetson-Nano
![output image]( https://qengineering.eu/images/Mask_2_Jetson.jpg )<br/>
## TensorFlow Lite Posenet running on a Jetson Nano
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/><br/>
A fast C++ implementation of TensorFlow Lite Face Mask detector on a Jetson Nano.<br/>
Once overclocked to 2015 MHz, the app runs at 14 FPS.<br/>
You could call this Face Mask detection ___2.0___.
The network used is a re-trained MobileNet V1 SSD. It has three classes: no maks, a mask, and wearing a mask incorrectly.<br/>
Although the latter category is not very convincing, given the small size of training samples.<br/>
It's not the usual cascade of the two deep learning models, one face recognition and a second one that detects the masks.<br/>
This one model now recognizes not only the white masks, but also the black, colored and fancy masks.<br/> 
Although it can detect more faces/masks in the same scene, the best result is still one face in front of the camera.<br/>

## Benchmark.
| Model | CPU 2015 MHz | CPU 1479 MHz | RPi 4 64os 1950 MHz |
|  :------------: |  :------------: | :-------------: | :-------------: |
| ssd_mobilenet_v2.tflite | 14.0 FPS | 11.4 FPS | 8.57 FPS |
| ssd_mobilenet_v2_fpnlite.tflite |  10.8 FPS | 8.5 FPS | 6.4 FPS |


Special made for a Jetson Nano see [Q-engineering deep learning examples](https://qengineering.eu/deep-learning-examples-on-raspberry-32-64-os.html) <br/>
<br/>
## Dependencies.
To run the application, you have to:
- TensorFlow Lite framework installed. [Install TensorFlow Lite](https://qengineering.eu/install-tensorflow-2-lite-on-jetson-nano.html) <br/>
- Optional OpenCV installed. [Install OpenCV 4.5](https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html) <br/>
- Code::Blocks installed. (```$ sudo apt-get install codeblocks```)
## Running the app.
To extract and run the network in Code::Blocks <br/>
$ mkdir *MyDir* <br/>
$ cd *MyDir* <br/>
$ wget https://github.com/Qengineering/TensorFlow_Lite_Face_Mask_Jetson-Nano/archive/master.zip <br/>
$ unzip -j master.zip <br/>
Remove master.zip, LICENSE and README.md as they are no longer needed. <br/> 
$ rm master.zip <br/>
$ rm README.md <br/> <br/>
Your *MyDir* folder must now look like this: <br/> 
Face_Mask_Video.mp4 <br/>
ssd_mobilenet_v2_fpnlite.tflite - more accurate<br/>
ssd_mobilenet_v2.tflite - somewhat faster <br/>
TestTensorFlow_Lite_Mask.cpb <br/>
FaceMask.cpp <br/>
Kapje_x.jpg - examples<br/>
 <br/>
Run TestTensorFlow_Lite.cpb with Code::Blocks.<br/>
You may need to adapt the specified library locations in *TestTensorFlow_Lite.cpb* to match your directory structure.<br/><br/>

