[//]: # (Image References)
[image_0]: ./misc/rover_image.jpg
[![Udacity - Robotics NanoDegree Program](https://s3-us-west-1.amazonaws.com/udacity-robotics/Extra+Images/RoboND_flag.png)](https://www.udacity.com/robotics)
# Search and Sample Return Project

# Introduction
- This project is modeled after
the [NASA Sample and Return Challenge](https://www.nasa.gov/directorates/spacetech/centennial_challenges/sample_return_robot/index.html).
- Fulfillment of this project gives first hand experience on the three essential elements of robotics, which are perception, decision making and actuation. The project is carried out in a simulator environment built with the Unity game engine.
- For more information about this project, check
[the starter code as provided by Udacity](https://github.com/udacity/RoboND-Rover-Project)

### Simulator
- Download depending on your OS:
- - [Linux](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Linux_Roversim.zip)
- - [Mac](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Mac_Roversim.zip)
- - [Windows](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Windows_Roversim.zip)

## Dependencies
You'll need Python 3 and Jupyter Notebooks installed to do this project.  The best way to get setup with these if you are not already is to use Anaconda following along with the [RoboND-Python-Starterkit](https://github.com/ryan-keenan/RoboND-Python-Starterkit). 


Here is a great link for learning more about [Anaconda and Jupyter Notebooks](https://classroom.udacity.com/courses/ud1111)

## Recording Data
- The `rover_playground.ipynb` notebook in the `code` folder analyzes my recorded data from the simulator as well as images that can be found at `calibration_images` folder.
- Recorded the data using the following steps:
- - launch the simulator
- - choose 'Training Mode'
- - Tap "R".
- -  Navigate to the directory you want to store data in
- - select it
- - drive around collecting data
- - Tap "R" again to stop data collection.

## Data Analysis
Included in the IPython notebook called `Rover_Project_Test_Notebook.ipynb` are the functions from the lesson for performing the various steps of this project.  The notebook should function as is without need for modification at this point.  To see what's in the notebook and execute the code there, start the jupyter notebook server at the command line like this:

```sh
jupyter notebook
```

This command will bring up a browser window in the current directory where you can navigate to wherever `Rover_Project_Test_Notebook.ipynb` is and select it.  Run the cells in the notebook from top to bottom to see the various data analysis steps.  

The last two cells in the notebook are for running the analysis on a folder of test images to create a map of the simulator environment and write the output to a video.  These cells should run as-is and save a video called `test_mapping.mp4` to the `output` folder.  This should give you an idea of how to go about modifying the `process_image()` function to perform mapping on your data.  

# Navigating Autonomously
- Go inside the `code` folder located at the root directory in your terminal
- Activate environment and launch jupyter notebook
```
$ source activate RoboND
```
- Run `drive_rover.py`
```
$ python driver_rover.py
```
- Launch the simulator
- I chose an 840 x 520 resolution with the graphic quality of 'good'
- Choose _'Autonomous Mode'_
- The rover should drive itselfthon drive_rover.py
```  
