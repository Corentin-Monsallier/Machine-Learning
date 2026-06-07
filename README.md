# Machine Learning Projects

This repository contains three machine learning and deep learning projects, ranging from building neural networks from scratch to applying transfer learning on complex medical images.

## 🚀 Installation & Prerequisites

To run the notebooks, it is highly recommended to create a Python virtual environment (`venv` or `conda`) and install the dependencies:

```bash
pip install -r requirements.txt
```

*(Note: For Part 3, a machine equipped with a GPU and CUDA is recommended to accelerate training).*

---

## 📁 Project Structure

### [Part 1: The MNIST Database](part1.ipynb)
**Objective:** Classification of handwritten digits (0 to 9).
**Method:** Building neural networks **from scratch** (without high-level Deep Learning libraries).
- Mathematical implementation of gradient descent, backpropagation, and activation functions (ReLU, Softmax).
- Successive models: Simple linear model, Model with 1 hidden layer, Model with 2 hidden layers.

### [Part 2: The CIFAR-10 Dataset](part2.ipynb)
**Objective:** Classification of colored images into 10 classes (airplanes, dogs, cats, ships, etc.).
**Method:** Introduction to Convolutional Neural Networks (CNN) with **PyTorch**.
- Utilization of Convolutional layers, MaxPooling, and Flattening.
- Analysis of the architecture's impact on visual pattern and color recognition.
- **Data required:** When running this notebook, the `torchvision.datasets.CIFAR10` module will automatically download the dataset from the internet and extract it into a local `data` folder at the root of the repository. You don't need to download any files manually.

### [Part 3: Application to Medical Diagnosis (CBIS-DDSM)](part3.ipynb)
**Objective:** Binary medical diagnosis: classifying breast tumors (mammograms) as **Benign (0)** or **Malignant (1)**.
**Method:** *Transfer Learning* and deep neural networks using **PyTorch**.
- **Architecture:** Utilizing a pre-trained **ResNet18** model, unfreezing all layers (Full Fine-Tuning) to specifically adapt its features to radiology.
- **Challenges:** Handling class imbalance (via `pos_weight` in `BCEWithLogitsLoss`), targeted Data Augmentation, and preventing overfitting (Early Stopping).
- **Evaluation:** Mathematical optimization of the clinical decision threshold using the **ROC Curve** and Youden's J statistic to drastically minimize **False Negatives**.

---

## ⚠️ Special Instructions for Part 3 (CBIS-DDSM)

For the `part3.ipynb` notebook to work properly, you must manually download and extract the medical database, **strictly** adhering to the following folder structure.

1. **Create the `images` folder:**
   At the root of this repository, create a folder named `images`.
   ```bash
   mkdir images
   ```

2. **Download the database:**
   Download the CBIS-DDSM database archive (typically provided on Kaggle or via your school).

3. **Extract the archive (Unzip):**
   Extract the database contents **inside the `images` folder**. You must ensure that the CSV files are located exactly at the following paths:
   `images/archive/csv/mass_case_description_train_set.csv`
   `images/archive/csv/mass_case_description_test_set.csv`

   *Expected final directory tree:*
   ```text
   Machine-Learning/
   ├── part1.ipynb
   ├── part2.ipynb
   ├── part3.ipynb
   └── images/
       └── archive/
           ├── csv/
           │   ├── mass_case_description_train_set.csv
           │   └── mass_case_description_test_set.csv
           └── ... (folders containing the images)
   ```

Once this structure is in place, you can run the entire `part3.ipynb` notebook!