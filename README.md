# Unet
We employed Unet architecture to segment biomedical images.

## 1 Introduction
Image segmentation is a critical task in computer vision, where the primary goal is to classify each pixel of an image into a particular category. The Unet architecture, known for its efficacy in segmentation tasks, was employed to segment biomedical images.

## 2 Result
### 2.1 Resulting Segmentation of Test Images
The segmentation results achieved from the test images using the Unet model are illustrated in Figure 1. The figure presents a side-by-side comparison where the original images with ground truth annotations are juxtaposed against their corresponding segmentation predictions.
The segmentation output, as shown in the right column, demonstrates the model’s ability to delineate the regions of interest with high precision. Although there is a visible distinction between the predicted segmentation and the ground truth in certain areas, indicating room for further model refinement, the over- all accuracy, which is 87.7%, and consistency of the results are indicative of the Unet model’s robustness in handling complex segmentation tasks.

![Figure 1: Comparative Segmentation Results. The left column displays the ground truth labels, and the right column shows the segmentation results ob- tained using the U-Net model on test images.
](https://github.com/ASmellyCat/Unet/assets/110814688/94582ddc-538e-4023-806b-f1c9d757292d)

### 2.2 Data Augmentation

A variety of data augmentation strategies were implemented to enhance the training set and improve the model’s ability to generalize. These strategies include:

• Horizontal/Verticle Flip: The image is randomly flipped with a 50% chance of a horizontal flip, creating a mirror image, or a 50% chance of a vertical flip, effectively inverting it top-to-bottom.
• Rotation: Rotating the image within a range of -45 to 45 degrees.
• Zoom: Zooming the image between 1.1 to 1.5 times the original size.
• Smooth Deformation: A non-rigid transformation inspired by the UNet authors’ approach, this technique applies smooth deformations using ran- dom displacement vectors on a coarse 3 by 3 grid. The displacements are drawn from a Gaussian distribution with a 10-pixel standard deviation. The generated displacements are then interpolated to create a smooth deformation field across the image.


These methods were carefully chosen and implemented to ensure that the model is exposed to a variety of transformations, thus enabling it to learn more robust and invariant features from the images.

### 2.3 Training Details

The plot for the train-test losses is shown in Figure 2. 
• Image Size: 572 x 572 pixels
• Number of Epochs: 10
• Batch Size: 8
• Learning Rate: 1e-2
• Accuracy rate: 87.7%
• Time Duration: 101.4 seconds.
![Figure 2: Train-test loss plots over epochs.](https://github.com/ASmellyCat/Unet/assets/110814688/efb18bb3-2620-4c65-a3be-0f0145e8b320)


## 3 Utilizing Weights & Biases for En- hanced Logging
### 3.1 Integration with Weights & Biases
We have integrated the Weights & Biases (wandb) platform into the training process. This tool was used for meticulous logging of various aspects such as training loss, validation loss, and key hyperparameters.

### 3.2 Parameters Logged
The following parameters were systematically logged using wandb: • Learning Rate
• Unet Architecture
• Dataset Used
• Number of Epochs
• Image Size
• Batch Size
Addtionaly, we also tracked:
• Training Loss: Monitoring the loss during the training phase to gauge model learning.
• Validation Loss: Tracking the loss on the validation set to assess model generalization.
This integration facilitated a more organized and accessible way to monitor and analyze the model’s performance and behavior during training.

### 3.3 Visualization of Logs
Figures 3 and 4 below showcase examples of the visualizations obtained from Weights & Biases. Figure 3 presents the recorded training and validation losses over epochs, while Figure 4 displays the key hyperparameters used during the training process.
<img width="1570" alt="Figure 3: Training and Validation Loss as logged in Weights & Biases." src="https://github.com/ASmellyCat/Unet/assets/110814688/77f51aab-2a9b-4836-ab45-08066b806add">
<img width="1567" alt="Figure 4: Snapshot of Hyperparameters as logged in Weights & Biases.
" src="https://github.com/ASmellyCat/Unet/assets/110814688/cf971096-e9a7-43f8-a4aa-fb0d15b11264">



## Conclusion
The experiments conducted using the Unet architecture for image segmentation yielded promising results. The data augmentation strategies adopted and the training parameters set were effective in achieving satisfactory segmentation outcomes on the test images. Further optimizations and fine-tuning can be explored in future work to improve segmentation performance.


