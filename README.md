# Extreme_Lossy-_Image_Compression

# Basic Idea:
VAE-GAN introduced by Larsen [1] presents a model which uses learned feature representations in the GAN discriminator as a basis for the VAE reconstruction objective.Based on their research and the 'Two-Player Game' idea in GAN, we use the following model as shown in Figure 1 to compress the images in a lossy way.
In this model, we collapse the decoder and the generator into one to reconstruct less blurry images. We place the VQA network in our discriminator to score the reconstruction images. After a few steps, the decoder can generator the images with clear relevant information based on the questions of VQA.

![Figure](https://github.com/wen0705/Extreme_Lossy-_Image_Compression/blob/main/mini-program/figure.png)


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
- [easy-VQA](https://easy-vqa-demo.victorzhou.com/)
- [Transformers-VQA](https://github.com/YIKUAN8/Transformers-VQA/blob/master/openI_VQA.ipynb)
- [VisualBert](https://github.com/uclanlp/visualbert)

## image compression
-- [image compression and code](https://github.com/zhiqiang-zhu/Image-Compression-Papers-and-Code)

## Dataset
- [Coco](https://cocodataset.org/)
