# Vehicle_Body_Pose_estimation
In this repository, I provide a Theoretical derivation for Vehicle body SE (3) pose estimation using Images obtained from 4 fisheye camera around the vehicle by minimizing the Photometric errors. The derivation here is inspired from the recent paper Xiao Liu, Lin Zhang et al. Online Camera Pose Optimization for the Surround-view System https://cslinzhang.github.io/CamPoseOpt/ but with a different strategy as explained below, which make this contribution novel.

In the paper of Xiao Liu, Lin Zhang et al. the main idea was to create a consistent surround view image from the well calibrated camera poses. The calibration is normally done offline which may not be sufficient as the camera poses can change when the vehicle experiences other dynamic motions while driving. Therefore, the authors of the paper developed finally a Ground-Camera Model which determines the correct SE (3) poses of the two (out of 4) cameras by minimizing the photometric errors between ground projections of the cameras adjacent to the two chosen for correction. The corrected pose of these two cameras results in a consistent surround view image. 

In contrast, I have again derived the Ground-Camera model equations with the SE (3) pose of a frame fixed to the vehicle rigid body as the only variable in optimization. This approach addresses directly the underlying reason of the main source behind the change of the camera poses which is infact the change of the pose of Vehicle rigid body itself as the 4 cameras are rigidly mounted on the vehicle body. Therefore, I propose to estimate the optimum SE (3) pose of the Vehicle body that minimizes the photometric error in all the overlapping ground projections of all the adjacent camera pairs.
