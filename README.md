# Deep Learning Final Project- Super-Resolution (DIV2K)

This repository contains the final project for the course "Deep Learning and Its Applications to Signal and Image Processing and Analysis" (361.2.1120).

**Submitted by**: Bar Naor (318477809) and Jacob Maimon (313612400)  
**Submission Date**: 13.07.2025

## Project Description

The task focuses on DIV2K Dataset Enhance to the resolution of low-quality images by training a model on 4×downsampled versions of high-resolution images, with the goal of accurately restoring fine details and texture. The evaluation metrics used are PSNR, SSIM and FID.

Two models were implemented and compared:

- **Model 1**: A vanilla FSRCNN implementation (baseline).
- **Model 2**: A variation of FSRCNN that includes:
  - A residual bicubic upsampling branch.
  - A combined loss function with MSE and VGG-based perceptual loss.

An ablation study was also conducted to evaluate the impact of the perceptual loss component.

## Files

- `deep_learning_final_project_361.2.1120_Bar_Naor_Jacob_Maimon.ipynb`: Main notebook with training, evaluation, and analysis.
- `README.md`: Instructions for running the project.

## How to Run

The notebook is designed to be run in Google Colab. All dependencies are installed within the notebook.

**Important**: In block 3 of the notebook, the user must upload their `kaggle.json` API key file. This is required to download the DIV2K dataset from Kaggle.

Steps:

1. Open the notebook in Google Colab.
2. Run the cells sequentially.
3. When prompted (on the third block), upload your `kaggle.json` file.
4. The dataset will be downloaded and extracted automatically.
5. Continue to run the remaining cells from top to bottom. The notebook includes:
   - Dataset loading and preprocessing.
   - Model architecture definitions.
   - Training for both models across three seeds.
   - Evaluation on validation and test sets after each training run.
   - Computation of PSNR, SSIM, and FID metrics.
   - Calculation of mean and standard deviation across seeds for all metrics.
   - Visualization of training curves and test results.
   - Qualitative image comparisons between models.
   - Ablation study and corresponding analysis.

## Requirements

The following libraries are installed automatically in the notebook:
- torch
- torchvision
- torchmetrics
- torch-fidelity
- numpy
- matplotlib
- PIL
- kaggle

There is no need to manually install these packages when using Google Colab.

## Notes

- All paths are relative and organized within the notebook runtime environment.
- The notebook saves results and images to folders like `model1_results`, `model2_examples`, and `ablation_results`.
- Evaluation is performed using both quantitative metrics and qualitative examples.
- Final results are aggregated and compared across seeds.
