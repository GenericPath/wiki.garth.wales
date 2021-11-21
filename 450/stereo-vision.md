---
description: Depth from a pair of images
---

# Stereo Vision

## Camera calibration

Use a checkerboard pattern to calibrate camera (set up a known reference plane)

Can calculate a homography based on 3 images for camera calibration

Can also model lens distortion or something

## Depth

From an image we can get

* Distant objects are smaller
* Close objects occlude distant
* Motion cues (parallax)
* Perspective - converging lines
* Depth from focus
* Atmospheric effects

But it is independent of these - random dot stereograms

Difference between views is disparity

z = f b / (u\_1 - u\_2)        f is focal length, b is distance between pinholes, z = depth

### Estimating depth

(for two cameras with same settings)

* Rectify images (warp to a simplified form where the match is only along some horizontal distance)
* Don't need SIFT if using the same/similar cameras to take both pictures!
* Block matching, SAD or SSD. Sliding window essentially to find the minimum points.

More generally (i.e. cameras have different calibration parameters, not a stereo camera)

* Rotation between cameras
* Translation along all three axes

Align XYZ plane with one camera

## Epipolar geometry

Epipolar line is the intersection of the epipolar plane

* plane defined by some point P, and the two centres of the cameras

If uncalibrated, we can calculate the epipolar line using fundamental matrix

* 7 degrees of freedom
* maps image points to their corresponding epipolar lines
* encapsulates both intrinsic and extrinsic properties of cameras

If calibrated, we can calculate the epipolar line using essential matrix (factor out the two K=K'=I)

* relates one point on a camera to the point where it is on the other camera
* without say distance between points we cannot determine absolute pose
* To estimate it using corresponding image points, the intrinsic parameters of both cameras must be known.
* 5 degrees of freedom (3 for rotation, 3 for translation, -1 for unknown scale)

## Stereo estimation

### Fundamental matrix

* 8-point algorithm: linear system p'^T F p = 0
  * 7-point algorithm works as only 7 DoF but harder and gives multiple solutions
  * Usually have lots of points.
  * 7-point if you want fewer RANSAC trials! or need constraints on F
* Solve via normalised DLT
* Estimates _relative pose_
* Estimate 3D structure
* Minimise reprojection error via non-linear least squares

### Essential matrix

* Estimate F, compute E = K'^T F K
  * 8 or 7 point algorithm
* Alternatively: 5 point algorithm
  * Complex, non-linear system
  * Up to 10 solutions
  * But - fewer RANSAC trials, enforces constraints

## Structural estimation (3D points)

Need the _relative pose _between camera (e.g. rotation, R, and translation, **t**,** **between cameras)

**E** tells us about R and **t**

* E = \[**t**]xR

Use singular value decomposition of E to get the solutions

* We know **w** must lie in front of both cameras (to select the correct solution)

Can minimise for algebraic or for non-linear in true K, K', R, t, w\_i

* Initial estimate from algebraic error minimised
* Minimise further via Levenberg-Marquardt

## Multi-view stereo

* Naive - Incremental two view approach
* Better - Identify best matching pair (and reconstruct relative pose + 3D points)

### Matching images

Bruteforce (matching all pairs) is expensive

#### Bag of Words

* Group features into 'words'
* Count how many times each 'word' appears in each image (histogram)
* Compare histograms (Similar histograms -> similar images)

Bag of Words as vectors ignores word order and is mostly applied to counts (but can be a binary present/not)

For images

* Cluster features (k clusters e.g. k-means where centers become k-'words')
* Detect and describe features, count features closest to each word
  * An example could be number of circle features present, number of triangle features etc etc

Therefore you can do two-view stereo for relative pose and then construct 3D points from best matches

### Absolute pose

Minimum need 3 points to determine pose from 2D-3D matches

Determine P (pose of camera) from the world space points A,B,C using distances and angles

* P is intersection of spheres, i.e. centered at A with radius |P->A| and ....
* Two solutions (use a fourth point or RANSAC to disambiguate)
  * 2 spheres gives a ring, another sphere gives two points on that ring

Always minimising reprojection error

* but reprojection error with Levenberg-Marquardt needs jacobian matrix that scales with number of measurements.. multiple images big jacobian!
  * But a lot of zeroes are present (sparse matrix), and they are predictable so we can skip them

## SLAM

Need to built a map of the environment, and know where it is within the environment

* Therefore, **S**imultaneous **l**ocalisation **a**nd **m**apping

kinda like multi-view stereo, but often with a speed requirement.

Small errors add up over time, need to detect when you return to previous regions to do 'loop closure' to correct for errors.







