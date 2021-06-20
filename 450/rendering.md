---
description: The essence of computer graphics
---

# Rendering

We have all the stereo, 3D reconstruction and mosaicing data but what to do with them?

One example is _real-time graphics_

* VR headset
* Augmented reality
* Video games
* Visualisations

## CasualStereo

* Same method as a panorama image, but creating stereo panoramas
* Handheld capture \(casual\)
* Structure from motion to determine camera poses
* Able to handle spherical motion \(i.e. arms stretched out to keep motion on surface of a sphere\)
* View syntehsis to generate perfect circle of images
* Extract left and right eye columns to compute two panoramas

They wanted a method that was quick and easy to use.

## Volume rendering

Made up of voxels, so a solid 'object' of data

* Simulations \(fluid dynamics\)
* Geoscience data
* Medical imaging data
* Material science data

Types

* Slicing - simply take pixel values for some slice cross section
* Indirect - make a mesh out of it
  * Contour lines
  * Marching cubes
* Direct
  * Image based
    * Ray tracing
    * Colour value from each voxel
    * Weighting from transparency values
  * Object based
    * Each voxel to calculate colour in image \(splatting\)
  * Texture-based
    * Texture mapping in GPU

Ray tracing

* Cast ray into scence, sample along ray.
  * e.g. grayscale take the highest intensity as the value

## Physically based rendering

Phong

* Ambient + diffuse + specular

Global illumination

* Direct + indirect lighting
* Shadows
* Inter-object reflections
* Radiosity

BRDF \(Bidrectional Reflectance Distribution Function\)

* Ratio of light coming from one direction that gets reflected in another direction
* Pure reflection, assumes no light scatters
* Focuses on angular aspects, not spatial variation
* Can be measured from real objects
* Cook-Torrance BRDF includes components of scattering and mirroring
  * Takes into account microfacets in the surface \(how rough it is\)

## Image based rendering

Given images and geometry

* Produce new images

Benefits

* No labour to model
* Captures high complexity
* Rendering time depends only on image size not complexity

### Plentopic function

Or a 'light field' describes light flowing in every direction through every point in space. A 5D function to map this.

## Methods

### Quicktime VR

* Stitch panoramas together, let you explore them in 360 view

### Layered depth images

* Similar to a sprite with depth, pixels contain depth values and colours
* Some depths may be occluded

Use by facebook for the one shot 3D stuff.

* Take an image
* estimate depth
* generate layers
* colour inpainting
* mesh
* novel view

## Light fields

* 4D slice of plenoptic function \(fixed time\)
* Assumes free of occluders
* Parameterize rays by intersection with two planes

I.e. take a bunch of images and can then sample new views

* Rotation of camera allowed with a rotating object to get a bunch of views

## Lumigraph

* Unstructured capture
* Precalibrated camera and camera poses computed by markers
* Rough geometric model of object
* Resamples images to two plane representation

## Multiplane images

* Approximate light field as a stack of semi-transparent, coloured layers arranged at various depths
* Uses gradient descent to generate an MPI from a set of sparse camera viewpoints
* Training datra based on a set of input views and a crop within target view
* Best optimized for forward-looking views from position near center of projection

## Casual real-world light fields

* Compute camera poses using custom structure-from-motion technique
* Predict an MPI for each sampled image with a 3D CNN
* Compute depth maps from predicted MPIs
* MPIs render views by re-projecting its layers into the novel view and compositing them from back-to-front

## Immersive light fields

* 46 low cost action cameras, all on a hemisphere
* Uses multi-sphere images instead of MPI to provide panoramic experiences as needed for VR

## Outlook NERFS

* Neural volumes \(consiting of opacity and colour at each 3D point\)
* Neural Radiance Fields \(Uses DeepSDF but density and color + numerical integration to approximate volumetric rendering\)

Really good, keep fine details and are temporally stable unlike other methods

