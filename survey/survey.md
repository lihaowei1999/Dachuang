# Survey

## 2D Real-Time Multi-Person Pose Estimation

- [Real-time 2D Multi-Person Pose Estimation on CPU: Lightweight OpenPose](https://arxiv.org/pdf/1811.12004.pdf)
  - 26 FPS, ~20 people, 456x256, 6-core Core i7-6850K CPU
  - code available
- [MultiPoseNet: Fast Multi-Person Pose Estimation using Pose Residual Network](https://arxiv.org/pdf/1807.04067v1.pdf)
  - 23 FPS, average 3 people; 15 FPS, 20 people, GTX1080Ti
  - person detector integrated, can be used to do matching
  - code available

<img src="https://xzreder.oss-cn-beijing.aliyuncs.com/img/image-20210728174655954.png" alt="image-20210728174655954" style="zoom: 67%;" />

- [Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields](https://arxiv.org/pdf/1611.08050v2.pdf)
  - 8.8 FPS, 19 people,  368×654, GTX-1080
  - code available



## Real Time Multi Person Multi View Pose Estimation

##### Benchmark [Humen3.6M](https://paperswithcode.com/sota/3d-human-pose-estimation-on-human36m)

- [Learnable Triangulation of Human Pose](./papers/1905.05754.pdf)
  - a popular method
  - **camera params are leveraged**
  - pytorch codes available

![image-20210727152133373](https://xzreder.oss-cn-beijing.aliyuncs.com/img/image-20210727152133373.png)

- [4D_Association_Graph_for_Realtime_Multi-Person_Motion_Capture_Using_Multiple Video Cameras](./papers/Zhang_4D_Association_Graph_for_Realtime_Multi-Person_Motion_Capture_Using_Multiple_CVPR_2020_paper.pdf)
  - 4D input (video)
  - **real time (track)** - 30 FPS 5 cameras 5 persons TITAN RTX
  - codes available
- [Light3DPose: Real-time Multi-Person 3D Pose Estimation from Multiple Views](./papers/2004.02688.pdf)
  - **real time** - 6 FPS 1080Ti
  - **camera params are leveraged**

![image-20210727145040612](https://xzreder.oss-cn-beijing.aliyuncs.com/img/image-20210727145040612.png)

- [Epipolar Transformers](./papers/Epipolar_Transformers.pdf)
  - not transformer
  - No.2 SOTA
  - pytorch codes available
- [Multi-View Multi-Person 3D Pose Estimation with Plane Sweep Stereo](./papers/Lin_Multi-View_Multi-Person_3D_Pose_Estimation_With_Plane_Sweep_Stereo_CVPR_2021_paper.pdf)
  - end to end
  - codes available
- [TesseTrack: End-to-End Learnable Multi-Person Articulated 3D Pose Tracking](./papers/Reddy_TesseTrack_End-to-End_Learnable_Multi-Person_Articulated_3D_Pose_Tracking_CVPR_2021_paper.pdf)
  - SOTA
  - **real time (track)**
  - No codes



## A Possible Design

Mainly three stages：

1. **2D pose estimation** in each camera view, respectively
2. **Person detection** (can be integrated in step 1) and then do **re-ID** to match each person in two camera views
3. for each person's each key point, do **2D -> 3D** based on known camera parameters 

Problem:

1. how to track a person



### Things Related

- stereo matching? -> a theme on paperswithcode
  - what is stereo matching https://medium.com/mini-distill/pps-efficient-deep-learning-for-stereo-matching-de253fc411d4
- 3D object detection based on stereo cameras -> probably not
- person reidentification? -> may not be, ReID has only one person in the image
  - flip-reid **tf2.2**
  - Lightweight Multi-Branch Network for Person Re-Identification **pytorch**
- 3D absolute human pose estimation -> some may be related
  - https://paperswithcode.com/task/3d-absolute-human-pose-estimation
- online MOT -> could be useful
  - https://paperswithcode.com/paper/real-time-multiple-people-tracking-with
- multi person multi camera human pose estimation by stereo camera -> **this keyword is useful**

