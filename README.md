
# Project Title: Customer Footfall Count
## Project Description: Integrating computer vision and deep learning to identify and track customer flow in and out of the shop


### Features of Customer Footfall Count
- Only count each person once
- Showcase how many people have entered and left
- Have a confidence threshold of 0.5
- Can be hosted on a cloud server
 
### Simplified overview
After getting our data set, we will implement object detection and object tracking to it. YOLOv4 is used for object detection and DeepSORT is used for object tracking. Object detection helps us identify what object is in the frame (bounding boxes)  and in our case, we will only be focusing on humans. Object tracking on the other hand will be tracking each and every object detected beforehand and giving them each a unique id. The output (Object detection) of YOLOv4 is fed to DeepSORT for object tracking. When DeepSORT tracks an object crossing the line, it will prompt the person to the counter to +1 or -1 according to their direction. This will enable us to keep track of how many people are currently within the line (in the shop). 

### Why YOLOv4
The reason why we chose YOLOv4 is that it’s relatively easy to set up. Besides, due to the time constraint of completing this project in a week, YOLOv4 has a pre-trained model, the coco dataset, which has over 80 trained data sets. This enabled us to skip the step of testing a new dataset. Besides, YOLOv4 has also gained a reputation for its high accuracy and high speed for detecting objects in fps and is able to produce near real-time feedback on live footage without the need to store them locally.

### Why DeepSORT
DeepSORT allows us to track an object after it is being detected. Even in any circumstances where the object went out of sight for a few seconds, it has the ability to determine the relationship between a measurement and an existing track, allowing it to track the object which went out of sight for split seconds. Its high accuracy and competency to offer multiple object detection and tracking is the best fit to be used in our project.

### Data Source
[People Walking Inside Shopping Mall Stock Footage](https://www.youtube.com/watch?v=_bmSDYqO8Dw)

### Difficulties faced
As said, our aim of this project is to come out with a people counter to keep track of the people entering and leaving the store. Implementing the counter algorithm gave us a small hiccup as there are many approaches to produce the same outcome. The method used may not be the best approach but is still able to deliver the expected outcome.  Due to large weights from YOLOv4, speed may be compromised if CPU is used instead of GPU. 

### Features to implement in the future
Since our program is made to cater to retail stores, it would be great to implement emotion detection to help us monitor the customer experience of the store. 

### How to Install the Project
#### 1) For object detection with YOLO v4 
   - Clone darknet repo
   - Change makefile to enable GPU, LIBSO and OPENCV
   - Build darknet to use its dependencies
   - Download pre-trained weight
   - Define helper functions, to display video, upload and download video
   - Test with Sample Data
   - Call out functions
   - Test with Personal Data
   - Call out functions

#### 2) For object tracking with DeepSORT
   - Clone repo with DeepSORT with YOLO v4
   - Step into YOLOv4-deepSORT folder
   - Install dependencies
    - Fetching YOLOv4 pre-trained weights
   - Convert pre-trained weights into tensor flow model
   - Define helper functions, to display image and video, upload and download video
   - Define helper function to convert video format from .avi to .mp4
   - Test with Sample Data
   - Call out functions
   - Test with Personal Data
   - Limit the coco-classes to only track human
   - To undo the limitation, head to object_tracker.py, then head to the “allowed_classes” variable to customize classes of objects to be tracked

#### 3)  To implement the counting algorithm
   - Obtain the coordinates of the bounding boxes and store them into a dictionary in the form of {ID, [last_updated_frame number, x-coordinates, y-coordinates]}.
   - If a new frame has the same ID, the dictionary will update the value.
   - The dictionary will discard the value stored for more than 5 seconds.
   - The current coordinate and coordinate in the dictionary will connect and draw a vector line.
   - The counter will increase and decrease based on the direction of the vector  when an intersection happens between the specific counter draw line and the vector line.
   - To change the counter draw line, head over to the variable named “lines”  and change the coordinates.


##### Credits
[YOLOv4 in the CLOUD: Install and Run Object Detector (FREE GPU)
](https://www.youtube.com/watch?v=mKAEGSxwOAY)
[theAIGuysCode - yolov4-deepsort](https://github.com/theAIGuysCode/yolov4-deepsort)
