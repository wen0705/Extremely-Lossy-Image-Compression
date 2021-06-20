# Extreme_Lossy-_Image_Compression

## Basic Idea:
VAE-GAN introduced by Larsen [MAIN Algo] presents a model which uses learned feature representations in the GAN discriminator as a basis for the VAE reconstruction objective.Based on their research and the 'Two-Player Game' idea in GAN, we use the following model as shown in Figure 1 to compress the images in a lossy way.
In this model, we collapse the decoder and the generator into one to reconstruct less blurry images. We place the VQA network in our discriminator to score the reconstruction images. After a few steps, the decoder can generator the images with clear relevant information based on the questions of VQA.

![Figure](https://github.com/wen0705/Extreme`_L`ossy-_Image_Compression/blob/main/mini-program/figure.png)

## Figure explanation:
As shown in the Figure above, Input X consists of a batch of images stored in a tensor. After some convolution networks (3 layers for instance), our encoder compresses the original input into the latent low-dimensional code Z which only contains few hundred bits sized tensor.

To approximate the best true distribution  of Z, we form a distribution p<sub>model</sub>(Z|X), which will be learned through a Gaussian-distribution.

We use Kullback-Leibler divergence between the encoder’s distribution p<sub>model</sub>(Z) and p<sub>data</sub>(Z|X) to present the loss L<sub>prior</sub>. This divergence measures how much information is lost when use p<sub>model</sub>(Z) to represent p<sub>data</sub>(Z|X). Then we sample Z<sub>p</sub> from this distribution.

The discriminator consists of a fixed stable VQA module, which presents the probable feature extraction, and a classification network C which assigns one to samples from p<sub>data</sub>(X) and zero to samples from p<sub>decoded</sub>(X|Z).
Define C<sub>r</sub> as the layer which denotes the probability of the image being original. This probability distribution from C<sub>r</sub> is the approximation of p<sub>data</sub>(X). 

Define Y as the hidden representation in the layer \subC<sub>r</sub>.

Given the discriminator X,X<sub>hat</sub>,X<sub>p</sub> as input and collect the corresponding Y: 
X\rightarrow Y, X<sub>hat</sub>\rightarrow Y<sub>hat</sub>, X<sub>p</sub>\rightarrow Y<sub>p</sub>
The correspondence losses L<sub>GAN</sub> and L<sub>Disc</sub> are defined as follows:

Back-propagation: We use the partial derivation of L<sub>prior</sub> + L<sub>disc</sub> to update parameters in Encoder, use the partial derivation of \gamma L<sub>disc</sub> - L<sub>GAN</sub> to update parameters in Decoder and use  the partial derivation of L<sub>GAN</sub> to update the parameters in Discriminator.


## Current Status:
-  We settled the basic structure of our network and most of our loss functions. Also we filtered out a reference-valuable existed algorithm and understand the proof process.
-  We tried to build a VAE demo with \texttt{pytorch}. [processing]
-  We tried to find\setminustrain a stable high quality network. [encountered problem with GPU,CUDA,CUDNN,torch conflict]


## References

- ### VAE-GAN
  - [【MAIN Algo】Autoencoding beyond pixels using a learned similarity metric](https://arxiv.org/pdf/1512.09300.pdf)

- ### VQA
  - [Deep Learning and Visual Question Answering](https://towardsdatascience.com/deep-learning-and-visual-question-answering-c8c8093941bc) 
  - [Official-site VQA](https://visualqa.org/)
  - [VQA data reading tools(for evaluation and reading)](https://github.com/GT-Vision-Lab/VQA)
  - [VQA: Visual Question Answering (ICCV 2015)](https://arxiv.org/pdf/1505.00468.pdf)
  - [Generative Neural Network Based Image Compression](http://cs229.stanford.edu/proj2018/report/44.pdf) 
  - [VAE introduction](https://www.tensorflow.org/tutorials/generative/cvae)
  - [End-to-end Optimized Image Compression](https://arxiv.org/abs/1611.01704)

## pretrained Model

- [ns-VQA【current testing...】](https://github.com/kexinyi/ns-vqa)
- [VQA](https://modelzoo.co/model/vqapytorch#pretrained-models)


## image compression
- [image compression and code](https://github.com/zhiqiang-zhu/Image-Compression-Papers-and-Code)


