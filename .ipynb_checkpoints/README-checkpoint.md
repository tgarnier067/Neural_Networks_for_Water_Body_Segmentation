# 🌊 AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net for Water Body Segmentation

This project implements an AER (Attention-Enhanced Multi-Scale Residual) U-Net architecture for **water body segmentation** using Sentinel-2 satellite imagery. The goal is to replicate and validate the improvements presented in the paper:

> *AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net Structure for Water Body Segmentation*  
> Naga Surekha Jonnala, Shaik Siraaj, Y. Prastuti, P. Chinnababu, B. Praveen Babu, Shonak Bansal, Prashant Upadhyaya, Krishna Prakash, Mohammad Rashed Iqbal Faruque, & K. S. Al-mugren

📦 Dataset available on Kaggle: [Satellite Images of Water Bodies](https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies)

---
## 📄 Paper

We encourage you to first read the paper we wrote as part of this project. You can find it in this GitHub repository under the filename ...

---

## 🎯 Objectives

- Reproduce the results from the original AER U-Net paper using Sentinel-2 satellite images.
- Demonstrate that the enhancements to the classic U-Net—through attention mechanisms and residual blocks—improve segmentation performance.

---

## 📁 Project Structure

### 📓 Notebooks

#### 📥 Data Collection & Exploration
- `01_Collect_data_from_Kaggle.ipynb`  
  Download and extract the dataset from Kaggle.

- `02_Collect_data_from_Drive.ipynb`  
  Load dataset from Google Drive (faster during development).

- `03_Exploration_of_data.ipynb`  
  Data visualization: sample previews, size & pixel ratio analysis.

#### 🧪 Baseline & AER Model Family
- `07_U-Net.ipynb`  
  Baseline U-Net.

- `06_R-U-Net.ipynb`  
  U-Net + residual blocks.

- `05_AE-U-Net.ipynb`  
  U-Net + attention blocks.

- `04_AER-U-Net.ipynb`  
  U-Net + both attention and residual blocks (AER model).

- `08_AA_AER-U-Net.ipynb`  
  Experimental: replaces convs with Attention Augmented Convolutions (AA).

#### 🧬 SE-based Models (Attention inside conv blocks)
- `09_SE_U-Net.ipynb`  
  U-Net + SE attention in conv blocks.

- `11_R-U-Net.ipynb`  
  U-Net + residuals in conv blocks.

- `10_SE_R_U-Net.ipynb`  
  U-Net + SE attention and residuals in conv blocks.

#### 📊 Evaluation & Replication
- `12_Results and Analysis.ipynb`  
  Plots, tables, metrics, and interpretation.

- `13_Final_Notebook.ipynb`  
  Final notebook used for replication (see 📄 Reproducibility).

  
---

## 📊 Results

### 🔁 AER U-Net Replication Attempt

| Model     | Accuracy | Precision | Recall | F1 Score | IoU   |
|-----------|----------|-----------|--------|----------|-------|
| U-Net     | **0.8372**   | **0.8425**    | 0.6434 | 0.7296   | 0.5743 |
| R-U-Net   | 0.8237   | 0.7782    | 0.6764 | 0.7237   | 0.5670 |
| AE U-Net  | 0.8314   | 0.7606    | **0.7387** | **0.7495**   | **0.5994** |
| AER U-Net | 0.8237   | 0.7725    | 0.6855 | 0.7264   | 0.5704 |

### 🧪 SE and Residuals Inside Convolutional Blocks

| Model       | Accuracy | Precision | Recall | F1 Score | IoU   |
|-------------|----------|-----------|--------|----------|-------|
| U-Net       | 0.8532   | 0.8207    | 0.7293 | 0.7723   | 0.6290 |
| R-U-Net     | 0.8072   | 0.7487    | 0.6552 | 0.6988   | 0.5371 |
| SE U-Net    | 0.8532   | 0.8207    | 0.7293 | 0.7723   | 0.6290 |
| **SE-R-U-Net** | **0.8688**   | **0.8593**    | **0.7365** | **0.7932**   | **0.6572** |

The original AER U-Net implementation did not reproduce the high performance reported in the paper, likely due to limited training time. Among all tested models, SE-R-UNet achieved the best results, confirming that combining residual connections and attention mechanisms improves segmentation performance. However, recall remained lower than precision across models, suggesting under-detection of water bodies.
A more detailed analysis and comparison of the results is provided in the accompanying paper.

---

## Reproductability

To reproduce our results, run notebook 13.
Make sure the dataset is correctly downloaded and placed in the appropriate folders, or update the file paths in the code accordingly. Alternatively, you can contact us (see Contact) to request access to the preprocessed data on Google Drive. In that case, run notebook 2 first to set up the environment, then proceed to notebook 13.
You will also need to select the model you wish to replicate by uncommenting the corresponding cell in the notebook.


---

## 📚 References

- Jonnala, N. S., Siraaj, S., Prastuti, Y., Chinnababu, P., Praveen Babu, B., Bansal, S., Upadhyaya, P., Prakash, K., Faruque, M. R. I., & Al-Mugren, K. S. (2023).  
  **AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net Structure for Water Body Segmentation**.  
  _Scientific Reports_. https://www.nature.com/articles/s41598-025-99322-z

- Ronneberger, O., Fischer, P., & Brox, T. (2015).  
  **U-Net: Convolutional Networks for Biomedical Image Segmentation**.  
  _MICCAI 2015_. https://arxiv.org/abs/1505.04597

- Bello, I., Zoph, B., Vaswani, A., Shlens, J., & Le, Q. V. (2019).  
  **Attention Augmented Convolutional Networks**.  
  _Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)_, 3285–3294. :contentReference[oaicite:1]{index=1}

- Hu, J., Shen, L., & Sun, G. (2018).  
  **Squeeze-and-Excitation Networks**.  
  _Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)_, 7132–7141. :contentReference[oaicite:2]{index=2}

- Dataset used:  
  [Satellite Images of Water Bodies on Kaggle](https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies)

- Code used:  
  U-Net code adapted from [UNet-Water-Segmentation GitHub repository](https://github.com/ThorOdinson246/UNet-Water-Segmentation).

---
## 📬 Contact

For questions or collaboration opportunities, feel free to reach out:

- **Thomas Garnier** – [tgarnier067@gmail.com](mailto:tgarnier067@gmail.com)  
- **Jamil Nassar** – [jamilnassar1@gmail.com](mailto:jamilnassar1@gmail.com)

