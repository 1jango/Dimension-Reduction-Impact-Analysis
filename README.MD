MNIST Classification: The Impact of PCA on Model Efficiency

Project Overview



This project explores the relationship between Dimensionality Reduction (using PCA) and the performance of various Machine Learning classifiers on the MNIST dataset. The goal was to reduce the feature space from 784 pixels to a set of Principal Components retaining 90% of the data variance and analyze the trade-offs in terms of speed and accuracy.

&nbsp;	

&nbsp;	

The most striking result is the massive reduction in computational time across all models.



k-Nearest Neighbors (kNN) achieved a 7.1x speedup. Because kNN must calculate distances between points, reducing the number of dimensions directly slashes the number of mathematical operations required per prediction.



Logistic Regression saw an even more significant improvement (~7.5x faster), demonstrating that training linear models on "concentrated" information is much more efficient than processing raw, noisy pixels.



The Accuracy Paradox (Noise Reduction)
Counterintuitively, reducing the amount of data actually increased accuracy in both cases:
kNN: +0.65% increase
Logistic Regression: +2.25% increase


Why? The original MNIST images contain "noise" (randomly lit pixels in the background or slight variations in writing style). PCA acts as a denoising filter. By keeping only the top components that explain 90% of the variance, we discard the "junk" data, allowing the classifiers to focus on the essential shapes and structures of the digits.

Handling the "Curse of Dimensionality"
This project proves that the Curse of Dimensionality (where models perform worse and slower as more features are added) is a real challenge in Image Processing. PCA successfully mitigated this by transforming 784 raw pixels into a compact feature set, proving that:



&nbsp;   We don't need all the data to get the best results.



&nbsp;   Computational efficiency can be achieved without sacrificing (and even improving) model quality.



Summary Conclusion

For the MNIST dataset, PCA is not just a compression tool—it is a performance enhancer. The best overall performance was achieved by the kNN model on PCA-reduced data, offering a superior balance of high accuracy (95.40%) and rapid execution.

