# EECS504_HW9
Panoramic Stitching
In this problem we will develop an algorithm for stitching a panorama from overlapping
photos (Figure 1), which amounts to estimating a transformation that aligns one image to
another. To do this, we will compute ORB features1
in both images and match them to obtain
correspondences. We will then estimate a homography from these correspondences, and we’ll
use it to stitch the two images together in a common coordinate system.
In order to get an accurate transformation, we will need many accurate feature matches.
Unfortunately, feature matching is a noisy process: even if two image patches (and their ORB
descriptors) look alike, they may not be an actual match.
To make our algorithm robust to matching errors, we will use RANSAC, a method for
estimating a parametric model from noisy observations. We will detect keypoints and represent
descriptors using ORB. We will then match features, using heuristics to remove bad matches
