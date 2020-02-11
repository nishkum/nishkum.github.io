---
title: "CrypTFlow: Secure TensorFlow Inference"
collection: projects
type: "Research project"
permalink: /projects/2019-09-15-project-cryptflow
excerpt: 'In this project, we present CrypTFlow, a first of its kind system that converts TensorFlow inference code into Secure Multi-party Computation (MPC) protocols at the push of a button. To do this, we build three components. Our first component, Athos, is an end-to-end compiler from TensorFlow to a variety of semi-honest MPC protocols. The second component, Porthos, is an improved semi-honest 3-party protocol that provides significant speedups for Tensorflow like applications. Finally, to provide malicious secure MPC protocols, our third component, Aramis, is a novel technique that uses hardware with integrity guarantees to convert any semi-honest MPC protocol into an MPC protocol that provides malicious security. The security of the protocols output by Aramis relies on hardware for integrity and MPC for confidentiality. Moreover, our system, through the use of a new float-to-fixed compiler, matches the inference accuracy over the plaintext floating-point counterparts of these networks. We experimentally demonstrate the power of our system by showing the secure inference of real-world neural networks such as ResNet50, DenseNet121, and SqueezeNet over the ImageNet dataset with running times of about 30 seconds for semi-honest security and under two minutes for malicious security.'
venue: "Microsoft Research Lab"
date: 2019-09-15
location: "Bengaluru, India"
---

## Broader Picture
This work is part of a larger project - namely [EzPC](https://www.microsoft.com/en-us/research/project/ezpc-easy-secure-multi-party-computation/) (Easy Secure Multi-party Computation), being pursued at Microsoft Research India, with an aim to increase the adoption of Secure Multi-party Computation (MPC) as a tool for various privacy-preserving tasks. The current work can be seen as an attempt to increase the usage of MPC for secure inference of large real-world neural networks. Have a quick look at the project's description in the following [youtube video](http://www.youtube.com/watch?v=-1H1Sp-_5YU).

[![EzPC(Easy Secure Multi-Party Computation)](http://img.youtube.com/vi/-1H1Sp-_5YU/0.jpg)](http://www.youtube.com/watch?v=-1H1Sp-_5YU)

## Details 
In this work, we build and present CrypTFlow, a first of its kind system that converts TensorFlow inference code into Secure Multi-party Computation (MPC) protocols at the push of a button. To do this, we build three components. Our first component, Athos, is an end-to-end compiler from TensorFlow to a variety of semi-honest MPC protocols. The second component, Porthos, is an improved semi-honest 3-party protocol that provides significant speedups for Tensorflow like applications. Finally, to provide malicious secure MPC protocols, our third component, Aramis, is a novel technique that uses hardware with integrity guarantees to convert any semi-honest MPC protocol into an MPC protocol that provides malicious security. The security of the protocols output by Aramis relies on hardware for integrity and MPC for confidentiality. Moreover, our system, through the use of a new float-to-fixed compiler, matches the inference accuracy over the plaintext floating-point counterparts of these networks.

We experimentally demonstrate the power of our system by showing the secure inference of real-world neural networks such as ResNet50, DenseNet121, and SqueezeNet over the ImageNet dataset with running times of about 30 seconds for semi-honest security and under two minutes for malicious security. Prior work in the area of secure inference (SecureML, MiniONN, HyCC, ABY3, CHET, EzPC, Gazelle, and SecureNN) has been limited to semi-honest security of toy networks with 3–4 layers over tiny datasets such as MNIST or CIFAR which have 10 classes. In contrast, our largest network has 200 layers, 65 million parameters, and over 1000 ImageNet classes. Even on MNIST/CIFAR, CrypTFlow outperforms prior work.

## Outreach and presentation
An archive version of the paper can be found on [eprint](https://eprint.iacr.org/2019/1049) or [arXiv](https://arxiv.org/abs/1909.07814). The complete code-base is also open-sourced at [GitHub](https://github.com/mpc-msri/EzPC).
The corresponding results were presented by me at TechFest, which is an internal conference of Microsoft at Redmond, Washington, and at the [PPML workshop](https://crypto.iacr.org/2019/affevents/ppml/page.html) at Crypto, 2019 by my collaborators.

## Updates
- <span style="color:#fa4d4d">[Feb '20]</span> CrypTFlow has been accepted at [IEEE Symposium on Security and Privacy (S&P), 2020](https://www.ieee-security.org/TC/SP2020/).

