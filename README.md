# Udacity Self-Driving Car Nanodegree - Finding Lane Lines on the Road
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

The goal of this project was to detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images. 


This repo contains the code written to complete the first project on Udacity Self-Driving Car Nanodegree. This project consists of algorithms to identify lane lines on the road on a video. The video is taken from a camera at the center of a vehicle.
The repo contains the jupyter notebook [P1.ipynb](P1.ipynb) where the processing pipeline is implemented.

The pipeline consists on six steps:

- Returns a gray scaled version of the input image using **cv2.cvtColor** method.
- Applies a Gaussian blur to the provided image using **cv2.GaussianBlur** method.
- Use a [Canny transformation](https://en.wikipedia.org/wiki/Canny_edge_detector) to find edges on the image using **cv2.Canny** method.
- Eliminate parts of the image that are not interesting in regards to the line detection (for now...).
- Use a [Hough transformation](https://en.wikipedia.org/wiki/Hough_transform) to find the lines on the masked image using **cv2.cv2.HoughLinesP**. It also adjust a line to the set of lines returned by the Hough transformation in order to have a clearer-two-lines representation of the road lines using **np.polyfit** method.
- Merges the output of the hough transform with the original image to represent the lines on it.

First, the pipeline is tested agains the images contained at [test_images](test_images).

The images after the overlay can be found on the [test_images_output](test_images_output) directory.

After that test, the pipeline is modified to apply it on a video frame. The sample videos could be found [here](test_videos).

The video after the transformation are saved on the [test_videos_output](test_videos_output) directory.

