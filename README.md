# 🌕 Lunar Crater Detection using Chandrayaan-2 Imagery

This repository presents an end-to-end pipeline for detecting lunar craters using high-resolution imagery captured by ISRO’s **Chandrayaan-2** mission. The system leverages deep learning for object detection, enhanced by high-capacity backbone architectures, and has been evaluated on two distinct datasets: **OHRC** and **TMC-2**.

---

## 📌 Project Highlights

- 📡 Utilized imagery from Chandrayaan-2’s **Orbiter High Resolution Camera (OHRC)** and **Terrain Mapping Camera-2 (TMC-2)**.
- 🧠 Built on the **YOLOv11** detection framework, enhanced with **ResNet101** from the [Timm](https://github.com/huggingface/pytorch-image-models) library.
- 🏷️ Supervised dataset created with precise crater annotations using **Roboflow**.
- 📈 Achieved robust performance on both OHRC and TMC-2 datasets, demonstrating high detection accuracy and generalization.

---

## 🛰️ Datasets Used

| Camera | Resolution | Tile Sizes Used |
|--------|------------|-----------------|
| OHRC   | ~0.25 m/pixel | 304×640 px |
| TMC-2  | ~5 m/pixel     | 79×640 px  |

All images were preprocessed to maintain aspect ratio and input compatibility for deep learning pipelines. Bounding box annotations were prepared manually via Roboflow.

---

## 🧠 Model Architecture

- Detection Framework: **Ultralytics YOLOv11**
- Backbone: **ResNet101** (replacing default YOLO backbone)
- Framework modifications made to integrate [Timm](https://rwightman.github.io/pytorch-image-models/) backbones.
- Optimized for crater-like morphology and varying terrain texture typical in lunar surfaces.

---

## 📊 Results

### OHRC Results (Epochs 0–300)
- **Precision:** 74.6%
- **Recall:** 66.8%
- **mAP@0.50:** 66.7%
- **mAP@0.50:0.95:** 32.4%

### TMC-2 Results (Epochs 0–150)
- **Precision:** 80.9%
- **Recall:** 51.9%
- **mAP@0.50:** 58.7%
- **mAP@0.50:0.95:** 33.7%

These results indicate consistent improvement in both detection accuracy and bounding box localization across epochs. mAP@50–95 scores particularly demonstrate the model's ability to perform well under strict IoU thresholds, reflecting its spatial precision.

---

## 🔗 Google Colab Notebooks

- 📘 **OHRC Code:**  
  [Colab Notebook](https://colab.research.google.com/drive/1FNppCZmDVBs3GjI-32QID0mW6Ii9GWJk?usp=sharing)

- 📙 **TMC-2 Code:**  
  [Colab Notebook](https://colab.research.google.com/drive/1BivB5VF1-MvjGvyNr4cGcxqugsAzKs1x?usp=sharing)

---

## 🚀 How to Use

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/lunar-crater-detector.git
    cd lunar-crater-detector
    ```

2. Open the relevant Colab notebook (OHRC or TMC-2) using the links above.

3. Run through the cells to:
    - Load and visualize datasets
    - Initialize and train the YOLOv11 model
    - Evaluate and visualize detection outputs

4. Optionally, customize model parameters or backbones via the `timm` interface.

---

## 🧩 Future Work

- Incorporation of **TMC-2 elevation data** to improve crater detection in shadowed/ambiguous regions.
- Enhanced labeling with tools like **ArcGIS Pro** for geospatial alignment.
- Experimentation with **segmentation-based models** for crater rims and interiors.
- Expansion to include datasets from other planetary bodies (e.g., Mars, Mercury).

---

## 📜 License

This project is released under the [MIT License](LICENSE).

---

## 🌌 Applications

- Automated planetary mapping  
- Surface age estimation  
- Lunar mission hazard planning  
- Geological feature extraction from high-res imagery

---

