# AngularVelocityData

## Overview
This repository contains the two color calcium imaging and behavioral data from the 2017 paper:

_Angular velocity integration in a fly heading circuit_

Daniel Turner-Evans*, Stephanie Wegener*, Hervé Rouault, Romain Franconville, Tanya Wolff, Johannes D Seelig, Shaul Druckmann, and Vivek Jayaraman

eLife, https://doi.org/10.7554/eLife.23496

Please email Dan at dturnere 'at' ucsc.edu with any questions.

## Data
The data is contained in a series of MATLAB files in the _data_ directory. Each .mat file is a single trial of one of three conditions:
- **Dark**: The fly was walking in the dark
- **1x**: The fly was shown a stripe that it had closed loop control over
- **2x**: The fly was shown a stripe that it had closed loop control over with a 2x gain (e.g. if the fly rotated 15 deg, the stripe rotated 30 deg).

The data is formatted as a MATLAB object with the following fields:
- **GROIaveMax**: The max intensity projection of the imaging volume over time for the green channel
- **GROIaveMean**: The mean projection of the imaging volume over time for the green channel
- **RROIaveMax**: The max intensity projection of the imaging volume over time for the red channel
- **RROIaveMean**: The mean projection of the imaging volume over time for the red channel
- **fullpath**: The original location of the activity .tiff
- **positionDat**: An object containing the animal's behavior over the course of the experiment. Variable include:
  - **t**: the time
  - **OffsetRot**: the animal's angle on the ball
  - **OffsetFor**: the animal's x or "forward" position
  - **OffsetLat**: the animal's y or "lateral" position
  - **dx0**, **dx1**, **dy0**, **dy1**: pixel readouts from the ball tracking cameras
  - **closed**, **direction**, **trans**, **gain**, **exType**: constants used for setting up the virtual reality
  - **tFrameGrab**: indices when the microscope computer was grabbing an imaging frame
  - **tVR**: indices when the virtual reality was refreshing
  - **tStim**: indices when an external stimuli (e.g. a light source for optogenetics) was being used

## Scripts
I have included a couple of jupyter notebooks that demonstrate how to work with the data in python in the _src_ directory.
- **mat2py**: Load the matlab data, convert it to a pandas DataFrame, group it by fly, organize it into a dictionary, pickle it, and save it
- **actPlot**: Load the pickled data and plot an example trial
