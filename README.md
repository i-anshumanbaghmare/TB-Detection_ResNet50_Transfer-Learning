# TB-Det: Researching Current Transfer Learning & XAI in Clinical Imaging

## Project Overview

This repository is dedicated to the study of **model robustness and data sensitivity** within the development of Computer-Aided Diagnostic (CAD) systems. Our research focuses on the classification of Chest X-rays (CXR) to detect Tuberculosis (TB)—treating it not merely as a standard pattern recognition task, but as a high-stakes clinical application where precision, interpretability, and trust are paramount.

The core of this project is a comparative study of **Transfer Learning** using deep convolutional neural networks. We utilize baseline models, such as **ResNet50**, and pivot toward advanced techniques like **LoRA (Low-Rank Adaptation)** fine-tuning to handle medical data that is exceptionally sensitive to architectural changes.

In medical AI, a "prediction" alone is insufficient. Therefore, this project explores the intersection of deep feature extraction and **Explainable AI (XAI)**. By generating visual evidence through heatmaps, we justify the model’s clinical predictions, building a transparent framework that clinicians can audit, understand, and ultimately rely on for diagnostic support.

---

## Project Progress and Achievement

This project contributes to the broader field of Computer Science and Medical AI by documenting the transition from "Black Box" models to "Clinically Transparent" systems.

1. **The Transition to LoRA (Low-Rank Adaptation):**
Moving beyond standard fine-tuning, we are investigating the application of LoRA for clinical data. By training low-rank matrices while keeping the base model specialized, we aim to capture micro-detail sensitivity without the catastrophic forgetting or overfitting typically seen in small-sample medical datasets.
2. **Bridging the Trust Gap with XAI:**
We implemented **Grad-CAM (Gradient-weighted Class Activation Mapping)** to generate visual evidence. By producing heatmaps that highlight the specific regions influencing a prediction, we transform the model from a "decision-maker" into a "decision-supporter" for radiologists.
3. **Studying Baseline Errors:**
By analyzing where ResNet50 failed, we have gained insights into the error surfaces of deep models in clinical contexts. This research is currently feeding into a custom, monochromatic-sensitive model (**In Progress**) designed to outperform general-purpose architectures.

---

## Key Features and Technologies

* **Clinical Image Processing:** We study Chest X-ray images and use **STA image processing** to preserve biological characteristics and transfer them to the model sensitively.
* **Transfer Learning:** Utilizes the **ResNet50V2 (Baseline)** model pre-trained on ImageNet weights. We identified that ImageNet characteristics differ significantly from CXR data, leading to the development of a main model trained on micro-detail sensitive, monochromatic datasets (**In Progress**).
* **Dual-Stage Training:** Employs a robust strategy of **(1) Head Training** (frozen base) followed by **(2) Fine-Tuning** (unfrozen top layers) with a very low learning rate.
* **Explainable AI (XAI):** Implements Grad-CAM to highlight pathological regions of the lung influencing the model's prediction.
* **Performance Metrics:** Focuses on clinically relevant metrics such as **Area Under the Curve (AUC)**, **Recall (Sensitivity)**, and **Precision**.

---

## The Baseline Study: A 'Productive Failure' with ResNet50

Every significant research breakthrough begins with the identification of a baseline’s limitations. In the initial phase of this project, we employed ResNet50V2—a gold standard in general computer vision—pre-trained on the ImageNet dataset.

**The Findings:**
While ResNet50 achieved respectable metrics on paper, it failed to meet the rigorous standards required for clinical deployment. We identified a fundamental **domain gap**:

* **Semantic Divergence:** ImageNet features are optimized for natural objects (texture, color, and macro-shapes like animals or vehicles).
* **Clinical Nuance:** Chest X-rays are monochromatic, high-bit-depth images where the diagnostic signal lies in micro-details—subtle opacities, pleural thickening, and architectural distortion of lung parenchyma.

This "productive failure" proved that standard Transfer Learning is often too "coarse" for medical imaging, necessitating architectures that respect high-resolution, monochromatic data.

---

## Domain-Level Data Processing

Understanding the data is the first step of the research. We applied **Spatio-Temporal Analysis (STA)** and specialized image processing to preserve essential biological characteristics.

* **Biological Preservation:** We focused on maintaining the integrity of the costophrenic angles and hilar regions, ensuring that preprocessing did not artifactually introduce "pathology" or erase subtle lesions.
* **Monochromatic Sensitivity:** Unlike standard RGB processing, our pipeline was designed to handle the specific intensity distributions found in clinical CXR hardware.

---

## Data

**Kaggle:** [Chest X-ray Dataset (Montgomery and Shenzhen)](https://www.google.com/search?q=https://www.kaggle.com/datasets/raddar/tuberculosis-chest-xrays-montgomery-and-shenzhen)

**Primary Sources:**

* **Montgomery County CXR Set:** [Link to Source](https://data.lhncbc.nlm.nih.gov/public/Tuberculosis-Chest-X-ray-Datasets/Montgomery-County-CXR-Set/MontgomerySet/index.html)
* **Shenzhen Hospital CXR Set:** [Link to Source](https://data.lhncbc.nlm.nih.gov/public/Tuberculosis-Chest-X-ray-Datasets/Shenzhen-Hospital-CXR-Set/index.html)
