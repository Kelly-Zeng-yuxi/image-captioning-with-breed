# Image Captioning with Breed-Specific Details

## Overview
This project focuses on **domain-specific image captioning** by incorporating **dog breed information** into generated captions. 

## Install Dependencies
```bash
pip install -r requirements.txt

## Run the project
```bash
python image_captioning_with_breed.ipynb

## Solution Approach
1. **Dataset Combination**: Combined the **Stanford Dogs Dataset** (for dog breeds) with the **Flickr8K Dataset** (for general captions).
2. **CNN-RNN Integration**:
   - **Inception V3** (fine-tuned) for dog breed classification.
   - Another **Inception V3** as a feature extractor for general image features.
   - **LSTM** for caption generation, integrating breed-specific and general features.
3. **Evaluation**: Performance tested using BLEU scores and accuracy metrics on subsets of images with and without dogs.
