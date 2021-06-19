---
description: Stitching many images together
---

# Image Mosaicing

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

A method to 

## Warp one image to the other

