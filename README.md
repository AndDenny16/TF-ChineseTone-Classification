# **Tone Buddy**  
## **Step 1: Deep Convolutional NN for Tone Classification**

---

<img src="https://github.com/AndDenny16/Tone-Identifier-Container/blob/main/logolfinal2.png" alt="Project Logo" width="150">

## **Motivation**
As a Computer Science major with a minor in Chinese Studies, I wanted to combine these two fields into a meaningful project. Mandarin Chinese, a tonal language, has **4 tones**, and the meaning of each word depends on using the correct tone.

For example:  
- **媽 (mā)**: 1st tone = *mother*  
- **罵 (mà)**: 4th tone = *scold*  

Messing up a tone can completely change the meaning of a sentence. This is a common challenge for learners of Mandarin. To address this, I created **Tone Buddy**, an app designed to help learners practice their tones using machine learning (ML).

---

## **Project Breakdown**
This repository is **Step 1** of the overall project. Below is an overview of the full project workflow:

### **Step 1: Tone Classification Model (This Repo)**
- Trained a **Deep Convolutional Neural Network (CNN)** on spectrograms of native Mandarin speakers using:
  - **TensorFlow**
  - **Librosa** (for audio preprocessing)
  - **Python**
- The model predicts the tone of a given word based on its audio spectrogram.

### **Step 2: [Dockerized ML Model](https://github.com/AndDenny16/Tone-Identifier-Container)**
- Deployed the pretrained ML model in a custom **Docker container**.
- The container performs the following:
  1. Accepts user audio input.
  2. Converts the audio into a spectrogram.
  3. Feeds the spectrogram into the ML model.
  4. Returns the predicted tone.

### **Step 3: Serverless Backend**
- Built a scalable backend using:
  - **AWS API Gateway** and **AWS Lambda** for serverless functions.
  - **Amazon S3** for storing user data and spectrogram files.
  - **AWS Fargate** for hosting the Docker container.

### **[Step 4: Frontend](https://github.com/AndDenny16/ToneBuddy)** 
- Developed a **React Native frontend** to provide an intuitive and engaging user experience for learners.

---
# Tone Classification Model 

## Overview
This Repo develops a **TensorFlow model** to recognize **Chinese tones** from spoken audio. The model processes **spectrograms** of audio recordings and applies **deep learning techniques** for classification

## Dataset
- Primary dataset: [TonePerfect](https://tone.lib.msu.edu/)
- Additional data: [Forvo] (https://forvo.com/)

## Project Workflow
1. **Data Preparation**
   - Utilized Librosa to create Mel Spectrograms and convert into dbs
   - Leveraged MatplotLib + Librosa Specshow to create spectrogram images
   - Save Images Into Tone Categories
   - Format data into a TensorFlow Dataset

2. **Enhancing the Dataset**
   - Fetch real-world audio examples from the **Forvo API** for better generalization
   - Merge datasets

3. **Model Training**
   - Architecture Inspiration: (https://www.isca-archive.org/interspeech_2019/gao19c_interspeech.pdf)
   - Design and train a deep learning model using **TensorFlow & Keras**
   - Utilizing Convolution Layers
   - Dropout
   - Early Stopping
   - TF Checkpoints
  
4. **Results**

   - 93% on Training Data
   - 98% Accuracy on Validation/Test Data
   - More In Depth Discussion Inside Notebook

6. **Results Visualization**
   - Scklearn Learn Confusion Metric
   - Discussion of Recall/Precision/Accuracy and False Negatives/False Positives
  
## Dependencies
- `TensorFlow`
- `Librosa`
- `Matplotlib`
- `NumPy`
- `Forvo API` (for additional data)
- `Sklearn`


