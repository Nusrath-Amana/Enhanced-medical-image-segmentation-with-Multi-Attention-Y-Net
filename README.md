# Multi-Attention Y-Net: A Spatiospectral Dual-Encoder Network for Medical Image Segmentation

## Abstract
Automated segmentation of retinal optical coherence tomography (OCT) images is crucial for diagnosing and monitoring eye diseases such as diabetic macular edema (DME) and age-related macular degeneration (AMD). The proposed Multi-Attention Y-Net (MA-YNet) builds upon Y-Net by integrating both spectral and spatial features to enhance segmentation performance. The method includes enhancements to the spatial encoder through a residual structure with a simple attention module and the use of multi-head self-attention at the lowest-level features. The proposed method achieves a mean Dice score of 0.86, advancing automated OCT image analysis.

## Index Terms
- OCT segmentation
- Y-Net
- Multi-head self-attention
- Channel attention
- Spatial attention

## I. Introduction
Automated retinal OCT segmentation is essential for diagnosing various retinal diseases. Existing methods often face challenges in segmenting fluid pockets due to their inability to extract fine-grained features from complex OCT images. Y-Net has improved segmentation by integrating spectral and spatial features, yet fine-grained feature extraction and multiscale variations still pose challenges.

The proposed MA-YNet improves on Y-Net by adding:
- **Residual structure** with a simple attention module to enhance the spatial encoder.
- **Multi-head self-attention** to reconstruct feature maps and improve segmentation.
- **Channel and spatial attention** modules for better feature fusion across scales.

## II. Related Work
Earlier methods like graph-based approaches and hybrid models combining neural networks with graph techniques were used for retinal OCT segmentation. More recent developments have focused on autoencoder architectures such as U-Net and Y-Net, with attention mechanisms and multiscale feature integration. MA-YNet builds upon the strengths of these methods, improving fine-grained segmentation and multiscale representation.

## III. Method
### A. Segmentation Framework
MA-YNet uses a dual-encoder architecture with spatial and spectral branches:
- **Spatial Encoder (Ec)**: Extracts local spatial features using a residual structure and attention module.
- **Spectral Encoder (Ef)**: Extracts global frequency-domain features using Fast Fourier Convolutional (FFC) blocks.
- **Decoder (G)**: Combines spatial and spectral features, using multi-head self-attention and attention modules for feature fusion.

### B. Spatial Encoder Components
1. **Residual Block**: Improves gradient flow and feature extraction by incorporating residual connections and attention mechanisms.
2. **simAM (Simple Attention Module)**: A parameter-free attention mechanism that evaluates neuron importance to enhance feature extraction.
3. **Attention Modules (SAM and CAM)**: Used for feature fusion at various stages to handle multiscale features.
4. **Multi-Head Self-Attention (MSA)**: Captures global dependencies and refines pixel-level segmentation.

### C. Spectral Encoder Components
1. **FFC Block**: A convolutional block that processes local and global features from the frequency domain.
2. **Fourier Unit**: Applies FFT to the features and integrates them back into the spatial domain.

### D. Loss Functions
- **Dice Loss**: Measures the overlap between predicted and ground truth segmentation maps.
- **Cross-Entropy Loss**: Maximizes information gain between true and predicted labels.
- **Combined Loss**: A weighted sum of Dice and Cross-Entropy Loss.

## IV. Experiments
### A. Experimental Setup
The Duke OCT dataset, consisting of scans from 10 patients, is used for training and testing. The protocol follows prior works with scans from subjects 1-6 for training, 7-8 for validation, and 9-10 for testing. Training is done with:
- Batch size: 10
- Learning rate: 5 × 10^-4
- Weight decay: 1 × 10^-4
- Max epochs: 100
- Optimizer: Adam

The images are resized to 224x224, and the combined loss function is used with equal weights for Dice and cross-entropy loss.

### B. Results
The MA-YNet model is compared against Y-Net and other baseline approaches using the Duke OCT dataset. Preliminary results indicate an improvement in segmentation accuracy, achieving a mean Dice score of 0.86. Further experimentation with focal loss did not show significant performance improvements.

## V. Conclusion
MA-YNet improves upon Y-Net by integrating attention mechanisms and residual structures, enhancing the extraction of fine-grained features and multiscale target representation. The method demonstrates superior performance in OCT segmentation, advancing the state of the art in medical image analysis.

## References
1. Y-Net: A Dual-Encoder Architecture for OCT Image Segmentation
2. He et al., OCT segmentation through topology-based methods
3. MDAN-U-Net for enhanced segmentation performance using multiscale features
4. Duke OCT Dataset for retinal OCT image analysis

## Acknowledgments
Special thanks to the collaborators and experts who annotated the dataset and contributed to the experimental setup.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

