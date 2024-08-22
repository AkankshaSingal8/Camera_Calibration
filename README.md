# Camera Calibration and Camera-LIDAR Cross-Calibration

## Overview
This project focuses on two main tasks: Camera Calibration and Camera-LIDAR Cross-Calibration. The goal is to estimate the camera's intrinsic and extrinsic parameters, correct for radial distortion, compute re-projection errors, and establish a transformation between LIDAR and camera coordinate systems. These tasks are essential for applications in computer vision and robotics, especially in scenarios involving autonomous vehicles.

## Tasks

### 1. Camera Calibration

#### 1.1 Image Collection
- Captured approximately 25 images of a chessboard calibration pattern from various orientations using a stationary camera setup.
- Ensured that the entire chessboard pattern was visible in each image and that the corners were automatically detected using OpenCV functions.

#### 1.2 Intrinsic Camera Parameters
- Estimated intrinsic camera parameters, including:
  - Focal lengths
  - Skew parameter
  - Principal point
- Reported error estimates for these parameters.

#### 1.3 Extrinsic Camera Parameters
- Estimated extrinsic camera parameters for each selected image, including:
  - Rotation matrix
  - Translation vector

#### 1.4 Radial Distortion Correction
- Calculated radial distortion coefficients and used them to undistort 5 raw images.
- Analyzed the changes in straight lines at the corners of the images after applying the distortion coefficients and commented on the observations.

#### 1.5 Re-Projection Error
- Computed the re-projection error for each of the 25 selected images using the estimated intrinsic and extrinsic camera parameters.
- Plotted the re-projection errors using a bar chart and reported the mean and standard deviation of these errors.

#### 1.6 Corner Detection and Re-Projection Visualization
- Plotted figures showing the detected corners in the image alongside the re-projected corners for all 25 images.
- Commented on the computation of re-projection error.

#### 1.7 Checkerboard Plane Normals
- Computed the checkerboard plane normals in the camera coordinate frame for each of the 25 selected images.

### 2. Camera-LIDAR Cross-Calibration

#### 2.1 LIDAR Plane Normals and Offsets
- Downloaded the provided dataset, including RGB images and corresponding LIDAR scans.
- Computed the chessboard plane normals and corresponding offsets using the planar LIDAR points from the .pcd files via singular value decomposition.

#### 2.2 Deriving Transformation Equations
- Derived the equations needed to estimate the transformation from the LIDAR frame to the camera frame, including rotation and translation matrices.

#### 2.3 Implementing Transformation Estimation
- Implemented a function to estimate the transformation from the LIDAR to the camera coordinate system, ensuring the rotation matrix has a determinant of +1.

#### 2.4 LIDAR to Camera Frame Mapping
- Mapped LIDAR points to the camera frame using the estimated transformation and projected them onto the image plane using the intrinsic camera parameters.
- Verified whether all points were within the checkerboard pattern’s boundary in each image.

#### 2.5 Normal Vector Comparison and Error Analysis
- Plotted the normal vectors for 5 image and LIDAR scan pairs and computed the cosine distance between the camera normal and the transformed LIDAR normal.
- Plotted a histogram of these errors and reported the average error with the standard deviation.

## Conclusion
This project provides a comprehensive approach to camera calibration and camera-LIDAR cross-calibration, essential for accurate sensor fusion in autonomous systems. The results include intrinsic and extrinsic parameter estimation, distortion correction, re-projection error analysis, and the establishment of a transformation between LIDAR and camera coordinate frames.
