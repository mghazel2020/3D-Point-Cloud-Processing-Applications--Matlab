# 3D-Point-Cloud-Processing-Application--Matlab
Objective: To demonstrate how to construct high-resolution 2D images from 3D point cloud and use apply OCR on the constructed 2D image to detect text.

# 1. Objectives

The objective of this project is to demonstrate how to construct high-resolution 2D images from 3D point cloud and use apply OCR on the constructed 2D image to detect text.

# 2. Motivation

In most depth measurements applications, only 3D point cloud data is collected. However, in some of these application may require higher resolution of objects of interest for computer processing and applications. For instance, consider a tire inspection application using 3D point cloud to examine the correct measurements of manufactired tires at the product line. In such application, there is a need to scan the tires and extract additional features, properties and identifiers from each inspected tire. These features include text and codes imprinted on the tires, such as the Department of Transportation (DOT) code, which certifies the tire manufacturer's compliance with government regulations. Extracting these codes requires optical character recognition algorithms, which will not work on 3D point cloud data and require higher resolution 2D images of the tires. 

In this project, we shall demonstrate how to construct high-resolution 2D images from 3D point cloud and use apply OCR on the constructed 2D image to detect text.

# 2. The input 3D Point Cloud

The input point cloud data representatiuon of part of a tire is illustrated in the next figure

<img src="figures/input_3D_point_cloud_tire.jpg" width="800">

# 3. Approach

As demonstrated in the submitted code, we implemented the following 3-step process to generated high-resolution 2D images from the relatively sparse 3D point cloud, illustrated in the fugure above:

1. Fit high resolution surface models to the 3D point cloud
2. Project 3D high resolution surface to a high resolution 2D image
3. Enhance the quality of the constructed high resolution 2D image.

## 3.1 Fitting high-resolution surface to the 3D point cloud

We make use of MATLAB 3D surface interpolation and fitting to constrctt high-resolution surface from the reklatively sparse 3D point cloud, as illustrated in the next figure.

<img src="figures/surface_3D_reconstruction_using_surf_grayscale.jpg" width="800">

## 3.2 Projecting the 3D high resolution surface to a high resolution 2D image

We then project the constructed high-resolution 3D surface 3D down to 2D high resolution from a top-down perspective, as illustrated in the next figure.

<img src="figures/projected_high_resolution_2D_image.png" width="800">

## 3.3 Enhancing the quality of the constructed high resolution 2D image

In order to enhance the quality of the constrcucted high resolutuion 2D image, we apply two simple image enhancement transformation, using MATLAB built-in functions:

* Histogram equalization
* Image sharpening

The output images after applying these enahnecmenet operations consecutively are illutrated next.

<img src="figures/projected_high_resolution_2D_image_histeq.png" width="800">
<img src="figures/projected_high_resolution_2D_image_histeq_imsharpen.png" width="800">


# 3. Text Detection from the Constructed High-Resolution 2D Image

The printed text on the constructed and enhanced 2D reolution image can now be detected using OCR algorithms. The figures below illustrated another reconstructed and enhanced 2D high resolution image and the OCR text detection results extracted from this image, respectively.

<img src="figures/new_enhanced_projected_high_resolution_2D_image.jpeg" width="800">
<img src="figures/new_enhanced_projected_high_resolution_2D_image_OCR_output.jpeg" width="800">

Using the MATLAB OCT built-in functionality, we are able to extract reasonable accurate text detection results from the high-resolution image.

# 4. Conclusion

In this mini-project, we demontrated a simple yet practical proof of concept of constructing high reolution 2D images from 3D point cloud and using the constracted high resolution image for computer vision applications, such text detection using OCR. In some depth-based applications, this may reduce or eliminates the need for additional vision imaging systems since we may be able to extract additional information from the high resolution 2D images reconstructed from the acquired 3D point cloud.  

