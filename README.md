# Vessel-segmentation-in-retinal-images
Retinal vessels segmentation plays a vital role in the diagnosis and screening of many fundus and cardiovascular diseases. 
The process of retinal vessel segmentation is accomplished by classifying each pixel in a fundus image into either vessels or background, essentially implementing a binary classification for every pixel in the image.
### Dataset
We use Drive dataset that is available: https://www.kaggle.com/datasets/zionfuo/drive2004/ \
DRIVE (Digital Retinal Images for Vessel Extraction) is a dataset comprising 40 randomly selected retinal images from a diabetic retinopathy screening program in the Netherlands, covering individuals aged 25–90 years. The dataset is split into a training set and a test set, each containing 20 images. 
The following figure shows a sample of training image and its manual segmentation.\
![image](https://github.com/NarjesKarami/Vessel-segmentation-in-retinal-images/assets/78353927/d6e466ab-0a7f-4610-a01d-71e180ec19f9)

### Pre-processing
Every image is resized to the standard size of [512,512,3] and then normalized to the range of [0,1].
Since the dataset is small we will employ the data augmentation techniques to increase the amount of data. The following data augmentations are utilized:
- horizontal flip
- brightness change
- gaussian noise addition 
  
Moreover, the complete image is divided into multiple patches. These patches are individually segmented and predicted before being reassembled to reconstruct the initial image. The figure bellow shows a sample of patches. This approach of spliting the image into smaller patches serves not only to augment the data but also help the model to read the image quickly.

![image](https://github.com/NarjesKarami/Vessel-segmentation-in-retinal-images/assets/78353927/03789bd4-bf1d-4e5b-8048-029fba411b77)
  
### Method
We will use U-net and Residual- Unet (ResNet) architectures to segment the retinal blood vessels.
