# Social-Distancing-in-Real-Time

Output       
:-------------------------:
![Output](Social-Distancing-Detection/Output/pedestrian-output.gif?raw=true "Output") 

- Use case: counting the number of people in the stores/buildings/shopping malls etc., in real-time.
- Sending an alert to the staff if the people are way over the social distancing limits.
- Acts as a measure to tackle COVID-19.

---
## Theory
This project is aimed at detecting people in a given video stream and then measuring the distance between them in real-time. The project uses deep learning techniques, specifically YOLO v3 object detection model, to detect and track people in the video. The project is mainly divided into three parts: object detection, object tracking, and distance measurement between detected people.

**Object detection:**
- I have used YOLOv3, trained on COCO dataset for object detection.
- In general, single-stage detectors like YOLO tend to be less accurate than two-stage detectors (R-CNN) but are significantly faster.
- YOLO treats object detection as a regression problem, taking a given input image and simultaneously learning bounding box coordinates and corresponding class label probabilities.
- It is used to return the person prediction probability, bounding box coordinates for the detection, and the centroid of the person.
---

**Object Tracking:**
- Once we have detected people in a frame, we need to track them across frames. 
- To achieve this, centroid tracking algorithm is used for tracking objects in a video.
- Centroid tracking works by assigning an ID to each detected person and then tracking their centroids (i.e., the center point of the bounding box that surrounds them) across frames.

---
**Distance calculation:**
- NMS (Non-maxima suppression) is also used to reduce overlapping bounding boxes to only a single bounding box, thus representing the true detection of the object. Having overlapping boxes is not exactly practical and ideal, especially if we need to count the number of objects in an image.
- Euclidean distance is then computed between all pairs of the returned centroids. Simply, a centroid is the center of a bounding box.
- Based on these pairwise distances, we check to see if any two people are less than/close to 'N' pixels apart.

## Thanks for the read!


