# Retinal Layer Segmentation with Multi-Attention Y-Net

This project implements a retinal layer segmentation model using the Multi-Attention Y-Net architecture. The notebook provides an end-to-end solution for training, evaluating, and visualizing retinal layer segmentation from OCT images.

## Datasets Downloading and Preproccesing

Downloads the DUKE dataset 


Ensure the dataset is placed in the correct directory structure before running the notebook.

## Running the Notebook

### Prerequisites
- Python 3.7+
- Jupyter Notebook
- Required Python packages ( install directly in the notebook)

### Steps to Run:
1. Clone the repository:
   ```bash
   git clone https://github.com/Nusrath-Amana/Enhanced-medical-image-segmentation-with-Multi-Attention-Y-Net
   ```

2. Start the Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

3. Open `y-net-extension.ipynb` and follow the instructions to execute the code cells.

## Model Architecture

The Multi-Attention Y-Net architecture includes the following components:

1. **Dual Encoders:**
   - Extract features from input images at different scales.

2. **Multi-Attention Mechanisms:**
   - Enhance feature representation by focusing on relevant regions.

3. **Fourier Features:**
   - Integrates Fourier-based feature extraction for better segmentation.

4. **Decoder:**
   - Reconstructs segmented images using refined features.

## Training the Model

1. **Preprocessing:**
   - Load images and annotations.
   - Apply necessary transformations (resizing, normalization, etc.).

2. **Data Splitting:**
   - Divide the dataset into training and validation sets.

3. **Model Compilation:**
   - Loss: Combined Dice and Cross-Entropy Loss.
   - Optimizer: Adam with a custom learning rate.

4. **Training Loop:**
   - Adjust hyperparameters like batch size, epochs, and learning rate in the notebook.

Run the training section in the notebook to train the Multi-Attention Y-Net model.

## Evaluation

The notebook includes detailed evaluation methods:
- **Quantitative Metrics:**
  - Dice Coefficient
  - Intersection over Union (IoU)
- **Qualitative Results:**
  - Visualizations of ground truth vs. predicted segmentations.

## Results

Segmentation results and metric evaluations are provided in the notebook, with options to save visualizations and metrics for further analysis.

## References

This implementation is based on:
- Farshad, A., et al. "Y-net: A spatio-spectral dual-encoder network for medical image segmentation." Medical Image Computing and Computer-Assisted Intervention MICCAI 2022. Springer Nature, 2022.
- He, Y., et al. "Topology guaranteed segmentation of the human retina from OCT using convolutional neural networks." 2018.
- Li, J., et al. "Multi-scale GCN-assisted two-stage network for joint segmentation of retinal layers and disc in peripapillary OCT images." 2021.



