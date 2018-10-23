Memory Replay GANs: learning to generate images from new categories without forgetting
=====================================
The paper has been accepted in NIPS 2018. An [arXiv pre-print](https://arxiv.org/abs/1809.02058) version is available. 

## Abstract
Previous works on sequential learning address the problem of forgetting in discriminative models. In this paper we consider the case of generative models. In particular, we investigate generative adversarial networks (GANs) in the task of learning new categories in a sequential fashion. We first show that sequential fine tuning renders the network unable to properly generate images from previous categories (i.e. forgetting). Addressing this problem, we propose Memory Replay GANs (MeRGANs), a conditional GAN framework that integrates a memory replay generator. We study two methods to prevent forgetting by leveraging these replays, namely joint training with replay and replay alignment. Qualitative and quantitative experimental results in MNIST, SVHN and LSUN datasets show that our memory replay approach can generate competitive images while significantly mitigating the forgetting of previous categories

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



## Citation

Please cite our paper if you are inspired by the idea.

```
@inproceedings{chenshen2018mergan,
title={Memory Replay GANs: learning to generate images from new categories without forgetting},
author={Wu, Chenshe and Herranz, Luis and Liu, Xialei and Wang, Yaxing and van de Weijer, Joost and Raducanu, Bogdan },
booktitle={Conference on Neural Information Processing Systems (NIPS)},
year={2018}
}



