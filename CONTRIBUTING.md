# Contributing

Thanks for helping improve **Awesome Robot Vision Datasets**.

This repository is intended to be a curated catalogue of datasets for robot vision, with a focus on object-centric tasks and low-data regimes.

## How to suggest a dataset

You can contribute by opening an issue or pull request.

A useful dataset suggestion should include:

```markdown
#### Dataset Name

- **Link:** https://...
- **Original task:** e.g. object detection, instance segmentation, 6D pose estimation
- **Category type:** e.g. household, tools, warehouse, industrial, vehicles, wildlife
- **Environment:** indoor / outdoor / mixed / studio
- **Clutter:** yes / no / partial
- **Scene diversity:** low / medium / high
- **Data/Labels:** RGB, RGB-D, bbox, mask, class label, 6D pose, video, multi-view, etc.
- **Scale:** number of images, classes, instances, scenes, or videos
- **Refs:** optional DOI or paper link

Short description of why the dataset is useful and what is special about it. Alays helpful are comparisons to existing or popular datasets.
```

## Dataset criteria

A dataset is a good fit if it satisfies several of the following:

- It is relevant to robot vision, object-centric perception, or few-shot evaluation.
- It has useful annotations such as class labels, bounding boxes, masks, depth, poses, parts, attributes, or multi-view captures.
- It is publicly documented and, ideally, downloadable.
- It contains challenging conditions such as clutter, occlusion, domain shift, rare categories, long-tail distributions, or realistic robot viewpoints.
- It is commonly used in the literature or fills a clear gap in existing benchmarks.


## What not to add

Please avoid:

- Commercial datasets without public documentation.
- Promotional entries without technical metadata.
