# Object_Detection_in_Video
Azure Custom Vision to detect objects in a video. By Angela!!!!

For this sample, we will use the Custom Vision API to predict the type of helicopter visible in each frame of a video. The video that is sampled is available here: https://www.youtube.com/watch?v=EbiPOwNr9bE&feature=youtu.be

The process involves the following steps:

## 1. Train a Custom Vision Object Detection Model
This was done using the web portal at https://www.customvision.ai and publically available images of the four kinds of helicopter visible in the video. Details on how to do this is listed here: https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/get-started-build-detector

## 2. Obtain Frames of the Video
The object detection model can be applied to images but not videos. Therefore, frames of the video must be obtained for the model to be inferenced over. This was done using VLC and the method outlined here: https://www.isimonbrown.co.uk/vlc-export-frames/ and the sample rate was every third frame. The frames are saved to a lcoal folder. 

## 3. Perform Object Detection Predictions on Each Frame
Leveraging the code in the Jupyter Notebook, each frame is passed to the Custom Vision Prediction API to generate the prediction tag, prediction probability and the bounding boxes of each object. These details are applied to each frame using the Python library cv2, and the resulting image is saved to another local folder. 

## 4. Stitch Frames Together to Create Results Video
Using the Microsoft Photos app, a new video project was created by loading the results images into the storyboard, each with a duration of 0.2seconds. The resulting video was saved locally.  

## 5. Future steps
Automation of this process using Azure Functions and Logic Apps. 
