# CAMEL for Retina OCT Image Classification and Segmentation [WACV 2025]

This is the official implementation of "CAMEL: Confidence-Aware Multi-task Ensemble Learning with Spatial Information for Retina OCT Image Classification and Segmentation" accepted in IEEE/CVF Winter Conference on Applications of Computer Vision (WACV 2025)


## News 
🔥October 2024, Paper accepted at WACV 2025 🎉.

## Requirements 
- Python 3.10
- torch 2.1.2
- TensorFlow 2.9.1
- segmentation-models 1.0.1


## Data Preparation
For training and testing the models, you can use the public dataset [OCT5K](https://rdr.ucl.ac.uk/articles/dataset/OCT5k_A_dataset_of_multi-disease_and_multi-graded_annotations_for_retinal_layers/22128671?file=44436359)

The dataset covers semantic segmentation and object detection tasks.

- "Images": Original OCT Images
- "Masks": pixel-wise annotations with three manual gradings for 1,672 images and 2,924 masks with single automatic grading
- "Detection": CSV files for object detection labels

<p align="center"><img width="674" alt="스크린샷 2024-11-17 오전 12 39 52" src="https://github.com/user-attachments/assets/78371572-8dee-41ff-bb5c-17e33127edb6">


## Training 
To train the network, you can run the following command:

```
python3 train.py --batch_size 4 --aug 5 --model resnet101 -img_size 320 -erm_weight 0.2 --ece_weight 0.01
```

## Testing on Dataset
After training, you can use ```test.ipynb``` for performance evaluation and visual inference. Open the notebook and follow the instructions to evaluate the trained model on your dataset.

## Code Description

- ```train.py```: Code for training CAMEL
- ```test.ipynb```: Code for testing CAMEL

### utils

- ```loss.py```: Code for loss functions
- ```utils.py```: util functions, including labeling, preprocessing codes

### preprocessing

- ```augmentation.py```: Code for image augmentation
- ```image_to_mask.py```: Applies our new OCT image preprocessing method, converting processed annotation images into the .npy format.

## Citation
```
@inproceedings{
jung2025camel,
title={CAMEL: Confidence-Aware Multi-task Ensemble Learning with Spatial
Information for Retina OCT Image Classification and Segmentation},
author={Juho Jung, Migyeong Yang, Hyunseon Won, Jiwon Kim, Jeongmo Han, Joonseo Hwang, Daniel Duck-Jin Hwang, and Jinyoung Han},
booktitle={},
year={2025},
url={}
}
```


