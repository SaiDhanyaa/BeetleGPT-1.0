# BeetleGPT 1.0

![Beetle](https://www.color-meanings.com/wp-content/uploads/2022/08/Polybothris-sumptuosa-gemma-1089x1536.jpeg)

# Zero-Shot Coordinate Prediction for Beetle Elytra Measurement

This repository contains the project **"Zero-Shot Coordinate Prediction for Beetle Elytra Measurement,"** which focuses on automating the process of generating beetle elytra coordinates without relying on Zooniverse, a citizen science platform. The project aims to facilitate large-scale entomological studies by providing an efficient method for measuring beetle elytra length and width.

## 📋 Project Overview

### Goal
- Automate beetle elytra coordinate generation without relying on Zooniverse.
- Emphasize the significance of this automation for large-scale entomological studies.

### Methodology
The project involves several key steps:
1. **Dataset Acquisition and Preprocessing:**
   - Downloaded the 2018 NEON dataset from [Hugging Face](https://huggingface.co/datasets/imageomics/2018-NEON-beetles).
   - Focused on 577 original high-resolution group images for detailed analysis.
   - Processed masked images to identify beetles using bounding boxes and removed 102 incorrect masks, leaving 474 valid ones.
   - Retained merged bounding boxes for overlapping beetles to avoid data loss.

2. **Ground Truth Creation:**
   - Generated `GT.csv` from `BeetleMeasurement.csv` containing image IDs, original image dimensions, bounding box coordinates, and elytra length and width.

3. **Model Architecture:**
   - Used ResNet as the backbone for feature extraction, combined with a regression head for coordinate prediction.
   - Split data into 70% training and 30% testing. Further divided the training data into 80% training and 20% validation sets.
   - Employed Mean Squared Error (MSE) as the validation metric.

### Results
- Achieved high training and validation accuracy using MSE for coordinate prediction accuracy.
- Retained overlapping beetle cases with merged bounding boxes to balance precision and data retention.

### Challenges
- Overlapping beetles caused merged bounding boxes, which were retained to prevent data loss.

### Next Steps
- Plan to apply SAM + Zero-Shot Object Detection for testing and predict elytra length and width.
- Develop a multi-class classification model to classify beetle species/genus based on elytra measurements.

### Future Goals
- Automate the classification process to detect beetle coordinates, calculate length, width, area, and classify under the correct species/genus.
- Develop a foundational Visual Language Model (VLM) tailored for beetle elytra analysis (BeetleGPT 1.0).

## 📂 Repository Structure

```
/data/                  # Contains raw and processed datasets
/scripts/               # Scripts for data preprocessing, training, and evaluation
/models/                # Trained model weights and configurations
/reports/               # Project reports and results
README.md               # Project overview and details (this file)
```

## 🛠️ Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/beetle-elytra-prediction.git
   ```
2. **Install the required packages:**
   Ensure you have Python 3.x and necessary libraries installed:
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the scripts:**
   Navigate to the `/scripts/` directory and execute the scripts to preprocess data, train the model, and evaluate the results.

## 🤝 Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss improvements or suggestions.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

For questions or collaborations, please contact [Dhanyapriya Somasundaram](mailto:dhanyapriyas@arizona.edu).
