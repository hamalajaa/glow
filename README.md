# Glow

This notebook features a PyTorch implementation of a glow proposed by Kingma, D. P. &amp; Dhariwal, P. (2018) with novel experimentation with CIFAR-10 dataset. 

This implementation is primarily designed to be run on Google Colab (with a mounted Google Drive for file management) using a single GPU but can be extended also to other environments with slight changes. As this implementation currently utilizes only a single GPU unit, training doesn't scale properly into more complex model configurations or larger number of training epochs. For the reference, the following table represents approximated computation times for some configurations:

|                | 1 Batch | 1 Epoch (=781 batches) | 50 Epochs     | 2000 Epochs   |
| -------------- | ------- | ---------------------- | ------------- | ------------- |
| L = 2, D = 10  | 0.33s   | 258s = 5.6min          | 215min = 3.6h | 143.2h = 6d   |
| L = 3, D = 10  | 0.43s   | 336s = 4.3min          | 280min = 4.7h | 186.6h = 7.8d |
| L = 3, D = 32  | 1.38s   | 1080 = 18min           | 900min = 15h  | 600h = 25d    |

### Results

Despite the indimidating computation times, the model is able to produce preliminary results also for smaller numbers of training epochs with shallow configurations. The following images represent the results for two alternative configurations:

- Config a) : L = 2, D = 10, max 52 epochs of training
- Config b) : L = 3, D = 10, max 27 epochs of training


| Configuration  | Target                             | Reconstruction                      | Random Samples                   |
| -------------- | ---------------------------------- | ----------------------------------- | -------------------------------- |
| a)             | ![](/images/cifar_Test_Target.png) | ![](/images/cifar_Test_Recon49.png) | ![](/images/cifar_Test_52_1.png) |
| b)             | ![](/images/cifar_Test_Target.png) | ![](/images/cifar_Test_Recon27.png) | ![](/images/cifar_Test_25_2.png) |

Additionally, below are three reconstructions of linear interpolations between the latent space representations of two random CIFAR-10 images for model a):

| ![](/images/cifar_Test_34__4.png) | ![](/images/cifar_Test_37__4.png) | ![](/images/cifar_Test_39__4.png) |
| --------------------------------- | --------------------------------- | --------------------------------- |


### TODO

- Support for multiple GPUs (+ other optimization)
- Extensions to other datasets

### References

Durk P Kingma and Prafulla Dhariwal, “Glow: Generative Flow with Invertible 1x1 Convolutions,” in Advances in Neural Information Processing Systems, 2018, pp. 10215–10224
