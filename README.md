# Extremely Lossy Image Compression

Nowadays, image compression plays a crucial role in our life. Lossy image compression can compress the image into only a few hundred bits. One of the drawbacks of lossy image compression is that some information from the original image is eliminated and can not be recovered by reconstruction. Therefore, we want to achieve a good balance between the compression size and the image quality. In this work, we present an architecture that can efficiently reconstruct the face region with correct genders from compressed one-person images. Our result shows a slight improvement compared to the Vanillia VAE.

![Figure](https://github.com/wen0705/Extreme_Lossy-_Image_Compression/blob/main/fig/model.png)
**Key world:**
Image Compression, VAE, Object detection
### Result:
<!-- We conduct both qualitative and quantitative comparisons of Vanilla VAE and our VAE. Due to our limited computing power on colab (one GPU with a limit using time), we only conducted 20 epoch for each module. According to \cite{Subramanian2020}, the minimum epoch number to converge is 50 for vanilla VAE, therefore, our result only shows a slight improvement compared to the Vanilla VAE, especially in quantitative analysis. -->
#### Qualitative Analysis:
**Positive effects:**

![Figure](https://github.com/wen0705/Extreme_Lossy-_Image_Compression/blob/main/fig/advantage.jpg)
- Our model reconstructs better face directions. The vanilla VAE only recognizes a small range of face rotation, so most reconstruction faces are frontal faces. But our model can capture the correct rotations and reconstruct them.
- Our model reconstructs gender better that can be recognized by human eyes. Due to the interference from the background, face shape, or facial accessories, vanilla VAE makes more mistakes by reconstructing gender. Considering more of the face region, our model obtains less influence on the surrounding area (hair, background, etc.) and has better results.
- Our model reconstructs the facial expression better. The vanilla VAE uses the same ”big smile” for the frontal face images and the same ”gentle smile” for the side faces. Therefore the reconstruction of facial expression in Vanilla VAE is highly related to the face directions rather than the facial expressions in the original images. At the expense of sharpness, our model can capture the facial expression directly from the original image.

**Negative effects:**

![Figure](https://github.com/wen0705/Extreme_Lossy-_Image_Compression/blob/main/fig/disadvantage.jpg)
- Our model works worse on ethnicities other than Caucasians. To the human eyes, Vanilla VAE has better results for different races than our VAE. A possible reason is that the learning priority changed, which means that our model learns the facial expression of the Caucasians first, and 20 epochs are not enough for this model to learn it for all the races.
- Our model is more sensitive to the light. These three images represent three extreme illumination situations. It shows that our model captures the illumination features of the original image better. However, our model produces less sharp reconstructions. Still, compared to Vanilla VAE, our reconstructions have more similar face regions to the original images.



<!-- To approximate the best true distribution  of Z, we form a distribution p<sub>model</sub>(Z|X), which will be learned through a Gaussian-distribution.

We use Kullback-Leibler divergence between the encoder’s distribution p<sub>model</sub>(Z) and p<sub>data</sub>(Z|X) to present the loss L<sub>prior</sub>. This divergence measures how much information is lost when use p<sub>model</sub>(Z) to represent p<sub>data</sub>(Z|X). Then we sample Z<sub>p</sub> from this distribution.

The discriminator consists of a fixed stable VQA module, which presents the probable feature extraction, and a classification network C which assigns one to samples from p<sub>data</sub>(X) and zero to samples from p<sub>decoded</sub>(X|Z).
Define C<sub>r</sub> as the layer which denotes the probability of the image being original. This probability distribution from C<sub>r</sub> is the approximation of p<sub>data</sub>(X). 

Define Y as the hidden representation in the layer \subC<sub>r</sub>.

Given the discriminator X,  X<sub>hat</sub>,  X<sub>p</sub> as input and collect the corresponding Y : 
X --> 
<!-- Y, X<sub>hat</sub> -->
<!-- Y<sub>hat</sub>, X<sub>p</sub> --> 
<!-- Y<sub>p</sub> --> 
<!-- -->
<!-- The correspondence losses L<sub>GAN</sub> and L<sub>Disc</sub> are defined as follows: -->

<!-- Back-propagation: We use the partial derivation of L<sub>prior</sub> + L<sub>disc</sub> to update parameters in Encoder, use the partial derivation of r L<sub>disc</sub> - L<sub>GAN</sub> to update parameters in Decoder and use  the partial derivation of L<sub>GAN</sub> to update the parameters in Discriminator. -->

<!-- 
## Current Status:
-  We settled the basic structure of our network and most of our loss functions. Also we filtered out a reference-valuable existed algorithm and understand the proof process.
-  We tried to build a VAE demo with pytorch. [processing]
-  We tried to find\train a stable high quality network. [encountered problem with GPU,CUDA,CUDNN,torch conflict] -->


### References
- Pytorch VAE:https://github.com/AntixK/PyTorch-VAE
- Ziwei Liu, Ping Luo, Xiaogang Wang, and Xiaoou Tang. Deep learning face attributes in the wild. In Proceedings of International Conference on Computer Vision (ICCV), December 2015.

<!-- - ### VAE-GAN
  - [【MAIN Algo】Autoencoding beyond pixels using a learned similarity metric](https://arxiv.org/pdf/1512.09300.pdf)

- ### VQA
  - [Deep Learning and Visual Question Answering](https://towardsdatascience.com/deep-learning-and-visual-question-answering-c8c8093941bc) 
  - [Official-site VQA](https://visualqa.org/)
  - [VQA data reading tools(for evaluation and reading)](https://github.com/GT-Vision-Lab/VQA)
  - [VQA: Visual Question Answering (ICCV 2015)](https://arxiv.org/pdf/1505.00468.pdf)
  - [Generative Neural Network Based Image Compression](http://cs229.stanford.edu/proj2018/report/44.pdf) 
  - [VAE introduction](https://www.tensorflow.org/tutorials/generative/cvae)
  - [End-to-end Optimized Image Compression](https://arxiv.org/abs/1611.01704)
 -->
<!-- ## pretrained Model

- [ns-VQA【current testing...】](https://github.com/kexinyi/ns-vqa)
- [VQA](https://modelzoo.co/model/vqapytorch#pretrained-models)
 -->

<!-- ## image compression
- [image compression and code](https://github.com/zhiqiang-zhu/Image-Compression-Papers-and-Code) -->


