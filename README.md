# 🌊 AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net for Water Body Segmentation

This project implements an AER (Attention-Enhanced Multi-Scale Residual) U-Net architecture for **water body segmentation** using Sentinel-2 satellite imagery. The goal is to replicate and validate the improvements presented in the paper:

> *AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net Structure for Water Body Segmentation*  
> Naga Surekha Jonnala, Shaik Siraaj, Y. Prastuti, P. Chinnababu, B. Praveen Babu, Shonak Bansal, Prashant Upadhyaya, Krishna Prakash, Mohammad Rashed Iqbal Faruque, & K. S. Al-mugren

📦 Dataset available on Kaggle: [Satellite Images of Water Bodies](https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies)

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

- `04_U-Net_architecture.ipynb`  
  Implements the baseline U-Net architecture and trains it on the dataset. Adapted from [UNet-Water-Segmentation GitHub repository](https://github.com/ThorOdinson246/UNet-Water-Segmentation).

- `05_AER-U-Net.ipynb`  
  Applies modifications to the base U-Net by adding attention and residual blocks (AER modules). Evaluates model performance on the dataset.

---

## 📊 Results & Insights

Results and evaluation metrics comparing U-Net and AER U-Net will be summarized here.  
_(to be completed)_

---

## 📚 References

- Jonnala, N. S., Siraaj, S., Prastuti, Y., Chinnababu, P., Praveen Babu, B., Bansal, S., Upadhyaya, P., Prakash, K., Faruque, M. R. I., & Al-Mugren, K. S. (2023).  
  **AER U-Net: Attention-Enhanced Multi-Scale Residual U-Net Structure for Water Body Segmentation**.  
  *Scientific Reports*. https://doi.org/10.1038/s41598-023-34266-9

- Ronneberger, O., Fischer, P., & Brox, T. (2015).  
  **U-Net: Convolutional Networks for Biomedical Image Segmentation**.  
  *MICCAI 2015*. https://arxiv.org/abs/1505.04597

- [Sentinel-2 Mission Overview – ESA](https://sentinel.esa.int/web/sentinel/missions/sentinel-2)

- Dataset used:  
  [Satellite Images of Water Bodies on Kaggle](https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies)

---
## 📬 Contact

For questions or collaboration opportunities, feel free to reach out:

- **Thomas Garnier** – [tgarnier067@gmail.com](mailto:tgarnier067@gmail.com)  
- **Jamil Nassar** – [jamilnassar1@gmail.com](mailto:jamilnassar1@gmail.com)

