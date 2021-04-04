# Image-Inpaint-Denoise-Deblur-Pytorch

This model is capable of performing good quality **image inpainting, denoising and debluring simultaneously** in time efficient manner!! 
</br>

<img src="Images/Untitled%20Diagram.png">
</br>
I have used fully convolutional approach using Decoder for image generation but the activation employed is **Gated_Activation** ,as proposed in the paper <a href="https://arxiv.org/abs/1606.05328"> Conditional Image Generation with PixelCNN Decoders</a> ,without the sequential masked convolution approach(which is slow).

</br>
Advantages: </br>
**(i)Good Quality Results** </br>
**(ii)Time-efficient Approach**
</br>

I have also tested an equivalent decoder with Relu activation and can say that the Gated_Activation produces superior results.

# Methedology
Vector Quantized -Variational Auto Encoder (**VQ-VAE**) is trained to reconstruct the Input, post training VQ-VAE all its parameters are freezed, it's then used to encode the input to discrete latent embeddings, then a Convolutional Decoder is trained to construct the noise -free, blur-free and inpainted Image. 
<img align='right' height="450px" src="Images/gif1.gif"/>
# Data Preparation
The Dataset used for this project is <a href="https://www.kaggle.com/arnaud58/flickrfaceshq-dataset-ffhq"> Flickr-Faces-HQ Dataset (FFHQ)</a> available on Kaggle.
</br>
</br>
To mimic real world scenario random white lines are drawn on the dataset while injecting random "Salt & Pepper" Noise and then randomly introducing one of ['average','gaussian','median'] blurring of different magnitutdes.

# Samples:
<img src="Images/Using%20Gated%20Activation%20(3).png">
</br>
<img src="Images/Input%20to%20Model%20(3).png">
