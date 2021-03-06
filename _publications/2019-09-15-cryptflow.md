---
title: "CrypTFlow: Secure TensorFlow Inference"
collection: publications
permalink: /publication/2019-09-15-cryptflow
excerpt: 'We present CrypTFlow, a first of its kind system that converts TensorFlow inference code into Secure Multi-party Computation (MPC) protocols at the push of a button. The system enables secure inference on real-world networks like ResNet50 over the ImageNet dataset with running time of about 30 seconds for semi-honest security and under 2 minutes for malicious security.'
date: 2019-09-15
year: 2020
venue: IEEE Symposium on Security and Privacy (S&P)
authors: 'Nishant Kumar, Mayank Rathee, Nishanth Chandran, Divya Gupta, Aseem Rastogi & Rahul Sharma'
eprint: 'https://eprint.iacr.org/2019/1049'
bib: 'https://eprint.iacr.org/eprint-bin/cite.pl?entry=2019/1049'
code: 'https://github.com/mpc-msri/EzPC'
---
We present CrypTFlow, a first of its kind system that converts TensorFlow inference code into Secure Multi-party Computation (MPC) protocols at the push of a button. To do this, we build three components. Our first component, Athos, is an end-to-end compiler from TensorFlow to a variety of semi-honest MPC protocols. The second component, Porthos, is an improved semi-honest 3-party protocol that provides significant speedups for Tensorflow like applications. Finally, to provide malicious secure MPC protocols, our third component, Aramis, is a novel technique that uses hardware with integrity guarantees to convert any semi-honest MPC protocol into an MPC protocol that provides malicious security. The security of the protocols output by Aramis relies on hardware for integrity and MPC for confidentiality. Moreover, our system, through the use of a new float-to-fixed compiler, matches the inference accuracy over the plaintext floating-point counterparts of these networks.

We experimentally demonstrate the power of our system by showing the secure inference of real-world neural networks such as ResNet50, DenseNet121, and SqueezeNet over the ImageNet dataset with running times of about 30 seconds for semi-honest security and under two minutes for malicious security. Prior work in the area of secure inference (SecureML, MiniONN, HyCC, ABY3, CHET, EzPC, Gazelle, and SecureNN) has been limited to semi-honest security of toy networks with 3--4 layers over tiny datasets such as MNIST or CIFAR which have 10 classes. In contrast, our largest network has 200 layers, 65 million parameters and over 1000 ImageNet classes. Even on MNIST/CIFAR, CrypTFlow outperforms prior work.

## Updates
- <span style="color:#fa4d4d">[Feb '20]</span> CrypTFlow has been accepted at [IEEE Symposium on Security and Privacy (S&P), 2020](https://www.ieee-security.org/TC/SP2020/).
- <span style="color:#fa4d4d">[May '20]</span> I [presented](https://www.youtube.com/watch?v=53rxhEmDqQk) our work on CrypTFlow at IEEE S&P, 2020.

## Links:
1. [eprint](https://eprint.iacr.org/2019/1049)
2. [arXiv](https://arxiv.org/abs/1909.07814)
3. [GitHub](https://github.com/mpc-msri/EzPC)
4. [Talk](https://crypto.iacr.org/2019/affevents/ppml/page.html) at PPML Workshop, Crypto 2019
5. [Talk](https://www.youtube.com/watch?v=53rxhEmDqQk) at IEEE S&P, 2020
6. [Teaser](https://www.youtube.com/watch?v=vOIpcq9mq8w) at IEEE S&P, 2020 
7. [Talk](https://www.youtube.com/watch?v=ydlEncvKTtU) at TPMPC, 2020
