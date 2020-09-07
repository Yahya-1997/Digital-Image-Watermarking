# Digital Image Watermarking
The digital image watermarking is based on the fact that a message is hide into the image such that image doesn’t get disturbed and message can be retrieved easily. The method should be 
robust. For this purpose, this repository is implementing the discrete wavelet transform (DWT) and discrete cosine transform (DCT) in cascade so that more robustness and security can be
achieved. These methods divide the image into different frequency regions so that watermark message can be embedded into lowest frequency region which will not disturb the image. DCT is
applied first which is similar to Fourier transform and divides the image into two parts of lower and higher frequency region. Lower frequency region has most of the image information.

Similarly, DWT using haar wavelet transform split the images into four different frequency coefficients: approximation coefficients, horizontal , vertical and detailed frequency component.

Horizontal coefficient is used to insert the watermark image and DCT transform is further applied to cH1 component of DWT transformed image. The embedding of watermark image needs a optimal gain factor which sets the robustness of the message. If this value is too high then security will be increased but retrieval of message will be difficult and vice-versa. So trade off gain factor has to be used for embedding of watermark in it. I used Bacterial Foraging optimization (BFO) for this purpose.

I tested the algorithm at three different kind of images which are low,high and medium key images. This category is suggested on the basis of computer graphics literature where the image with more number of histogram bins are aligned to left for low key image, to right for hugh key image and in middle  for medium key image.

A gui to compare the three different watermarking algorithms is also designed in MATLAB. It makes easy to run the algorithm and analyse. On the criteria of PSNR, NCC and IF parameters, I found the gain factor tuning by BFO gives best performance.

# How To Use

In Matlab scrip explorer, open manit1.m file and run. A gui opens. From there, you can select the cover image and secret message in png format and use on the button to apply the embedding algorithms.
