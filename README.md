# **Finding Lane Lines on the Road** 

Overview
---

The main goal of the project is to identify and annotate the lane lines in a video of a road. A code pipepline of image processing is developed and tested, first on images and subsequently on videos. In brief, a raw image is first converted to grayscale, then filtered using a guassian kernel followed by subjecting it to Canny Edge Detection algorithm. The region of interest in the image (bare minumum area including the lane lines) is marked and everything outside is masked out. This image is then subjected to Hough transform to obtain line segment parameters representing the lines obtained by Canny Edge detection. The obtained line segments are then separated into two sets: left lane and right lane. The line segments with outlier slopes are rejected to obtain a smoother, uniform dataset representing each lane. Finally, these line segments are used to calculate an average, equivalent single line representing one lane. Once a statisfactory lane identification is observed, this pipeline is put together to work on videos, acting on images from individual video frames. In order to observe a smooth transition on video from one frame to another, a weighted moving average filter of window size 3 is implemented.


This project requires the installation of miniConda followed by specific packages, all of which are covered in *environment.yml*

**The key components of the project are as follows**:

1. P1.ipynb: a Jupyter notebook containing the detailed project with code
2. writeup.md: a brief project summary with pictures
3. test_images_output: Directory containing the outputs of the lane detection pipeline
4. test_videos_output: Directory containing annotated, lane detected videos