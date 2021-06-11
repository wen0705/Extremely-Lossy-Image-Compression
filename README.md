# Extreme_Lossy-_Image_Compression

In the domain of lossy image and, especially, video compression, classical (non machine-learning based) compression codecs are still somewhat difficult to outperform in the high-quality regime. By contrast, in the low-quality regime, it is often much easier to design a machine-learning based compression technique that is significantly better than any existing classical codec. In this project, you will take this idea to an extreme and you will explore a regime about which little is known so far: the regime of extremely low bit rate. Your goal is to compress images into just a few hundred bits in such a way that you can still reconstruct an image that has something in common with the original image, so that one can still use the reconstructed image to answer some basic questions like “How many red objects are there in the image?” or “What color is the ball next to the red cube?”.

# Basic idea:
We want to build a neural network like the construction like the GAN. It consists of two deep neural networks called "generator" and the "discriminator".

## "generator": 
The generator takes the original images and then compresses them into few hundred bits. 

## "discriminator":
Input: 
a batch of images (original images with the question created by VQA) and a binary that showed that the image is reconstructed or not.

The discriminator classifies the input images as original images or the reconstruction images.

we update the generator and the discriminator alternatively.

## References

- [Deep Learning and Visual Question Answering](https://towardsdatascience.com/deep-learning-and-visual-question-answering-c8c8093941bc) 
- [Generative Neural Network Based Image Compression](http://cs229.stanford.edu/proj2018/report/44.pdf) 
- [VQA](https://modelzoo.co/model/vqapytorch#pretrained-models)
- [VAE introduction](https://www.tensorflow.org/tutorials/generative/cvae)
