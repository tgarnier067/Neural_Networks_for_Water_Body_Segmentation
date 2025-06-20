# 🌊 AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net for Water Body Segmentation

This project implements an AER (Attention-Enhanced Multi-Scale Residual) U-Net architecture for **water body segmentation** using Sentinel-2 satellite imagery. The goal is to replicate and validate the improvements presented in the paper:

> *AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net Structure for Water Body Segmentation*  
> Naga Surekha Jonnala, Shaik Siraaj, Y. Prastuti, P. Chinnababu, B. Praveen Babu, Shonak Bansal, Prashant Upadhyaya, Krishna Prakash, Mohammad Rashed Iqbal Faruque, & K. S. Al-mugren

📦 Dataset available on Kaggle: [Satellite Images of Water Bodies](https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies)

---

## Paper

Please, first, read the paper that we wrote, with respect to this project (it's in the git folder, with the name ...). 

---

## 🎯 Objectives

- Reproduce the results from the original AER U-Net paper using Sentinel-2 satellite images.
- Demonstrate that the enhancements to the classic U-Net—through attention mechanisms and residual blocks—improve segmentation performance.

---

## 📁 Project Structure

### 📓 Notebooks

- `01_Collect_data_from_Kaggle.ipynb`  
  Downloads the dataset from Kaggle and extracts the content. Useful for the first data collection step.

- `02_Collect_data_from_Drive.ipynb`  
  Alternative method to fetch data from Google Drive for easier and faster access during development.

- `03_Exploration_of_data.ipynb`  
  Data exploration and visualization: image/mask previews, size distributions, water pixel ratios, etc.

AER UNets Models family : Applies modifications to the base U-Net by adding attention and/or residual blocks to reproduce AER models. Evaluates model performance on the dataset.

- `04_AER-U-Net.ipynb`

  Add attention and residual blocks

- `05_AE-U-Net.ipynb`

  Add attention blocks

- `06_R-U-Net.ipynb`

  Add residual blocks

- `07_U-Net.ipynb`

  Baseline Model : UNet
  
- `08_AA_AER-U-Net.ipynb`

  Add attention aware convolution blocks, instead of simple convolution blocks

SE UNets Models family : Applies modifications to the base U-Net by adding attention and/or residual blocks through convolution blocks. Evaluates model performance on the dataset.

- `09_SE_U-Net.ipynb`

  Add attention (SE) in convolution blocks

- `10_SE_R_U-Net.ipynb`

  Add attention (SE) and residual connections in convolution blocks

- `11_R-U-Net.ipynb`

  Add residual connections in convolution blocks


- `12_Results and Analysis.ipynb`

  Plots, tables, metrics and interpretation of the previous results

- `13_Final_Notebook.ipynb`

  Notebook used for replication (see replication part)

  
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

Use notebook 14, please make sur to first download the data in appropriate folders, or to change the file path in the code. Otherwise, ask us (see contact) for access to the drive, and run the notebook 2 before running the notebook 14.


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

