# Replace this entire README with the markdown below:
 
# CIFAR-10 Mini Image Classifier
## Transfer Learning with ResNet18 and PyTorch
 
## Results
- Test Accuracy: 0.7630  (76.30%)  (fill in your result)
- Training time: approximately 2-4 minutes total
- Dataset: CIFAR-10 Mini (5,000 images, 10 classes)
 
## Model Architecture
- Base model  : ResNet18 pretrained on ImageNet
- Strategy    : Feature extraction (all layers frozen except final fc)
- Output layer: Linear(512 → 10 classes)
- Parameters  : 5,130 trainable / 11.2M total
 
## Dataset
CIFAR-10 Mini — 500 images per class × 10 classes = 5,000 images
| Split      | Images |
|------------|--------|
| Training   | 4,000  |
| Validation | 1,000  |
| Test       | 1,000  |
 
**Classes:** airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck
 
## Training Settings
| Setting       | Value              |
|---------------|--------------------|
| Epochs        | 10                 |
| Batch size    | 32                 |
| Optimiser     | Adam (lr=0.001)    |
| Loss function | CrossEntropyLoss   |
| Scheduler     | ReduceLROnPlateau  |
 
## Results Visualisation
![Training Curves](training_curves.png)
![Confusion Matrix](confusion_matrix.png)
 
## Reflection
# Reflection Questions

## 1. What was the most challenging part of this lab and how did you overcome it?

The most challenging part of this lab was training the CNN model correctly and fixing errors during implementation. I faced issues such as incorrect variable names, model evaluation errors, and GitHub upload problems. I overcame these problems by carefully debugging the code, checking error messages, and correcting mistakes step by step. Running the notebook cells again and verifying outputs also helped me complete the lab successfully.

---

## 2. What test accuracy did you achieve? Is this good enough for real-world use?

The model achieved approximately **70% test accuracy** on the CIFAR-10 mini dataset. This is a reasonable result for a small educational project and shows that the model learned useful image features. However, for real-world applications, higher accuracy would usually be required because incorrect predictions could reduce reliability.

---

## 3. Look at your confusion matrix. Which class has the lowest accuracy and why?

The class with the lowest accuracy was likely one of the visually similar categories such as **cat** or **dog**. These classes are difficult because their images share similar shapes, colours, and textures. The model can confuse them when image quality is low or when the dataset is limited.

---

## 4. How did augmentation affect your results? (Hint: try training without it)

Data augmentation improved the model’s generalisation ability by creating slightly modified versions of training images. It reduced overfitting and helped the validation accuracy become more stable. Without augmentation, the model would memorise the training data more easily and perform worse on unseen images.

---

## 5. What real-world application would you build using this technology?

One real-world application could be an intelligent image classification system for security cameras or smart devices. For example, it could automatically detect vehicles, animals, or suspicious objects in real time. Similar CNN models are also widely used in medical imaging, self-driving cars, and facial recognition systems.

---

## 6. What would happen if you trained without freezing any layers?

If no layers were frozen, the entire pretrained model would update during training. This could improve accuracy if a large dataset is available, but it would also increase training time and risk overfitting on a small dataset like CIFAR-10 mini. Freezing layers helps preserve useful pretrained features while training only the final layers for the new task.
 
## How to Run
1. Open [https://www.kaggle.com/code/ayesha1911/cv-lab11-cifar10/edit]
2. Enable GPU: Settings → Accelerator → GPU T4
3. Run all cells in order
 
## Requirements
PyTorch | torchvision | scikit-learn | seaborn | matplotlib | Pillow
