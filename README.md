# VOCAL-TRACT-SEGMENTATION
The aim of the project is to implement a Ruthven U-net architecture for vocal tract segmentation using Real Time Magnetic Resonances (rtMR) images. The vocal tract segmentation involves identifying six regions: Upper lip, Hard palate, Soft palate, Tongue, Lower lip, and Head. The focus is particularly on the accurate segmentation of the Soft palate and Tongue, as their motion and anatomical features play a crucial role in speech-related issues.


<p float="left" align="center">
  <img src="1.png" hspace="30"  width="200" heigth="200"/ >
  <img src="2.png" hspace="30"  width="200" heigth="200"/> 
</p>

## PREPROCESSING
The preprocessing phase aimed to eliminate Gaussian noise present in the provided dataset through three tests. Several methods have been performed; the one that demonstrates the most effective noise reduction was the **fastNlMeansDenoising**, a function already implemented in OpenCV library.
<p align="center">
  <img width="550" height="320" alt="noise" src="https://github.com/NacliNaclo/VOCAL-TRACT-SEGMENTATION/assets/107640468/122d29da-2bb9-420a-8963-313553b85a0e](https://github.com/NacliNaclo/VOCAL-TRACT-SEGMENTATION/assets/107640468/a7b6610e-bc6b-4319-85fe-2687a8c6ae23)">
</p>

## MODEL
## RESULTS
- The model architecture is based on the Ruthven U-net, consisting of encoder and decoder paths. In the encoder path, high-level features are extracted by progressively reducing spatial dimensions and increasing the number of feature maps. This process results in a latent representation space where spatial resolution is sacrificed for high-level features. The decoder path aims to restore the initial image's spatial dimension, utilizing transpose convolutional layers in combination with standard blocks. Skip connections are incorporated at each step to preserve spatial information extracted by the encoder.
To enhance U-net's performance, residual blocks are introduced into the architecture. This modification involves transforming basic blocks into residual blocks by concatenating the input of the first block with the output of the second in the same layer. This operation is repeated in both the decoder and encoder parts. The incorporation of residual blocks allows the network to capture intricate features, proving beneficial for segmentation tasks involving subtle details.

<p align="center">
  <img width="700" height="200" src="https://github.com/NacliNaclo/VOCAL-TRACT-SEGMENTATION/assets/107640468/8c7b3b2c-7689-4db5-aaac-77e2ffcc0394"/>
</p>


<p align="center">
  <img width="200" height="200" src="Media1 (online-video-cutter.com)(1).gif"/>
</p>




<p float="left" align="center">
  <img src="Picture2.png" width="200" />
  <img src="Picture3.png" width="200" /> 
</p>

