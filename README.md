# Image Classification Model Analysis

This repository contains scripts for analyzing and visualizing the performance of various image classification models on ImageNet datasets, including adversarial examples.

## Features

- Support for multiple deep learning models:
  - ViT (Vision Transformer)
  - ConvNeXT
  - Swin Transformer
- Implementation of various Grad-CAM algorithms:
  - GradCAM
  - HiResCAM
  - GradCAMPlusPlus
  - XGradCAM
  - LayerCAM
- Evaluation on different ImageNet datasets:
  - Original ImageNet validation set
  - Adversarial examples (Gaussian noise, defocus blur, pixelate)
- Generation of visualizations:
  - Original images
  - Grad-CAM heatmaps
  - Masked images
- Performance metrics calculation:
  - Precision, Recall, F1 Score
  - Confusion matrix for each class

## Setup

1. Clone the repository:

   ```
   git clone https://github.com/YourUsername/ImageClassificationAnalysis.git
   cd ImageClassificationAnalysis
   ```

2. Install the required dependencies:

   ```
   pip install torch torchvision tqdm pillow numpy opencv-python transformers pytorch-grad-cam
   ```

3. Prepare your ImageNet dataset and adversarial examples.

4. Update the `current_dir` and `dataset_dirs` variables in the scripts to point to your data locations.

## Usage

The repository contains three main scripts:

1. `vit_analysis.py`: Analyzes ViT model performance
2. `convnext_analysis.py`: Analyzes ConvNeXT model performance
3. `swin_analysis.py`: Analyzes Swin Transformer model performance

Run each script separately:

```
python vit_analysis.py
python convnext_analysis.py
python swin_analysis.py
```

Each script will process the specified datasets, generate visualizations, and save results in the `results` directory.

## Output

For each image, the following files are generated:

- `original.jpg`: The original input image
- `gradcam.jpg`: Grad-CAM visualization
- `grayscale.jpg`: Grayscale Grad-CAM heatmap
- `grayscale.npy`: NumPy array of the Grad-CAM heatmap
- `masked_image.jpg`: Original image masked with Grad-CAM heatmap
- `info.txt`: Top predictions for the original image
- `info_masked.txt`: Top predictions for the masked image
- `scores.npy`: NumPy array of prediction scores

## Directory Structure

```
results/
└── [dataset_name]/
    └── [model_name]/
        └── [cam_algorithm_name]/
            └── [image_name]/
                ├── original.jpg
                ├── gradcam.jpg
                ├── grayscale.jpg
                ├── grayscale.npy
                ├── masked_image.jpg
                ├── info.txt
                ├── info_masked.txt
                └── scores.npy
```

## Contributing

Contributions to improve the code or extend the analysis to other models/datasets are welcome. Please submit a pull request or open an issue to discuss proposed changes.

