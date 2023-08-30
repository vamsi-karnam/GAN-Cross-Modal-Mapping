# Cross-Modal Mapping with Pix2Pix GAN
This repository contains code for training and evaluating a Pix2Pix GAN model to perform cross-modal mapping between sensor data and visual images. The model is trained on two real-time continuous datasets - an underwater shipwreck dataset containing Sonar scans and images, and an aerial dataset containing LiDAR maps and photographs.


### Methodology

The model architecture follows the original Pix2Pix GAN formulation with a U-Net generator and PatchGAN discriminator. Two models are evaluated:

1. Baseline model with default hyperparameters
2. Modified model with increased batch size
Performance is compared using structural similarity (SSIM) between generated and real images. Qualitative inspection is also performed.


### Results

Key findings:

1. Slightly increasing the batch size improved training stability and reduced mode collapse.
2. Model with batch size of 4 performed better both quantitatively and qualitatively.
3. Approach shows promise for cross-modal mapping tasks using continuous data.

To download the checkpoints containing model weights, follow the links below.
Model weights:
- [shipwreck data model](https://mega.nz/folder/uVcgRbCL#n_pWXaeslc8o-iJARUq5Rw)
- [map data model](https://mega.nz/folder/eB8RQQYZ#Lun6gqoyss876H07y80ZBw)


### References

Data sources:

[Shipwreck-dataset](https://gite.lirmm.fr/shipwreck/shipwreck-dataset)
> N. Pecheux, V. Creuze, F. Comby and O. Tempier, “Self-Calibration of a Sonar–Vision System for Underwater Vehicles: A New Method and a Dataset”, Sensors, vol. 23, no. 3, p. 1700, Feb. 3, 2023

[MapAI dataset](https://huggingface.co/datasets/sjyhne/mapai_dataset)
> S. Jyhne, M. Goodwin, P.-A. Andersen, I. Oveland, A. S. Nossum, K. Ormseth, M. Ørstavik and A. C. Flatman, “MapAI: Precision in Building Segmentation,” Nordic Machine Intelligence, vol. 2, no. 3, pp. 1-3, Sep. 2022.
