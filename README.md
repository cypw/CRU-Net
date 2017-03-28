# Collective Residual Networks
This repository contains the code and trained models of "Sharing Residual Units Through Collective Tensor Factorization in Deep Neural Networks".

## Implementation

### Augmentation

| Method         |  Settings  |
| :------------- | :--------: |
| Random Mirror  |    True    |
| Random Crop    |  8% - 100% |
| Aspect Ratio   |  3/4 - 4/3 |
| Random HSL     | [20,40,50] |

> Note: 
> We did not use PCA Lighting and any other advanced augmentation methods.

### Normalization

The augmented input images are substrated by mean RGB = [ 124, 117, 104 ], and then multiplied by 0.0167.


## Results

### ImageNet-1k

**Single crop validation error (center 224x224 crop from resized image with shorter side=256):**

Model|Setting|Model Size|Top-1
:-----|------:|---------:|:---:
CRU-Net-56 @x14|32x4d|98MB|21.9%
CRU-Net-56 @x14|136x1d|98MB|21.7%
CRU-Net-116 @x28x14|32x4d|168MB|20.6%
CRU-Net-116, wider @x28x14|64x4d|318MB|20.3%

We also trained a tiny CRU-Net-56 with less than half the size of ResNet-56.

**Single crop validation error (center 224x224 crop from resized image with shorter side=256):**

Model|Setting|Model Size|Top-1
:-----|------:|---------:|:---:
CRU-Net-56,tiny @x14|32x4d|48MB|22.9%


### Places365-Standard

**10-crop validation error (averaging softmax scores of 10 224x224 crops from resized image with shorter side=256):**

Model|Setting|Model Size|Top-1
:----|------:|---------:|:---:
CRU-Net-116 @x28x14|32x4d|163MB|56.6%



## Trained Models

Model|Setting|Dataset| Link
:----|------:|:------:|:---:
CRU-Net-56,tiny @x14|32x4d|ImageNet-1k|[GoogleDrive](https://goo.gl/oTG7HJ)
CRU-Net-56 @x14|32x4d|ImageNet-1k|[GoogleDrive](https://goo.gl/AD8Bs0)
CRU-Net-56 @x14|136x1d|ImageNet-1k|[GoogleDrive](https://goo.gl/PEY8al)
CRU-Net-116 @x28x14|32x4d|ImageNet-1k|[GoogleDrive](https://goo.gl/OFyIaD)
CRU-Net-116 @x28x14|32x4d|Places365-Standard|[GoogleDrive](https://goo.gl/6gglTz)





