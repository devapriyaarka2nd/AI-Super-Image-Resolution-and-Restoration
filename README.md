# AI Super-Resolution and Image Restoration

A deep learning-based image restoration pipeline combining
Super-Resolution, Denoising, and Image Colorization.

## Overview

This project implements a multi-stage image restoration pipeline
using PyTorch and OpenCV.

The system performs:

1. Single Image Super-Resolution using SRCNN
2. Image Denoising using Non-Local Means
3. Image Colorization using a lightweight U-Net

However, this is a prototype & the results here are not quite promising. Subsequent updates and enhancements to the existing pipeline will be released in future iterations.

## Pipeline

Input Image
↓
Image Degradation
↓
Bicubic Upsampling
↓
SRCNN Super-Resolution
↓
Non-Local Means Denoising
↓
U-Net Colorization
↓
Restored Image

## Dataset

The project uses the DIV2K dataset.

Training:
- 800 images

Validation:
- 100 images

The dataset is not included in this repository.

## Models

### SRCNN

The SRCNN architecture consists of:

- Conv2D: 1 → 64, 9×9
- ReLU
- Conv2D: 64 → 32, 5×5
- ReLU
- Conv2D: 32 → 1, 5×5

### Colorization U-Net

A lightweight U-Net is used to predict the `ab`
color channels from the LAB `L` channel.

## Evaluation

Super-resolution performance is evaluated using:

- PSNR
- SSIM
### Super-Resolution Performance

The trained SRCNN model was evaluated on the DIV2K validation set using PSNR and SSIM. Bicubic interpolation was used as the baseline.

| Method | PSNR (dB) | SSIM |
|---|---:|---:|
| Bicubic | 26.1938 | 0.8600 |
| SRCNN | **26.4896** | **0.8725** |

SRCNN achieved an improvement of **+0.2958 dB in PSNR**
and **+0.0125 in SSIM** over bicubic interpolation.

The SRCNN reconstruction is compared against
bicubic interpolation.

## Results


## Technologies

- Python
- PyTorch
- OpenCV
- NumPy
- scikit-image
- Matplotlib
- Kaggle GPU

## How to Run

1. Download the repository.
2. Download the DIV2K dataset.
3. Open the notebook.
4. Update `DATASET_DIR`.
5. Enable GPU acceleration.
6. Run the notebook sequentially.

## Project Structure

...

## Future Improvements  
Just a raw initial plan will see more in future 

- EDSR
- ESRGAN / Real-ESRGAN
- Perceptual loss
- LPIPS evaluation
- Larger training patches
- Advanced denoising networks
- Transformer-based restoration
- EDSR
- ESRGAN / Real-ESRGAN
- Perceptual loss
- LPIPS evaluation
- Larger training patches
- Advanced denoising networks
- Transformer-based restoration
