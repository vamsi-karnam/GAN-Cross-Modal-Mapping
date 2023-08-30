# Cross-Modal Mapping with Pix2Pix GAN
This repository contains code for training and evaluating a Pix2Pix GAN model to perform cross-modal mapping between sensor data and visual images. The model is trained on two real-time continuous datasets - an underwater shipwreck dataset containing Sonar scans and images, and an aerial dataset containing LiDAR maps and photographs.


### Methodology

The model architecture follows the original Pix2Pix GAN formulation with a U-Net generator and PatchGAN discriminator. The code was developed using Python 3.6 with TensorFlow 2.0 and OpenCV. 
Two models are evaluated:

1. Baseline model with default hyperparameters of the original pix2pix model [3].
2. Modified model with increased batch size (BATCH_SIZE = 4)

Performance is compared using structural similarity (SSIM) between generated and real images. Qualitative inspection is also performed.


### Results

Key findings:

1. Slightly increasing the batch size improved training stability and reduced mode collapse.
2. Model with batch size of 4 performed better both quantitatively and qualitatively.
3. Approach shows promise for cross-modal mapping tasks using continuous data.

To download the checkpoints containing model weights, follow the links below.

- [shipwreck data model](https://mega.nz/folder/uVcgRbCL#n_pWXaeslc8o-iJARUq5Rw)
- [map data model](https://mega.nz/folder/eB8RQQYZ#Lun6gqoyss876H07y80ZBw)

A video was generated from both the original and augmented frame data, demonstrating a promising approach to generating missing data through cross-modal mapping using a pix2pix GAN, the link below redirects to the video.

[Frames generation](https://vimeo.com/858667797)


### References

Data sources:

[1] [Shipwreck-dataset](https://gite.lirmm.fr/shipwreck/shipwreck-dataset)
> N. Pecheux, V. Creuze, F. Comby and O. Tempier, “Self-Calibration of a Sonar–Vision System for Underwater Vehicles: A New Method and a Dataset”, Sensors, vol. 23, no. 3, p. 1700, Feb. 3, 2023

[2] [MapAI dataset](https://huggingface.co/datasets/sjyhne/mapai_dataset)
> S. Jyhne, M. Goodwin, P.-A. Andersen, I. Oveland, A. S. Nossum, K. Ormseth, M. Ørstavik and A. C. Flatman, “MapAI: Precision in Building Segmentation,” Nordic Machine Intelligence, vol. 2, no. 3, pp. 1-3, Sep. 2022.

[3] [Pix2Pix](https://www.tensorflow.org/tutorials/generative/pix2pix)
> P. Isola, J. -Y. Zhu, T. Zhou and A. A. Efros, "Image-to-Image Translation with Conditional Adversarial Networks," 2017 IEEE Conference on Computer Vision and Pattern Recognition (CVPR), Honolulu, HI, USA, 2017, pp. 5967-5976, doi: 10.1109/CVPR.2017.632.
