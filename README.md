# Image-Inpaint-Denoise-Deblur-Pytorch

<img align='right' height="450px" src="Images/gif1.gif"/>

This model is capable of performing good quality image inpainting, denoising and debluring simultaneously in time efficient manner!! 
</br>
</br>
I have used convolutional decoder for image generation but the activation employed is **Gated_Activation** as proposed in the paper <a href="https://arxiv.org/abs/1606.05328"> Conditional Image Generation with PixelCNN Decoders</a>.

I have also tested an equivalent decoder with Relu activation(Samples Below) and yes the Gated_Activation produces superior results.

# Methedology
I have used Vector Quantized - Auto Encoder (**VQ-VAE**) as feature extracter 

# Data Preparation
The Dataset used for this project is <a href="https://www.kaggle.com/arnaud58/flickrfaceshq-dataset-ffhq"> Flickr-Faces-HQ Dataset (FFHQ)</a> available on Kaggle.
</br>
</br>
To mimic real world scenario random white lines are drawn on the dataset while injecting random "Salt & Pepper" Noise and then randomly introducing one of ['average','gaussian','median'] blurring of different magnitutdes.
