# AngularVelocityData
 
This repository contains the two color calcium imaging data from the 2017 paper:
_Angular velocity integration in a fly heading circuit_
Daniel Turner-Evans*, Stephanie Wegener*, Hervé Rouault, Romain Franconville, Tanya Wolff, Johannes D Seelig, Shaul Druckmann, and Vivek Jayaraman
eLife, https://doi.org/10.7554/eLife.23496

The data is contained in a series of MATLAB files in the _data_ directory. Each .mat file is a single trial, formatted as a MATLAB object with the following fields:
- 'GROIaveMax': The max intensity projection of the imaging volume over time for the green channel
- 'GROIaveMean'': The mean projection of the imaging volume over time for the green channel
- 'RROIaveMax'': The max intensity projection of the imaging volume over time for the red channel
- 'RROIaveMean'': The mean projection of the imaging volume over time for the red channel
- 'fullpath': The original location of the activity .tiff
- 'positionDat': An object containing the animal's behavior over the course of the experiment. Variable include:
