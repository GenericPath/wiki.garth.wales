---
description: Stitching many images together
---

# Image Mosaicing

[https://blackboard.otago.ac.nz/bbcswebdav/pid-2625554-dt-content-rid-16683578\_1/courses/COSC450\_S1DNI\_2021/Mosaicing%204%20-%20Review.pdf](https://blackboard.otago.ac.nz/bbcswebdav/pid-2625554-dt-content-rid-16683578_1/courses/COSC450_S1DNI_2021/Mosaicing%204%20-%20Review.pdf)

## Detect features

Feature points / key points and feature descriptors

* Key points reliably detected across multiple images + precise location information
* Descriptor to tell features apart
  * Ideally robust to changes in lighting, viewpoint, contrast etc

### Features

#### Corners

* If no gradient then flat area...
* Gradient in one direction -&gt; edge
* Gradient in all directions -&gt; corner

Gradient calculated using

* a convolutional filter \(i.e. like sobel filter\)
  * One each for horizontal and vertical components
* Shi-Tomasi corners

Only a location

#### Blobs

Blobs are the new corners, a dark region surrounded by a bright region \(or vice-versa\)

Difference of a Gaussian filter

* Two Gaussians of different width
* Subtract wide from narrow
* Bright blobs - high positive response
* Dark blobs - high negative response

Scale and location

### 

## Match features

_The hard part_

To find good feature correspondences.. you need good descriptors for features!

### Descriptors

_A feature might be found, but using say raw pixels to describe it doesn't work if you rotate.._

We want to be invariant to

* Translation
* Rotation
* Scale
* Brightness / Contrast

Translation invariance is what we solved in the first place..

Scale invariance is using blob features

Brightness invariance is from using image gradients \(relative brightness\)

Rotation invariance by estimating feature orientation

**SIFT** does this well

* SIFT does feature orientation with Histogram of Gradients
* SIFT uses blobs

### Matching

* Approximate Nearest neighbours \(look in distinct regions in both images\)
  * But might be transformed slightly past that region...
* Quadtrees, Octrees, etc
  * Recursively split across axis to have some minimum number of splits/items
* k-d Trees
  * Split on axis to keep similar number of items per region
* Bruteforce
  * Match literally everything together.. \(even most of these are wrong!\)

Rejecting bad matches

* Ambiguity \(two with similar distances\)
* Orientation \(not the same relative orientation\)
* Scale \(not the same relative scale\)

_or something along those lines_

## Estimate a homography

Homography is a linear map \(transformation matrix\) between one images feature to that feature in the second image.

Given a set of n points \(**u** ,**v** \) which are matching points in both images we want to estimate the homography matrix **H**.

* **u** ≡ **H x u'**
  * Equivalence due to being the same when scaled also

\*\*\*\*

### Direct linear transform

Estimate the homography matrix using matching points \(there are two equations to substitute all the points with\) such that A**h** = 0 = 0**h**

So looking for an eigenvector with a zero eigenvalue...

_**Four points is sufficient**_ \(H has 9 values, upto a scale so 8 degrees of freedom\)

More points gives a least-squares solution

* Eigenvector with the smallest least squares solution
* Minimised \|\|A**h\|\|**

Because each u,v are pixel coordinates vary from 0,1 up to 1000's therefore solutions quite unstable  
as equations have 0, 1, u, v and u\*v values so vary from 0 to millions. Normalise to make each each h\_i have a similar effect on the solution  


therefore:

* Normalise
* DLT
* Denormalise

### Reprojection error

With more than 4 points we are trying to minimise \|\|A**h\|\|** but has no inherent meaning.

Instead could consider error as only existing in the second image \(transfer error\)

Reprojection error is for error in both images, nonlinear least squares

* Levenberg Marquardt \(to solve the reprojection error\)

Least-square solutions are sensitive to outliers!

Use _RANSAC_ to solve this.

* Randomly pick 4 points
* Esimate H
* Count how many agree
* Repeat until you find a good one

Parameters

* Threshold of acceptance \(too high and outliers, too low and small consensus set\)
* Number of trials \(resource limitations? could also be considered as a probability of success instead\)

### The gist

* Compute and describe features in each image
* Find correspondences between images, _filter them_
* RANSAC estimation via DLT \(selection 4, estimate H. See how many agree\)
* Optimal estimation - using all inliers estimate H using Levenberg-Marquardt to minimise reprojection error

## Warp one image to the other

Project the image onto a mapping scheme \(planar, spherical, cylindrical etc\)

### Seamlines

* Minimise error along seam
* Pixels become verticies of a graph
* Djikstras algorithm for shortest path

Another approach

* Find worst you have to cross
* Remove edges with greater weight
* Shortest remaining path

### Multi-image

* If realtime, seamline with incremental seamlines \(but doesn't neccessarily produce the most optimal solution\)
* Junction fitting - Use a rough guess, seamline to some junction area \(not global!\)
  * Bottlenecks are found in each local area

