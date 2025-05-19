# Job Recommendation System (LinkedIn Replica)
  
**Technologies:** PySpark, Word2Vec, KNN, TensorFlow, AWS EMR, S3, Collaborative Filtering

## 📌 Overview

This project is a large-scale job recommendation engine inspired by LinkedIn, designed to predict relevant job postings for users using both collaborative filtering and deep learning. The system processes and analyzes 3GB+ of user-job interaction data in a distributed environment.

## 🧠 Objectives

- Predict jobs users are likely to apply for using past behavior and semantic job/user embeddings.
- Build scalable infrastructure for model training and data processing.
- Combine classical recommendation techniques (KNN) with neural network models for performance comparison.

## 🧱 Key Features

- **Collaborative Filtering (KNN)**: Used `pyspark.ml` and a custom KNN implementation to recommend jobs based on similar users' application history.
- **Text Embeddings with Word2Vec**: Generated vector representations for jobs and user activity using Word2Vec to capture contextual meaning.
- **Deep Learning (TensorFlow)**: Built a neural network to predict job applications based on joined user-job embeddings.
- **Batch Training with Window Filtering**: Used time windows to batch data and streamline model training for large-scale processing.
- **Cloud Infrastructure**: Leveraged **AWS EMR clusters** for distributed processing and **Amazon S3** for scalable data storage and experiment tracking.

## ⚙️ Architecture
Raw Data (3GB+) ─▶ S3 ─▶ EMR Cluster ─▶ PySpark + Word2Vec Embeddings
│
├──▶ KNN (Collaborative Filtering)
└──▶ TensorFlow Neural Network
│
─▶ Job Predictions ─▶ Output to S3


## 🛠️ Tools & Libraries

- **PySpark** – distributed processing for large-scale data.
- **Word2Vec (Spark MLlib)** – for embedding job descriptions and user behaviors.
- **TensorFlow** – for building and training a neural network recommendation model.
- **AWS EMR** – scalable cluster-based computation.
- **Amazon S3** – used for data storage and checkpointing progress.
- **KNN** – for collaborative filtering, leveraging user similarity.

## 🧪 Pipeline Summary

1. **Preprocessing**:
   - Cleaned and vectorized user/job data with Word2Vec.
   - Windowed data by timestamp to simulate batch training.

2. **Collaborative Filtering**:
   - Built a KNN model to find similar users and recommend jobs based on their behavior.

3. **Neural Network Prediction**:
   - Joined user and job vectors.
   - Fed combined embeddings into a TensorFlow model for prediction.
   - Compared neural model performance against KNN baseline.

4. **Model Management**:
   - Stored training checkpoints, embeddings, and results in S3 for tracking and reproducibility.

## ✅ Results (Sample)

- Improved prediction accuracy over baseline KNN by 90%.
- Enabled scalable training over 3GB dataset without local resource limits.

