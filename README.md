# PyTorch Playing Card Classifier 🃏

## Overview
This repository contains a PyTorch-based computer vision project that classifies images of playing cards. Using transfer learning with a pre-trained **EfficientNet-B0** model, the classifier is capable of identifying 53 different classes of playing cards (the 52 standard cards of a deck + the Joker). 

The goal of this project was to understand the core paradigms of deep learning in PyTorch, including creating custom datasets, configuring model architectures, and writing training loops from scratch.

## 🏆 Acknowledgments & Attributions
This project was built while learning from the incredibly helpful tutorials created by **Rob Mulla**. A huge thank you to him for the educational content! 

If you want to learn how to build the base of this model step-by-step, check out the original resources used:
* **YouTube Tutorial**: [Build Your First Pytorch Model In Minutes! [Tutorial + Code]](https://youtu.be/tHL5STNJKag)
* **Kaggle Notebook**: [Train Your First PyTorch Model (Card Classifier)](https://www.kaggle.com/code/robikscube/train-your-first-pytorch-model-card-classifier)

## Key Features & Learnings
* **Data Processing**: Implemented custom PyTorch `Dataset` and `DataLoader` classes to load, resize (to 128x128), and batch the image data.
* **Transfer Learning**: Utilized the `timm` (PyTorch Image Models) library to leverage a pre-trained `efficientnet_b0` architecture, modifying the final classifier layer to output 53 classes.

* **Custom Training Loop**: Wrote a complete training and validation loop from scratch using `CrossEntropyLoss` and the `Adam` optimizer.
* **Model Evaluation (Accuracy)**: **[Custom Addition]** Extended the original tutorial by writing a custom evaluation script to calculate the overall accuracy of the model across the unseen test dataset.
* **GPU Acceleration**: Configured the model and data tensors to train efficiently on CUDA-enabled GPUs.

## Dataset
The dataset contains images of playing cards divided into `train`, `valid`, and `test` directories. Each folder contains sub-directories for the 53 specific card classes. 

## 🚀 Running on Kaggle (Recommended)
Because training deep learning models requires significant compute power, running this project on Kaggle is highly recommended so you can take advantage of their free GPUs.

1. **Create a Kaggle Notebook**: Go to Kaggle, click on **Code**, and select **New Notebook**.
2. **Add the Dataset**: Click **Add Data** in the right-hand panel, search for the playing card image dataset used in the original tutorial, and add it to your environment.
3. **Enable GPU**: Go to the **Notebook Options** (right panel) -> **Accelerator** -> select **GPU T4 x2** (or P100).
4. **Upload Code**: Upload this repository's notebook or copy and paste the scripts directly into the Kaggle cells.
5. **Update File Paths**: Ensure your `data_dir` variables point to the correct Kaggle input path (e.g., `/kaggle/input/cards-image-datasetclassification/`).

## Requirements (Local Setup)
If you prefer to run this locally, you will need the following Python libraries installed:
```bash
pip install torch torchvision timm matplotlib pandas numpy tqdm
