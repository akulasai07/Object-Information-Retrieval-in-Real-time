# Object-Information-Retrieval-in-Real-time

### Abstract

According to the World Health Organization survey from 
2021, there are 1 billion people in the world who have 
moderate or severe distance vision impairment. The 
project's main objective is to develop an android 
application for object detection for the blind. This is 
implemented for the COCO dataset, which has 80 classes 
of objects that the user will probably utilize daily. Android 
Studio is used to make the app and the UI. The model is 
trained using TensorFlow and converted into TensorFlow 
Lite. The project is carried out using a camera device on 
the client's side that records live video, converts it into 
frames, detects the objects and it's position and gives 
audio output.

### Dataset 

https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset

Common Objects in Context (COCO) is a 
high-quality dataset primarily used in neural 
networks.
COCO has several features:
- 328K images (>200K labeled)
- 1.5 million object instances
- 80 object categories

### Methodology

1. The user opens the android application built 
using Android Studio and accesses the camera 
to detect the object in real-time. 
2. The model converts the real-time video and 
divides it into a series of frames. 
3. Now using the ssd_mobilenet_v2_quantized 
model, the objects are detected in the frames, 
if there are any, and classified into different 
classes available in the COCO dataset; if no 
object is found, the process keeps on running 
until it finds the object. 
4. The detected label of an object with a spatial 
location is converted to speech.

### Result

We chose the best model for our project and converted it to a TensorFlow Lite model, after which we built an 
Android app and integrated the TensorFlow Lite model. The developed model detects objects and their locations 
in the frame. It also displays the confidence of each detected object. To name a few limitations, the app can only 
detect 10 objects at a time and has difficulty identifying objects in low lighting. Furthermore, the app keeps 
detecting the same object. We added a play and stop function to the code to start and stop the audio output 
whenever the screen is touched. 

### Future Work

Predict the situation of the 
surroundings based on the objects 
detected and their positioning.
▪ Quantizing the model for 
increasing the fps and decreasing 
the inference time.

## Build the demo using Android Studio

### Prerequisites

* If you don't have already, install **[Android Studio](https://developer.android.com/studio/index.html)**, following the instructions on the website.

* You need an Android device and Android development environment with minimum API 21.
* Android Studio 3.2 or later.

### Building
* Open Android Studio, and from the Welcome screen, select Open an existing Android Studio project.

* From the Open File or Project window that appears, navigate to and select the tensorflow-lite/examples/object_detection/android directory from wherever you cloned the TensorFlow Lite sample GitHub repo. Click OK.

* If it asks you to do a Gradle Sync, click OK.

* You may also need to install various platforms and tools, if you get errors like "Failed to find target with hash string 'android-21'" and similar.
Click the Run button (the green arrow) or select Run > Run 'android' from the top menu. You may need to rebuild the project using Build > Rebuild Project.

* If it asks you to use Instant Run, click Proceed Without Instant Run.

* Also, you need to have an Android device plugged in with developer options enabled at this point. See **[here](https://developer.android.com/studio/run/device)** for more details on setting up developer devices.


### Model used
Downloading, extraction and placing it in assets folder has been managed automatically by download.gradle.

If you explicitly want to download the model, you can download from **[here](http://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip)**. Extract the zip to get the .tflite and label file.

### Additional Note
_Please do not delete the assets folder content_. If you explicitly deleted the files, then please choose *Build*->*Rebuild* from menu to re-download the deleted model files into assets folder.
