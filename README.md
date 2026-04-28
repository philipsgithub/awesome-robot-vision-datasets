# Awesome Robot Vision Datasets

A curated list of datasets related to robotic vision tasks, including few-shot learning, object detection, pose estimation, grasping, segmentation, depth estimation, SLAM, and autonomous navigation.

---

## Table of Contents
- [Few-Shot Learning](#few-shot-learning)
- [Object Detection & Recognition](#object-detection--recognition)
- [6D Pose Estimation](#6d-pose-estimation)
- [Robotic Grasping](#robotic-grasping)
- [Semantic & Instance Segmentation](#semantic--instance-segmentation)
- [Depth Estimation & RGB-D](#depth-estimation--rgb-d)
- [SLAM & 3D Reconstruction](#slam--3d-reconstruction)
- [Navigation & Autonomous Driving](#navigation--autonomous-driving)
- [Multi-Task & Meta-Learning Benchmarks](#multi-task--meta-learning-benchmarks)

---

## Few-Shot Learning

| Dataset | Year | Classes | Description | Link |
|---------|------|---------|-------------|------|
| **Omniglot** | 2015 | 1,623 | Handwritten characters from 50 alphabets; standard few-shot benchmark | [Paper](https://science.sciencemag.org/content/350/6266/1332) |
| **miniImageNet** | 2016 | 100 | 100-class subset of ImageNet (64 train / 16 val / 20 test); widely used for N-way K-shot evaluation | [Paper](https://arxiv.org/abs/1606.04080) |
| **tieredImageNet** | 2018 | 608 | Hierarchically organised ImageNet subset with semantic train/test splits to reduce domain overlap | [Paper](https://arxiv.org/abs/1803.00676) |
| **CIFAR-FS** | 2018 | 100 | CIFAR-100 split into 64/16/20 classes for few-shot evaluation | [Paper](https://arxiv.org/abs/1805.08136) |
| **FC100** | 2018 | 100 | CIFAR-100 regrouped by coarse superclasses for harder few-shot evaluation | [Paper](https://arxiv.org/abs/1805.10123) |
| **CUB-200-2011** | 2011 | 200 | Fine-grained bird species recognition; commonly used for few-shot fine-grained tasks | [Website](http://www.vision.caltech.edu/visipedia/CUB-200-2011.html) |
| **Meta-Dataset** | 2020 | 10 sources | Large-scale benchmark spanning 10 diverse image datasets for realistic few-shot evaluation | [Paper](https://arxiv.org/abs/1903.03096) / [GitHub](https://github.com/google-research/meta-dataset) |
| **ORBIT** | 2021 | 486 objects | Real-world few-shot object recognition for assistive robotics, captured by blind/low-vision users | [Paper](https://arxiv.org/abs/2104.03841) / [GitHub](https://github.com/microsoft/ORBIT-Dataset) |
| **FEWSOL** | 2022 | 336 objects | Few-shot object learning dataset specifically designed for robot perception in cluttered tabletop scenes | [Paper](https://arxiv.org/abs/2207.03333) / [GitHub](https://github.com/IRVLUTD/few-shot-dataset) |

---

## Object Detection & Recognition

| Dataset | Year | Description | Link |
|---------|------|-------------|------|
| **ImageNet (ILSVRC)** | 2010 | 1.2 M images across 1,000 classes; foundation benchmark for visual recognition | [Website](https://image-net.org) |
| **MS COCO** | 2014 | 330 K images with 80 object categories; standard benchmark for detection, segmentation, and captioning | [Website](https://cocodataset.org) |
| **PASCAL VOC** | 2005–2012 | 20-class benchmark for object detection and segmentation | [Website](http://host.robots.ox.ac.uk/pascal/VOC) |
| **Open Images V7** | 2016–2022 | 9 M images, 600 object classes with bounding boxes, segmentation masks, and relationships | [Website](https://storage.googleapis.com/openimages/web/index.html) |
| **Objects365** | 2019 | 638 K images, 365 categories; large-scale detection pre-training dataset | [Website](https://www.objects365.org) |
| **YCB Object Set** | 2015 | 77 household objects with 3D models; standard set for robot manipulation benchmarks | [Paper](https://arxiv.org/abs/1502.03143) / [Website](http://www.ycbbenchmarks.com) |
| **BigBIRD** | 2014 | 125 everyday objects with high-res images and 3D point clouds for tabletop recognition | [Website](http://rll.berkeley.edu/bigbird) |
| **HOPE** | 2020 | 28 grocery objects with 6D pose annotations for household robot perception | [Paper](https://arxiv.org/abs/2008.09298) / [GitHub](https://github.com/swtyree/hope-dataset) |

---

## 6D Pose Estimation

| Dataset | Year | Objects | Description | Link |
|---------|------|---------|-------------|------|
| **LINEMOD** | 2012 | 15 | Classic benchmark for texture-less object pose estimation | [Paper](https://link.springer.com/chapter/10.1007/978-3-642-33765-9_8) |
| **Occlusion LINEMOD** | 2014 | 8 | LINEMOD extension with heavy inter-object occlusion | [Paper](https://arxiv.org/abs/1406.1171) |
| **T-LESS** | 2017 | 30 | Industry-relevant texture-less objects with no discriminative color or texture | [Paper](https://arxiv.org/abs/1701.05602) / [Website](http://cmp.felk.cvut.cz/t-less) |
| **YCB-Video** | 2018 | 21 | Video sequences of YCB objects with 6D pose labels for deep-learning-based estimation | [Paper](https://arxiv.org/abs/1711.00199) / [GitHub](https://github.com/yuxng/YCB_Video_toolbox) |
| **BOP Benchmark** | 2019–ongoing | 7+ datasets | Unified benchmark for 6D object pose estimation covering LINEMOD, T-LESS, YCB-V, and more | [Website](https://bop.felk.cvut.cz) |
| **HomebrewedDB** | 2019 | 33 | Diverse objects with multiple textures and shapes for pose estimation | [Paper](https://arxiv.org/abs/1904.03167) |
| **YCBV-Synth** | 2020 | 21 | Photorealistic synthetic rendering of YCB-Video for sim-to-real pose estimation | [Paper](https://arxiv.org/abs/2011.11190) |

---

## Robotic Grasping

| Dataset | Year | Description | Link |
|---------|------|-------------|------|
| **Cornell Grasping Dataset** | 2011 | 885 RGB-D images with 5,110 grasp rectangles on 240 objects | [Website](http://pr.cs.cornell.edu/grasping/rect_data/data.php) |
| **Jacquard** | 2018 | 54 K images and 1.1 M grasp annotations generated in simulation from ShapeNet | [Paper](https://arxiv.org/abs/1803.11469) / [Website](https://jacquard.liris.cnrs.fr) |
| **GraspNet-1Billion** | 2020 | 97,280 RGB-D images, 190 M grasp poses for cluttered real-world scenes | [Paper](https://openaccess.thecvf.com/content_CVPR_2020/papers/Fang_GraspNet-1Billion_A_Large-Scale_Benchmark_for_General_Object_Grasping_CVPR_2020_paper.pdf) / [Website](https://graspnet.net) |
| **EGAD** | 2020 | 2,331 3D-printed objects spanning a complexity and graspability spectrum | [Paper](https://arxiv.org/abs/2003.01314) / [GitHub](https://github.com/dougsm/egad) |
| **DexNet** | 2017–2019 | Large-scale synthetic dataset for robotic dexterous grasping; includes planar and 6-DOF variants | [Website](https://berkeleyautomation.github.io/dex-net) |
| **ACRONYM** | 2020 | 17.7 M grasps for 8,872 objects derived from ShapeNet for dexterous grasp planning | [Paper](https://arxiv.org/abs/2011.09584) / [GitHub](https://github.com/NVlabs/acronym) |

---

## Semantic & Instance Segmentation

| Dataset | Year | Description | Link |
|---------|------|-------------|------|
| **ADE20K** | 2017 | 25 K images, 150 semantic categories; dense pixel-level annotation | [Website](https://groups.csail.mit.edu/vision/datasets/ADE20K) |
| **Cityscapes** | 2016 | 25 K images of urban driving scenes with fine and coarse annotations; 30 semantic classes | [Website](https://www.cityscapes-dataset.com) |
| **ScanNet** | 2017 | 2.5 M RGB-D frames of indoor scenes with 3D instance segmentation labels | [Website](http://www.scan-net.org) |
| **Matterport3D** | 2017 | 194,400 RGB-D images from 90 building-scale indoor environments with mesh and semantic labels | [Paper](https://arxiv.org/abs/1709.06158) / [Website](https://niessner.github.io/Matterport) |
| **OCID** | 2019 | 2,390 RGB-D images of tabletop and floor scenes with instance segmentation for robot manipulation | [Paper](https://arxiv.org/abs/1901.08211) / [GitHub](https://github.com/shaifaliparashar/OCID-dataset) |
| **UOAIS-Sim / UOAIS** | 2021 | Unseen object amodal instance segmentation dataset for robot perception in clutter | [Paper](https://arxiv.org/abs/2109.11103) / [GitHub](https://github.com/gist-ailab/uoais) |

---

## Depth Estimation & RGB-D

| Dataset | Year | Description | Link |
|---------|------|-------------|------|
| **NYU Depth V2** | 2012 | 1,449 RGB-D image pairs of indoor scenes captured with Kinect; standard depth-estimation benchmark | [Website](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html) |
| **SUN RGB-D** | 2015 | 10 K RGB-D images from four sensors with 3D bounding box and semantic annotations | [Website](https://rgbd.cs.princeton.edu) |
| **DIML/CVL RGB-D** | 2021 | High-resolution outdoor and indoor RGB-D images across diverse environments | [Paper](https://arxiv.org/abs/2110.11590) |
| **MegaDepth** | 2018 | 200 K images with depth from SfM reconstructions of 196 Internet photo collections | [Website](https://www.cs.cornell.edu/projects/megadepth) |
| **HRSD** | 2022 | High-resolution stereo dataset with ground-truth depth for robot navigation | [Paper](https://arxiv.org/abs/2204.00740) |

---

## SLAM & 3D Reconstruction

| Dataset | Year | Description | Link |
|---------|------|-------------|------|
| **TUM RGB-D** | 2012 | RGB-D sequences with ground-truth trajectories for SLAM evaluation | [Website](https://vision.in.tum.de/data/datasets/rgbd-dataset) |
| **ICL-NUIM** | 2014 | Synthetic RGB-D sequences of living room and office scenes with ground-truth camera poses | [Website](https://www.doc.ic.ac.uk/~ahanda/VaFRIC/iclnuim.html) |
| **EuRoC MAV** | 2016 | Stereo + IMU sequences from a Micro Aerial Vehicle for visual-inertial odometry and SLAM | [Website](https://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets) |
| **SceneNN** | 2016 | 100 indoor scene meshes with semantic annotation for 3D scene understanding | [Website](http://scenenn.net) |
| **Replica** | 2019 | Photorealistic 3D reconstructions of 18 indoor scenes for embodied AI and SLAM | [Paper](https://arxiv.org/abs/1906.05797) / [GitHub](https://github.com/facebookresearch/Replica-Dataset) |
| **Habitat-Matterport 3D (HM3D)** | 2021 | 1,000 building-scale 3D environments for embodied navigation and SLAM | [Paper](https://arxiv.org/abs/2109.08238) / [Website](https://aihabitat.org/datasets/hm3d) |

---

## Navigation & Autonomous Driving

| Dataset | Year | Description | Link |
|---------|------|-------------|------|
| **KITTI** | 2012 | Stereo, LiDAR, GPS/IMU sequences for odometry, depth, optical flow, object detection, and tracking | [Website](http://www.cvlibs.net/datasets/kitti) |
| **nuScenes** | 2019 | 1,000 driving scenes with 6 cameras, LiDAR, and RADAR for 3D detection and tracking | [Website](https://nuscenes.org) |
| **Waymo Open Dataset** | 2019 | 1,950 segments with LiDAR and camera data for 3D detection and tracking | [Website](https://waymo.com/open) |
| **Gibson** | 2018 | 572 real-world scanned environments for embodied navigation research | [Website](http://gibsonenv.stanford.edu) |
| **MP3D (Matterport3D nav)** | 2017 | Building-scale 3D environments used in PointNav, ObjectNav, and VLN benchmarks | [Website](https://niessner.github.io/Matterport) |
| **R2R (Room-to-Room)** | 2018 | Vision-and-language navigation instructions in Matterport3D environments | [Paper](https://arxiv.org/abs/1711.07280) / [GitHub](https://github.com/peteanderson80/Matterport3DSimulator) |

---

## Multi-Task & Meta-Learning Benchmarks

| Dataset / Benchmark | Year | Description | Link |
|---------------------|------|-------------|------|
| **Meta-World** | 2019 | 50 robotic manipulation tasks for multi-task and meta-reinforcement learning | [Paper](https://arxiv.org/abs/1910.10897) / [Website](https://meta-world.github.io) |
| **RLBench** | 2020 | 100 structured robot manipulation tasks with visual observations for RL and imitation learning | [Paper](https://arxiv.org/abs/1909.12271) / [Website](https://sites.google.com/view/rlbench) |
| **RAVENS** | 2020 | Tabletop manipulation tasks in simulation for transporter network learning | [Paper](https://arxiv.org/abs/2010.14406) / [GitHub](https://github.com/google-research/ravens) |
| **ManipulaTHOR** | 2021 | Embodied object manipulation benchmark in interactive indoor 3D scenes | [Paper](https://arxiv.org/abs/2104.11213) / [Website](https://ai2thor.allenai.org/manipulathor) |
| **BridgeData V2** | 2023 | 60,000 robot demonstrations across 24 environments for generalised robot learning | [Paper](https://arxiv.org/abs/2308.12952) / [Website](https://rail-berkeley.github.io/bridgedata) |
| **Open X-Embodiment** | 2023 | Aggregated dataset of 22 robot embodiments and 527 skills for cross-embodiment learning | [Paper](https://arxiv.org/abs/2310.08864) / [Website](https://robotics-transformer-x.github.io) |

---

## Contributing

Pull requests are welcome. Please follow the existing table format and include:
- Dataset name, year, a short description, and a link to the paper/website.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)