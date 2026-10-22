# PCB image collection

This repository contains **photographs only** for the ReSort AI / Delta Cup PCB
vision project. It does not contain detection labels, train/validation/test splits,
or a training-ready dataset. The files are kept at their source resolution and
have not been cropped or downsampled in this collection.

## Contents

The flat `images/` directory contains 1,588 photographs with source-prefixed,
unique filenames:

| Source | Images | Filename prefix | Notes |
| --- | ---: | --- | --- |
| PCB DSLR | 628 | `dslr_part##_pcb###_rec##` | Seven available parts, 140 physical board IDs; part 8 has not been added. |
| eWaste PCBs Classification v1 | 960 | `ewaste_train_`, `ewaste_valid_`, `ewaste_test_` | Extracted local export; 32 appliance-scene images present in the original ZIP were absent from the curated extracted folders and were not added. |

`image_manifest.csv` records each image's source dataset, original part or split,
board ID when available, byte size, and SHA-256 hash. The prefixes and the
manifest retain provenance, but the eWaste export's split names should **not**
be treated as leakage-safe final splits. Its images are 640-pixel tiles and may
show only part of a PCB or overlap other images.

## Source attribution and usage

- **PCB DSLR Dataset:** C. Pramerdorfer and M. Kampel, “A Dataset for
  Computer-Vision-Based PCB Analysis,” MVA 2015. Dataset record:
  https://doi.org/10.5281/zenodo.3886553 . The record describes availability
  for non-commercial research use and requests citation. The repository owner
  has confirmed permission to publish these copies; the source record does not
  present a general redistribution license.
- **eWaste PCBs Classification v1:** University of Genova, Roboflow Universe,
  https://universe.roboflow.com/university-of-genova-bwt36/ewaste-pcbs-classification-ajtlx/dataset/1 .
  The source lists **CC BY 4.0**. These 960 images were copied from the local
  extracted YOLO26 export; source annotations are not included here.

The two sources have distinct usage terms. This repository does not relicense
third-party images. Consult the source records and the repository owner before
reuse or redistribution.

## Download

Photographs are stored through Git Large File Storage (Git LFS). Install Git
LFS before cloning, then run:

```bash
git lfs install
git clone https://github.com/TonySu1009/Monash_Cup-PLC_RECYCLING_CAMERA.git
```

The PCB DSLR board IDs are retained in filenames so later dataset splits can
keep all views of one physical board together. No inference about component
materials or monetary value should be drawn from visual appearance alone.
