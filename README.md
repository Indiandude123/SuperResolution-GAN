# SRGAN (Super-Resolution GAN) on a Custom Dataset

This repository provides an implementation of **SRGAN (Super-Resolution GAN)** trained on a custom dataset.  
It allows you to train the model with your own **Low Resolution (LR)** and **High Resolution (HR)** image pairs.

---

## Environment Setup

First, navigate to the project directory in your **Anaconda Prompt** where you have the `environment.yml` file.

```bash
conda env create -f environment.yml
conda activate srganenv_gpu
```

### Install PyTorch

Choose the installation command that suits your system resources.

#### GPU Version

```bash
conda install pytorch==1.1.0 torchvision==0.3.0 cudatoolkit=10.0 -c pytorch
```

#### CPU Only

```bash
conda install pytorch-cpu==1.1.0 torchvision-cpu==0.3.0 cpuonly -c pytorch
```

---

## Train the Model

Replace the dataset paths with the paths to your custom dataset.

**Example:**

```bash
python main.py --LR_path custom_dataset_cars/hr_train_LR --GT_path custom_dataset_cars/hr_train_HR
```

---

## Test the Model

Run inference using your test dataset and a pretrained generator model.

**Example:**

```bash
python main.py --mode test_only --LR_path test_data/cars --generator_path ./model/srgan_custom.pt
```

---

## Custom Dataset Structure

Your custom dataset should follow this specific format to be used with the training script:

```
custom_dataset_cars/
├── hr_train_LR/
│   ├── img1.png
│   ├── img2.png
│   └── ...
└── hr_train_HR/
    ├── img1.png
    ├── img2.png
    └── ...
```

---
