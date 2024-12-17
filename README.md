# Image Captioning with Breed-Specific Details

## Overview
This project focuses on **domain-specific image captioning** by incorporating **dog breed information** into generated captions. 

## Solution Approach
1. **Dataset Combination**: Combined the **Stanford Dogs Dataset** (for dog breeds) with the **Flickr8K Dataset** (for general captions).
2. **CNN-RNN Integration**:
   - **Inception V3** (fine-tuned) for dog breed classification.
   - Another **Inception V3** as a feature extractor for general image features.
   - **LSTM** for caption generation, integrating breed-specific and general features.
3. **Evaluation**: Performance tested using BLEU scores and accuracy metrics on subsets of images with and without dogs.

## Install Dependencies
```bash
pip install -r requirements.txt

```
## Dataset Setup
Download the Flickr8K Dataset and Stanford Dogs Dataset:

- Use kagglehub as in image_captioning_with_breed.ipynb
- or download manually from:
   - Flickr8K: https://www.kaggle.com/datasets/shadabhussain/flickr8k
   - Stanford Dogs: https://www.kaggle.com/datasets/jessicali9530/stanford-dogs-dataset

## Run the project
```bash
python image_captioning_with_breed.ipynb
```

## Example Results

With Dog (Breed-Specific Caption):

<img width="369" alt="Screenshot 2024-12-17 at 12 32 20 AM" src="https://github.com/user-attachments/assets/bea168c2-3d09-4343-89a8-958c402d31a1" />

Without Dog (General Caption):

<img width="497" alt="Screenshot 2024-12-17 at 12 32 50 AM" src="https://github.com/user-attachments/assets/a17d45cc-ca4f-4e98-ad4b-c740478dbb1e" />

## Evaluation Metrics

The performance of our model was evaluated using the following metrics:

| Dataset Subset       | Loss   | Accuracy  | BLEU Score |
|:-----------------------|:--------|:-----------|:------------|
| **With Dog Images**   | 0.2168 | 67.07%    | 0.2950     |
| **Without Dog Images**| 0.9909 | 35.14%    | 0.0789     |

Accuracy: Measures the correctness of breed classification and token prediction.

BLEU Score: Evaluates caption quality by comparing generated captions with ground-truth captions.

## Future Work

- Use beam search for more accurate caption decoding.
- Incorporate larger and more balanced datasets to generalize across different image types (OR generate pseudo label)

## Acknowledgments

- **[Flickr8K Dataset](https://www.kaggle.com/datasets/shadabhussain/flickr8k)** for captions and general images.
- **[Stanford Dogs Dataset](http://vision.stanford.edu/aditya86/ImageNetDogs/)** for fine-grained breed classification.
- Pre-trained models from **[PyTorch](https://pytorch.org/)** and **[TensorFlow](https://www.tensorflow.org/)**.
