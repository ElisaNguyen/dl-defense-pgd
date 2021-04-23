# Defending against Projected Gradient Descent
A project in the frame of the Deep Learning course at the University of Twente. Run the notebooks as they are to reproduce the project. 

### Abstract
Recent studies have shown that minor perturbations in the input space may cause neural networks to misclassify data samples at a high confidence level. The efficacy of these adversarial attacks, despite the high perceptual similarity between adversarial examples and natural data, expose the network's flawed decision boundaries. To address this problem, this project inspects a convolutional neural network's adversarial robustness against projected gradient descent (PGD). Adversarial training and data augmentation techniques are studied as defensive mechanisms against PGD. It appears that adversarial training serves as an effective defense against PGD, while data augmentation minimally contributes to the model's adversarial robustness.

### Data
This project used the Fashion-MNIST dataset. 

### Model
The underlying model is a CNN, based on the LeNet5 architecture and trained with early stopping. The following hyperparameters were tuned with a random search of 100 iterations. 
- Optimizers
- Kernel size
- Pool function

### Method and Notebooks
Different defense configurations were studied. The PGD attack from [1] is implemented. Below is a list describing the contents of each notebook:
| Notebook       |  Description     |
| :------------- | :-----------  |
|  Hyperparameter tuning.ipynb |  Random search of hyperparameters    |
|  Model training.ipynb   | Training of the CNN model  |
|  Attack.ipynb   | PGD attack implementation  |
|  DA.ipynb   |  Data Augmentation (DA) Defense, each Data Augmentation technique applied once, thus inflating the dataset size  |
|  CDA.ipynb   | Combined Data Augmentation (CDA) Defense, combining all DA techniques, thus doubling the dataset in size |
|  FAT.ipynb   | Full Adversarial Training (FAT) Defense, so the model is only trained with adversarial examples |
|  MAT.ipynb   | Mixed Aversarial Training (MAT) Defense, so the model is trained on 50% adversarial and 50% clean examples picked at random |
|  FAT_DA.ipynb   | FAT + DA defense     |
|  MAT_DA.ipynb   | MAT + DA defense     |
|  FAT_CDA.ipynb   | FAT + CDA defense     |
|  MAT_CDA.ipynb   | MAT + CDA defense     |

### Requirements
- ```python > 3.7```
- Libraries: ```torch, numpy, pandas, matplotlib, sklearn, advertorch```

### Bibliography
[1] Ding, Gavin Weiguang; Wang, Luyu; Jin, Xiaomeng (2019): advertorch v0.1: An Adversarial Robustness Toolbox based on PyTorch. Available online at http://arxiv.org/pdf/1902.07623v1.
