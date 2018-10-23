Memory Replay GANs: learning to generate images from new categories without forgetting
=====================================

Code for reproducing experiments in ["Memory Replay GANs: learning to generate images from new categories without forgetting"](https://arxiv.org/abs/1809.02058).


## Prerequisites

- Python 2.7, NumPy, TensorFlow 1.4, SciPy, Matplotlib
- A recent NVIDIA GPU

## Models

For training:
- `python main.py --dataset mnist --result_path mnist_SFT/` Sequential Fine Tuning
- `python main.py --dataset mnist --RA --RA_factor 1e-3  --result_path mnist_RA_1e_3/` MerGAN Replay Alignment
- `python main.py --dataset mnist --JTR --result_path mnist_JTR/` MerGAN Joint Training with Replay
- `python joint.py --dataset mnist --result_path mnist_joint/` Joint Training

For testing:
- `python main.py --dataset mnist --test  --result_path result/mnist_RA_1e_3/`
- `python joint.py --dataset mnist --test --result_path result/mnist_joint/`
