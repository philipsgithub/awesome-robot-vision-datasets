# Awesome Robot Vision Datasets

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated catalogue of vision datasets useful for **robot vision** related to (but not exclusively)
* **few-shot image classification (FSC)**
* **few-shot object detection (FSOD)**
* **few-shot instance segmentation (FSIS)**.

Many datasets listed here were originally designed for adjacent tasks such as 6D pose estimation or multi-view 3D reconstruction, but can potentially used for (qualitatively) testing few-shot perception models.


## Scope

This list focuses on datasets relevant to robot perception. Most entries are object-centric, but the list also includes datasets useful as pretraining or transfer sources for models later deployed in robotic scenarios.

## How to read the tables

- **Original task** describes what the dataset was primarily created for.
- **Labels** summarizes available annotation masks, bounding boxes, parts, or poses.
- **Scale** refers to the number of samples and categories. Note: values are approximate and need to be verified.
- **Refs** are links to the dataset or related publications.
- Some datasets are inaccessible from the public internet and are listed separately at the end. However, directly contacting the authors might help getting access, if the data is still stored somewhere.

## Contents

- [Indoor](#indoor)
  - [Household](#household)
  - [Tools and hardware](#tools-and-hardware)
  - [Warehouse and logistics](#warehouse-and-logistics)
  - [Industrial and texture-less](#industrial-and-texture-less)
  - [Generic indoor scenes and instance recognition](#generic-indoor-scenes-and-instance-recognition)
- [Outdoor](#outdoor)
  - [Vehicles](#vehicles)
  - [Natural species and wildlife](#natural-species-and-wildlife)
  - [Construction sites and PPE](#construction-sites-and-ppe)
- [Studio and turntable captures](#studio-and-turntable-captures)
- [Mixed and unconstrained](#mixed-and-unconstrained)
  - [Generic detection, segmentation, and classification benchmarks](#generic-detection-segmentation-and-classification-benchmarks)
  - [Object counting](#object-counting)
  - [Object-centric and instance retrieval](#object-centric-and-instance-retrieval)
- [Specialised collections](#specialised-collections)
  - [Apparel and fashion](#apparel-and-fashion)
  - [Trash and waste](#trash-and-waste)
  - [Continual learning with few-shot character](#continual-learning-with-few-shot-character)
  - [Food](#food)
  - [Part-level and texture annotations](#part-level-and-texture-annotations)
- [Inaccessible](#inaccessible)
- [Candidates to check](#candidates-to-check)

---

### Indoor

#### Household

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [Active Vision Dataset](https://cs.unc.edu/~ammirato/active_vision_dataset_website/) | Object detection; active vision benchmarking | RGB-D, bbox, image class | ≈20k images / 33 instances | Densely sampled indoor RGB-D captures on a regular camera grid, enabling simulated robot trajectories by re-sampling existing frames. Cluttered multi-object home/office scenes with medium scene diversity.|
| [KITchen](https://kitchen-dataset.github.io/KITchen/) | 6D pose estimation | RGB-D, mask, bbox, 6D pose | ≈210k images / 111 instances | Egocentric humanoid-robot captures in two real kitchens. Focused on non-tabletop settings: cupboards, ovens, dishwashers, shelves, drawers, and fridges.|
| [OpenLORIS-Object](https://lifelong-robotic-vision.github.io/dataset/object) | Continual learning; object recognition | RGB, RGB-D, video, image class, bbox | 40 classes / ≈121 instances | Explicitly varies illumination, occlusion, pixel size, and clutter at three difficulty levels for lifelong-learning evaluation on a RealSense-equipped robot platform. |
| [YCB and YCB-Video](https://www.ycbbenchmarks.com/) | Manipulation benchmark / 6D pose estimation | RGB-D, video, mask, bbox, 6D pose, multi-view | YCB: 77 instances, 600 RGB + 600 RGB-D views/object; YCB-Video: ≈130k images / 21 instances | One of the standard physical object sets for robotic manipulation. YCB-Video reuses 21 of the objects in cluttered tabletop video sequences with frame-level 6D pose ground truth. Often used for detection tasks as well.|

#### Tools and hardware

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [HANDAL](https://nvlabs.github.io/HANDAL/) | Category-level 6D pose estimation with affordance | RGB, video, multi-view, mask, bbox, 6D pose, part affordance | ≈310k images / 17 classes / 212 instances | Robot-graspable tools, semi-automatically annotated from handheld videos. Includes NeRF-style mesh reconstructions and graspable-part labels. Potentially useful for category-level FSC/FSOD.|

#### Warehouse and logistics

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [Amazon Picking Challenge MIT/Princeton Shelf & Tote](https://apc.cs.princeton.edu/) | 6D pose estimation with instance segmentation | RGB-D, multi-view, mask, 6D pose | ≈7.3k images / 39 SKU instances across 452 scenes / ≈2.1k unique poses | Practice and finals captures of the APC 2016 SKU set.|
| [ARMBench](https://armbench.com/) | Instance segmentation / identification | RGB, video, mask, bbox, image class | ≈235k images / ≈190k instances | Pick-and-place captures from an Amazon warehouse. Wide SKU coverage and heavy tote occlusion, all from a single overhead capture.|
| [Products-10K](https://products-10k.github.io/) | Fine-grained SKU/product image classification | RGB, image class | ≈190k images / ≈10k classes | SKU-level product recognition from JD.com with hierarchical categories. Studio/catalog photography rather than robot capture, but the SKU set is representative of warehouse picking.|

#### Industrial and texture-less

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [IMD (Industrial Metallic Dataset)](https://arxiv.org/abs/2509.11680) | 6D pose estimation | RGB-D, mask, 6D pose | ≈22k images / 45 instances | Reflective metallic CAD-paired parts captured by a robot-mounted RGB-D sensor under top-down and 45° views. Auto-annotated with SAM2.|
| [LINEMOD](https://bop.felk.cvut.cz/datasets/) | 6D pose estimation | RGB, RGB-D, mask, bbox, 6D pose | ≈18k images / 15 instances | RGB-D 6D-pose benchmark for texture-less objects. The limited real training data per object historically encouraged synthetic augmentation. |
| [MR6D](https://huggingface.co/datasets/anas-gouda/mr6d) | 6D pose estimation | RGB, RGB-D, mask, 6D pose | ≈8.5k images / 16 instances | Targets mobile-robot challenges such as long range, extreme viewpoints, and occlusion on industrial parts. Covers both static and dynamic interactions. |
| [T-LESS](https://cmp.felk.cvut.cz/t-less/) | 6D pose estimation | RGB-D, mask, 6D pose | ≈49k images / 30 instances | Texture-less industrial parts with shape symmetries and part-of relations. Part of the (BOP benchmark)[https://bop.felk.cvut.cz/home/], which contains many more datasets for industrial-related tasks.|

#### Generic indoor scenes and instance recognition

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [InsDet](https://insdet.github.io/) | Instance retrieval / recognition; instance detection | RGB, multi-view, mask, bbox, image class | ≈2.4k profile images + 160 scene images / 100 instances | 100 object instances captured turntable-style on white background, then placed in 160 high-resolution cluttered scenes.|
| [OCID (Object Clutter Indoor Dataset)](https://www.acin.tuwien.ac.at/en/vision-for-robotics/software-tools/object-clutter-indoor-dataset/) | Instance segmentation | RGB-D, point-wise mask, point cloud | ≈2.3k labelled point clouds / up to 20 objects/scene | Built with the EasyLabel semi-automatic tool. Clutter is graded by adding objects one at a time, so the same scene appears at multiple difficulty levels. Limited object-model variety.|
| [OCID-Ref](https://github.com/lluma/OCID-Ref) | Referring-expression grounding; object detection | RGB, RGB-D, bbox, text, attributes, relations | ≈2.3k scenes / ≈310k referring expressions | Extends OCID with visual attributes and spatial/colour relations, with a focus on grounding occluded targets using 2D and 3D information.|
| [STIOS (Stereo Instances on Surfaces)](https://www.dlr.de/en/rm/research/publications-and-downloads/datasets/stereoinstancesonsurfaces) | Unknown-object instance segmentation | RGB, RGB-D, stereo multi-view, mask, image class | ≈190 stereo pairs per sensor | Evaluation-only set, no training split. Covers textureless and texture-rich surfaces for stereo and RGB-D segmentation.|
| [UW-IS Occluded](https://figshare.com/articles/dataset/UW_Indoor_Scenes_UW-IS_Occluded_Dataset/20506506) | Object detection / instance recognition | RGB-D, video, bbox, mask, 6D pose | ≈8.5k images / 20 classes / ≈43k instances | Successor to the original UW-IS dataset. Robot-eye RealSense D435 capture across lounge and warehouse scenes with explicit illumination and occlusion variation.|

---

### Outdoor

#### Vehicles

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [FGVC-Aircraft](https://www.robots.ox.ac.uk/~vgg/data/fgvc-aircraft/) | Fine-grained image classification | RGB, image class, bbox | ≈10k images / 102 variant classes / 70 families / 41 manufacturers | Three-level hierarchy of aircraft variant, family, and manufacturer. Usually one object per image with sky or apron backgrounds.|
| [Stanford Cars](https://www.tensorflow.org/datasets/catalog/cars196) | Fine-grained image classification | RGB, image class, bbox | ≈16k images / 196 classes | Model/year fine-grained recognition. The dataset is provided via mirrors such as TensorFlow Datasets.|

#### Natural species and wildlife

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [CUB-200-2011](https://www.vision.caltech.edu/datasets/cub_200_2011/) | Fine-grained image classification | RGB, image class, bbox, mask, 15 part keypoints, 312 binary attributes | ≈11.8k images / 200 classes | Popular fine-grained recognition and part-localisation benchmark. The part keypoints and binary attributes provide semantic supervision beyond class labels.|
| [iNaturalist 2021](https://github.com/visipedia/inat_comp/tree/master/2021) | Fine-grained species classification | RGB, image class | ≈2.7M train + 100k val + 500k test images / 10k classes | Geographically diverse citizen-science imagery with clutter, foliage, and occlusion. The 2021 release is class-balanced at roughly 300 train images per species; a mini variant with 50 samples per species is also available.|

#### Construction sites and PPE

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [CIS (Construction Instance Segmentation)](https://github.com/XZ-YAN/CIS-Dataset) | Instance segmentation | RGB, mask, bbox, image class | CISv1: ≈50k images / 10 classes / ≈104k instances; CISv2: ≈61k images / 10 classes / ≈114k instances | Construction-site classes: workers with/without helmet, dump trucks, concrete-mixer trucks, excavators, rollers, dozers, wheel loaders, PC delivery trucks, and precast components. Rare outdoor benchmark with both equipment classes and FSIS-quality annotations.|
| [SH17](https://github.com/ahmadmughees/SH17dataset) | Object detection for PPE compliance | RGB, bbox, image class | ≈8.1k images / 17 classes / ≈76k instances | A generic tools class plus helmets, vests, gloves, ear-muffs, face guards, medical suits, and safety suits. Based on heterogeneous Pexels stock imagery; viewpoint is photographer-style rather than mobile-robot. Hosted on Kaggle.|
| [SODA (Site Object Detection dAtaset)](https://linjiarui.net/en/portfolio/2022-02-22-SODA-site-object-detection-dataset-for-deep-learning-in-construction) | Object detection | RGB, bbox, image class | ≈19.8k images / 15 classes / ≈286k instances | Ground-level handheld captures from Chinese construction sites across weather and construction phases. Classes: workers, helmets, vests, materials, electric boxes, and heavy machines.|

---

### Studio and turntable captures

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [BigBIRD](https://rll.berkeley.edu/bigbird/) | Instance retrieval / recognition | RGB, RGB-D, multi-view, mask, calibrated 6D pose | ≈75k images / 125 instances | 12 MP studio captures with 5 cameras plus depth at 600 calibrated viewpoints. Mostly packaged retail goods. Project page is partially unreachable; mirrors seem to exist.|
| [DTU MVS](http://roboimagedata.compute.dtu.dk/?page_id=36) | Multi-view 3D reconstruction | RGB, multi-view, structured-light reference points | 124 scenes × 49–64 calibrated views / ≈7.4k images | Robot-arm acquisition with seven lighting conditions per scene. Lab-controlled MVS benchmark.|
| [KIT 3D Object Models database](https://h2t.iar.kit.edu/english/1329.php) | Instance retrieval / recognition; 3D models for manipulation | RGB, multi-view, silhouettes, 3D model | ≈100 instances with densely sampled viewpoints | Semi-automatic turntable rig producing calibrated multi-view images, triangulated point clouds, and pre-computed grasp data.|
| [The Met Dataset](https://cmp.felk.cvut.cz/met/) | Instance retrieval / recognition for artworks | RGB, image class | ≈400k images / ≈224k classes | Long-tail benchmark with one class per exhibit and strong train/test distribution shift from studio images to visitor photos.|
| [RGB-D Object Dataset](https://rgbd-dataset.cs.washington.edu/) | Image classification and instance recognition | RGB-D, video, multi-view, image class, mask | ≈210k images / 51 classes / 300 instances | Early large-scale Kinect RGB-D dataset with hierarchical WordNet categories. Combines turntable captures with a small set of cluttered evaluation scenes.|

---

### Mixed and unconstrained

#### Generic detection, segmentation, and classification benchmarks

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [CD-FSOD](https://github.com/lovelyqian/CDFSOD-benchmark) | Cross-domain few-shot object detection | RGB, bbox | Target-specific: ArTaxOr, Clipart1k, DeepFish, DIOR, NEU-DET, UODD | Aggregates target domains with COCO as source for `K`-shot evaluation, explicitly exposing domain-shift failure modes of FSOD. There is a corresponding CVPR challenge [NTIRE](https://www.codabench.org/competitions/12873/).|
| [CIFAR-FS / FC100](https://github.com/bertinetto/r2d2) | Few-shot classification | RGB, image class | 60k images / 100 classes at 32×32 | Both are derived from CIFAR-100. CIFAR-FS uses a random 64/16/20 class split, while FC100 uses 60/20/20 classes from disjoint super-classes to reduce semantic leakage. |
| [FSOD-1000](https://github.com/fanq15/Few-Shot-Object-Detection-Dataset) | Few-shot object detection | RGB, bbox, image class | ≈66k images / 1k classes / ≈182k instances | Purpose-built FSOD benchmark. Uses 800 train and 200 test categories; test categories are chosen to maximise semantic distance from train categories. Low-quality boxes are pruned for support-set quality. |
| [LVIS](https://www.lvisdataset.org/) | Instance segmentation | RGB, mask, bbox, image class | ≈160k images / ≈1.2k classes / ≈2M instances | Federated long-tail re-annotation of COCO 2017 with high-quality boundary masks. The rare/common/frequent split is routinely used as an implicit few-shot benchmark. |
| [Meta-Dataset](https://github.com/google-research/meta-dataset) | Few-shot classification | RGB, image class; MSCOCO crops indirectly use bbox | Aggregate of 10 source datasets, dominated by ILSVRC-2012 with ≈1.28M images | Cross-domain few-shot benchmark. Sources: Omniglot, Aircraft, CUB-200-2011, DTD, Quick Draw, Fungi, VGG Flower, Traffic Signs, MSCOCO, and ILSVRC-2012. Tasks vary in way, shot, and class balance. |
| [mini-ImageNet](https://github.com/yaoyao-liu/mini-imagenet-tools) | Few-shot classification | RGB, image class | ≈60k images at 84×84 / 100 classes / 64/16/20 split | Widely-used few-shot benchmark. Downsampled from ImageNet and not officially redistributed; typically regenerated from full ImageNet. |
| [COCO](https://cocodataset.org/) | Instance segmentation, detection, captioning, keypoints | RGB, mask, bbox, image class, captions, keypoints | ≈330k images / 80 classes / ≈2.5M instances | The dominant general-purpose detection/segmentation benchmark. FSOD and FSIS literature commonly re-splits COCO into base/novel class subsets, for example 60/20.|
| [Objects365](https://www.objects365.org/overview.html) | Object detection | RGB, bbox, image class | ≈2M images / 365 classes / ≈30M instances | Large-scale detection benchmark with manually verified bounding boxes. Widely used as a pre-training corpus, so care is needed when evaluating models whose backbones may have seen it.|
| [ODinW-35](https://eval.ai/web/challenges/challenge-page/1839/overview) | In-the-wild object detection | RGB, bbox, class names as text prompts | ≈27k images / ≈300 heterogeneous classes | Suite of 35 Roboflow datasets proposed alongside GLIP/GLIPv2. Per-task training sizes range from ≈17 to >32k images, naturally supporting cross-domain FSOD evaluation.|
| [Pascal VOC](http://host.robots.ox.ac.uk/pascal/VOC/) | Object detection, classification, semantic segmentation | RGB, bbox, segmentation masks, image class | VOC07: ≈9.96k images / 20 classes / ≈25k instances; VOC12: ≈11.5k images / 20 classes | Historical reference benchmark. The `N`-shot splits derived from VOC07+12 remain common in FSOD.|
| [tieredImageNet](https://github.com/renmengye/few-shot-ssl-public) | Few-shot classification | RGB, image class | ≈779k images / 608 classes | Hierarchical ImageNet split with disjoint train/val/test super-categories. Creates a much harder semantic gap than mini-ImageNet. |

#### Object counting

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [FSC-147](https://github.com/cvlab-stonybrook/LearningToCountEverything) | Few-shot object counting | RGB, point/dot, 3 exemplar boxes per image | ≈6.1k images / 147 classes / avg. ≈59 instances per image | First large few-shot counting benchmark. All instances are dot-marked; only three exemplar boxes are provided per image.|
| [FSCD-147](https://github.com/VinAIResearch/Counting-DETR) | Few-shot object detection / counting | RGB, bbox, point/dot | ≈6.1k images / 147 classes | Successor to FSC-147 that adds full bounding-box annotations on val/test for joint counting and detection evaluation.|

#### Object-centric and instance retrieval

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [Google Objectron](https://github.com/google-research-datasets/Objectron) | 6D pose estimation; 3D bbox / 9-DoF | RGB, video, multi-view, bbox, 6D pose | ≈4M images / 9 classes / ≈15k instances | Mobile-AR scans for 9 household categories. In-the-wild indoor and outdoor capture, but biased toward a single object centered in the frame with limited clutter.|
| [INRIA Holidays](https://lear.inrialpes.fr/~jegou/data.php) | Instance retrieval / recognition | RGB, scene-group image class | ≈1.5k images / 500 instance scene groups | Hand-curated holiday photos with rotation, viewpoint, illumination, and blur variation. Small dataset; useful as a robustness probe.|

---

### Specialised collections

#### Apparel and fashion

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [Clothing dataset small](https://github.com/alexeygrigorev/clothing-dataset-small) | Image classification | RGB, image class | ≈3.8k images / 10 classes | CC0 educational subset of a larger 5k-image clothing dataset. Top-10 classes only, pre-resized, with train/val/test split provided. Can be used for texture-concept analysis.|
| [DeepFashion](http://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html) | Image classification, attribute prediction, retrieval, landmark detection | RGB, image class, bbox, attributes, landmarks | ≈800k images / 50 classes / ≈1k attributes | Canonical multi-task fashion dataset with shop and consumer imagery. Four sub-benchmarks cover attribute prediction, in-shop retrieval, consumer-to-shop retrieval, and landmark detection.|

#### Trash and waste

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [SeaClear Marine Debris](https://data.4tu.nl/datasets/4f1dff25-e157-4399-a5d4-478055461689) | Instance segmentation and detection | RGB, video, mask, bbox, image class | ≈8.6k images / 40 classes | Captured by a mobile underwater ROV. Categories: bottles, cans, fishing nets, ropes, tires, plastic bags, ROV parts, and marine fauna/flora. Long-tailed by class.|
| [TACO (Trash Annotations in Context)](http://tacodataset.org/) | Instance segmentation | RGB, mask, bbox, image class | ≈1.5k images / 60 classes / ≈4.8k instances | COCO-style segmentation of litter in the wild. Dominated by cans, bottles, and plastic bags.|

#### Continual learning with few-shot character

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [CORe50](https://vlomonaco.github.io/core50/) | Continual learning; object recognition | RGB, RGB-D, video, image class | ≈165k images / 10 classes / 50 instances | 11 acquisition sessions per object provide an explicit domain-shift axis for new-instance and new-class continual-learning protocols.|

#### Food

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [FoodX-251](https://github.com/karansikka1/iFood_2019) | Fine-grained food image classification | RGB, image class | ≈161k images / 251 classes | Dish-level recognition with deliberately noisy training labels and clean human-verified validation/test splits. Intended for noisy-label and fine-grained benchmarking. |

#### Part-level and texture annotations

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [DTD (Describable Textures Dataset)](https://www.robots.ox.ac.uk/~vgg/data/dtd/) | Texture recognition | RGB, image class, attribute | ≈5.6k images / 47 classes | Widely used as a few-shot transfer target. 120 images per attribute, sized roughly 300×300 to 640×640. |
| [PartImageNet](https://github.com/TACJu/PartImageNet) | Part-level semantic segmentation | RGB, mask, part, image class | ≈24k images / 158 classes / 11 super-categories | An order of magnitude larger than prior part datasets. Covers non-rigid articulated objects for 158 ImageNet classes. |

---

### Inaccessible

Frequently cited but currently inaccessible.

| Dataset | Original task | Labels | Scale | Notes |
|---|---|---:|---:|---|
| [ARID (Autonomous Robot Indoor Dataset)](https://www.acin.tuwien.ac.at/en/vision-for-robotics/software-tools/autonomous-robot-indoor-dataset/) | Object detection / instance recognition | RGB-D, bbox, image class | ≈6k images / 51 classes / 153 instances | Autonomously collected by a mobile robot. The web extension WOD is currently unreachable.|
| [SMOT](https://www.acin.tuwien.ac.at/en/vision-for-robotics/software-tools/smot/) | 6D pose estimation | RGB-D, video, mask, 6D pose | 2 train + 11 test sequences / 8 instances | Single-sequence multi-object capture. Pose annotations are reconstruction-derived rather than manually adjusted.|
| [TUW / Willow / Challenge](https://www.acin.tuwien.ac.at/en/vision-for-robotics/software-tools/tuw-object-instance-recognition-dataset/) | 6D pose estimation / instance recognition | RGB-D, multi-view, 6D pose, image class | TUW: 17 models, 15 static + 3 dynamic scenes; Willow: 35 models / 353 frames / ≈1.6k instances; Challenge: 176 frames / ≈430 instances | Three related multi-view RGB-D collections from ACIN TU Wien with partly textureless and symmetric models and a semi-automated ground-truth annotation pipeline.|

---

### Candidates to check

These should be verified before transfering to the main list.

| Dataset / source | Why it may be relevant |
|---|---|
| THUD++ | Large-scale dynamic indoor scene dataset for mobile robots; object categories may be too general|
| ScanNet++ | Rich indoor 3D reconstruction/scene-understanding resource; similar motivation to THUD++ |
| Google Landmarks v2 | Potential fine-grained instance recognition / retrieval benchmark|
| Caltech101 | Classic object classification dataset; useful mostly as a historical FSC target|
| Oxford-IIIT Pets | Fine-grained pet breed classification |
| SUN397 | Scene classification; less object-centric, but useful for domain-shift evaluation |
| EuroSAT | Remote-sensing classification; common cross-domain few-shot benchmark |
| CompCars | Fine-grained car recognition with hierarchy|
| DOTA | Aerial object detection with oriented boxes and fine-grained categories |
| AI2D | Diagram understanding with object annotations |

## Contributing

Dataset suggestions and corrections are welcome. Please have a look at [CONTRIBUTING.md](CONTRIBUTING.md).

## License

This repository is licensed under the [MIT License](LICENSE).
It is intended as a curated index and does not contain any data.

**Important:** Dataset licenses are controlled by the original dataset authors and providers.
Please check each dataset page before use and remember to cite the authors' publications related to the datasets in case you use them for your research.
