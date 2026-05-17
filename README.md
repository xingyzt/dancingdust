Particle trackers for Physics 111B: Brownian Motion and Cellular Transport

The trackers are built around a convolutional pipeline that finds diffraction rings in microscopy images.
In the `microspheres/` directory, this pipeline is applied frame-by-frame,
then connected via a neighborhood search between adjacent frames. 
In the `onion/` directory, this pipeline is only applied to the initial frame.
For subsequent frames, we use OpenCV's implementation of Lucas-Kanade optical flow to find where each 
ring shifted.

The `microspheres/` directory contains an example image sequence of 1-micron-diameter polystyrene microspheres
undergoing Brownian motion in a 2.6-centipoise solution of polyvinylpyrrolidone (PVP).
The `onion/` directory contains an example image sequence of vesicles being actively transported in the fifth
layer of the bulb of a white common onion.

There are some arguments that the LK tracking is better suited for the onion due to how dense the points are,
however I think it's mainly an interesting pedagogical exercise to compare the frame-by-frame centroid finding
versus the LK optical flow tracking.
