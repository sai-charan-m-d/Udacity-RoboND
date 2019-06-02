A PR2 robot is given a RGB-D sensor so it can pick and place objects in the appropriate place. 
The theme of this lab is to develop the image processing pipeline. This requires object detection, identification, and localization.


There are two phases in this project , an offline training for matching image features to object labels and an online prediction to identify objects within the view of the robot.


1) Offline Training

Given an image of an object, correctly identify the label of the object. We use SVM to classify images to object labels. The input is a feature vector composed of the color (RGB channels) + normal (XYZ dimensions) histogram.

Training data is collected via an empty world (shown below) where random object poses are presented in front of the RGBD camera. 


After training a SVM model from this data, we can visualize a confusion matrix to show nearly 94% accuracy in identifying the correct object. We achieved this level of accuracy by using 100 training examples per object.


2) Online Prediction

The robot is presented with a noisy snapshot of the environment.


A first step is to filter out clearly erroneous measurements by identifying point cloud measurements that clearly deviate from neighboring points.


Next, we need to separate the objects from the table so that we can then individually classify each group of object point clouds. We use RANSAC using a plane filter to robustly identify points belonging to the table.



Given this particular setup, we assume that points not belonging to the table are the objects.


Next, we segment point clouds into objects via euclidean clustering. Clustering assume that object clusters have specific density of points.


Finally, we label the object point clouds by predicting their labels from our SVM model.

The # of objects correctly identified:
World 1: 3/3

World 2: 5/5

World 3: 7/8

========================================

Running:

1) Build
rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y
catkin_make

2) Execute

roslaunch sensor_stick training.launch
rosrun sensor_stick capture_features.py
rosrun sensor_stick train_svm.py
