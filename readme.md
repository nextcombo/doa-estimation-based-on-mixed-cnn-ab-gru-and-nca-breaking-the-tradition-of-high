# DOA Estimation Based on Mixed CNN-AB-GRU and NCA: Breaking the Tradition of High Precision Solutions[With MATLAB Code]

The proposed framework combines a Convolutional Neural Network (CNN) with an Attention-based Gated Recurrent Unit (GRU), and NCA for end-to-end DOA estimation, breaking through traditional high-precision estimation methods. The core of this method lies in reconstructing the angle of incidence from the received signals in an array. Traditional algorithms like MUSIC rely on ideal signal assumptions, which significantly degrade their performance under low SNR and small number of snapshots. Surface learning methods are limited by their feature representation capabilities, failing to meet high-precision requirements. This paper introduces a novel hybrid CNN-Attention-based GRU-NCA framework for end-to-end DOA estimation, eliminating the need for complex spectral peak searches, achieving high precision and robustness for multi-target joint estimation.

The core system model employs an N-element uniform linear array (ULA) with element spacing of λ/2, where the received data model is:

where Ω is the received data matrix (K is the number of snapshots), V is the steering vector matrix, I is the incident signal, and W is Gaussian white noise. The specific form of the steering vector matrix is:

To simplify computation and retain key information, we extract upper triangular non-zero elements from the spatial covariance matrix, separating real and imaginary parts to form real-valued feature vectors:

(...)

The core framework consists of two parts: "Deep Feature Extraction" and "Adaptive Feature Selection," achieving efficient transformation from raw features to discriminative features.

2.1 Dual-branch heterogeneous feature extraction adopts dual-branch networks to achieve feature complementarity:

1  
CNN branch: Through 1D convolution, batch normalization, and ReLU activation, it captures the local spatiotemporal structure of the covariance features, outputting local deep features;
2  
Attention GRU branch: Using GRU to model temporal dependencies (core formula is provided below), stacking multiple attention layers enhances critical features, outputting sequentially enhanced features.

GRU core formula:
Concatenate the outputs of both branches to obtain fused features.

2.2 NCA-MRMR feature selection aims to reduce redundancy of high-dimensional features by using NCA and MRMR weighted fusion strategies:

1  
NCA-MRMR weighted fusion strategy:
NCA (Neighborhood Component Analysis): By optimizing the feature space distance, outputs feature weights;
2  
MRMR (Maximum Relevance Minimum Redundancy): While ensuring high relevance between features and labels, minimize redundancy among features, output weights.
3  
Comprehensive sorting: select the top T optimal features.
III. End-to-end DOA Estimation and Performance Advantages will preferentially use the selected features as input to a fully connected classification network, which outputs DOA estimation results through ReLU activation, max pooling, and Softmax.
Compared with the traditional methods, this framework has obvious advantages:
1  
Lose the ideal assumption: no need for eigenvalue decomposition, spectral peak search, data-driven adaptation to complex scenarios.
2  
Feature complementarity: CNN and self-attention GRU capture local and temporal features respectively, with stronger representation capabilities.
3  
4  
Engineering-friendly: end-to-end inference, no need for manual intervention, convenient for real-time deployment.
IV. Conclusion The proposed CNN-AB-GRU-NCA DOA estimation framework, integrating deep learning with array signal mechanisms, overcomes the performance bottlenecks of traditional methods and achieves strong noise resistance, high precision, and multi-target DOA joint estimation. It provides a new and efficient approach for practical engineering scenarios such as radar and electronic reconnaissance.

## Images

![(DOA Estimation)DOA Estimation Based on Mixed CNN-AB-GRU and NCA: Breaking Through the High Accuracy Traditional Solutions [with MATLAB Code]](01.jpg)
![(DOA Estimation)DOA Estimation Based on Mixed CNN-AB-GRU and NCA: Breaking Through the High Accuracy Traditional Solutions [with MATLAB Code]](02.jpg)
![(DOA Estimation)DOA Estimation Based on Mixed CNN-AB-GRU and NCA: Breaking Through the High Accuracy Traditional Solutions [with MATLAB Code]](03.jpg)
![(DOA Estimation)DOA Estimation Based on Mixed CNN-AB-GRU and NCA: Breaking Through the High Accuracy Traditional Solutions [with MATLAB Code]](04.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
