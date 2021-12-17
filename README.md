<p align="center"><img width=20% src="https://github.com/yyj-02/Customer-Footfall-Counter/blob/main/assets/logo.png" /></p>
<h1 align="center">Customer Footfall Counter</h1>
<h3 align="center">A machine learning + computer vision project to count customers</h3>

# Customer Footfall Counter

<p align="center"><img width=70% src="https://github.com/yyj-02/Customer-Footfall-Counter/blob/main/assets/result.gif" /></p>

## Project Description

This project was created for the [ICMS Embark](https://icms-embark.webflow.io/) event which is sponsored by the [Sunway Group](https://www.sunway.com.my/). This machine learning model can analyse a top down CCTV footage to identify and track moving humans inside the footage. The algorithm will then count the number of people entering and leaving the premise by counting the number of people crossing the boundary lines.

## Team Members

- [Goh Choi Yin](https://github.com/angelina-create)
- [Lim Yi Jing](https://github.com/yijingLim/)
- [Yeoh Yong Jie](https://github.com/yyj-02)

## Tech Stack

<p align="center">
<img height=96px src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/640px-Python-logo-notext.svg.png" />&nbsp;&nbsp;&nbsp;&nbsp;
<img height=96px src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Tensorflow_logo.svg/1200px-Tensorflow_logo.svg.png" />&nbsp;&nbsp;&nbsp;&nbsp;
<img height=96px src="https://colab.research.google.com/img/colab_favicon_256px.png" />
</p>

## Methodology

1. YOLOv4 model trained with the COCO dataset is first used to identify all humans inside the footage.
2. DeepSORT algorithm is then employed to track every identified humans.
3. An algorithm is then written to determine the intersection of the bounding lines with the travelling vector of the people and the direction they are moving in using determinant.

## Implementation

1. This model can be integrated into a CCTV to provide higher accuracy and ability to define the objects, especially during emergency, off hours and abiding to Covid-19 SOP.
2. An integration with dashboard can give insights about the marketing as well as products likability of a particular season, or to understand buying patterns better.
3. The realtime data can also give managers customer's insight, allowing them to make quick high-level decision.

## Future Improvements

1. This project can be deployed on a cloud server to allow greater scalability and flexibility.
2. Multi-Live-camera object tracking without overlapping from different direction can be implemented.
3. This service can be integrated with a real time dashboard that displays the demographics over time to give us more insights.
4. The model can be improved to be able to differentiate between people of different age groups and genders.

## Credits

[The Ai Guys Code: yolov4-deepsort](https://github.com/theAIGuysCode/yolov4-deepsort)
