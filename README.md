# Pharma_TextVision_Assistant
# Multimodal Pharmaceutical AI Assistant
**Vision + Text RAG system for pharmaceutical question answering**

## Project Overview

This project implements a **multimodal AI assistant capable of answering pharmaceutical questions using both text and images**.

The system combines:

- Vision-language modeling
- Retrieval-Augmented Generation (RAG)
- Multimodal training datasets
- Vector search with FAISS

The assistant can:

- Identify a medication from an image
- Retrieve relevant pharmacological information
- Generate accurate answers grounded in medical data

The system was developed as a **complete end-to-end AI pipeline**, including:

1. Exploratory Data Analysis
2. Data preprocessing and vector database creation
3. Image dataset processing
4. Synthetic dataset generation (RAFT)
5. Multimodal dataset construction
6. Model inference pipeline
7. Evaluation framework

---

# Project Architecture

The system integrates **three main AI components**:

### 1. Vision Model
A fine-tuned **vision-language model** trained to identify medications from packaging images.

### 2. Retrieval System (RAG)
A **FAISS vector database** built from a pharmacological dataset to retrieve relevant context.

### 3. Language Generation
A language model generates answers using the retrieved information.


---

# Repository Structure

├── PRESENTACION -> con la presentación del proyecto en formato ppt y PDF, jutno al video que aprece ene l ppt


├── 00_eda.py


├── 01_dataprocessing.py


├── 02_image.py


├── 02_raft_multimod.py


├── 03_multimod.py


├── 04_inference_vt.py


├── 05_evaluation.py


└── README.md


#### 00_eda.py
Exploratory data analysis of the pharmaceutical dataset, inspecting missing values, text distributions and dataset quality.

#### 01_dataprocessing.py
Cleans and processes the dataset and builds the **FAISS vector database** used for semantic retrieval.

#### 02_image.py
Processes the pharmaceutical image dataset and standardizes images for vision model training.

#### 02_raft_multimod.py
Implements **RAFT synthetic dataset generation**, creating question-answer pairs grounded in retrieved pharmaceutical context.

#### 03_multimod.py
Builds the **final multimodal training dataset** by combining text and visual supervision.

#### 04_inference_vt.py
Implements the **complete multimodal inference pipeline**, including image recognition and RAG-based answer generation.

#### 05_evaluation.py
Runs the **evaluation pipeline** using automatically generated questions and LLM-based grading.


---

# Results Analysis and Conclusions

The developed system demonstrates that combining **vision models with retrieval-augmented language models** significantly improves the ability of AI systems to answer pharmaceutical questions accurately.

The multimodal architecture allows the assistant to **identify medications from images and retrieve relevant pharmacological information**, enabling contextualized and grounded responses. The use of RAFT to generate synthetic training data also proved useful for expanding the dataset and improving the robustness of the multimodal model.

However, several limitations remain. The performance of the system depends on the **quality of the retrieved context**, meaning that incomplete or noisy entries in the pharmaceutical dataset can affect the generated answers. Additionally, the vision model may struggle with images that contain poor lighting conditions, unusual packaging formats, or partial visibility of the medication name.

Despite these limitations, the results demonstrate the feasibility of building **domain-specific multimodal assistants for healthcare applications**, particularly when combining structured knowledge bases with modern large language models.


---

# Future Improvements

Several improvements could further enhance the system:

• **Improved vision model fine-tuning** using a larger dataset of pharmaceutical packaging images.

• **Higher quality medical datasets**, potentially including regulatory drug databases or clinical pharmacology resources. Likewise, include a medical history.

• **Deployment of a user interface**, enabling pharmacists or healthcare professionals to interact with the assistant. With an application, it would also be possible to include a voice assistant.


---

# Technology Stack

### Machine Learning
- PyTorch
- Transformers
- Unsloth

### Retrieval
- FAISS
- Sentence Transformers

### Language Models
- Llama 3
- Groq API

### Data Processing
- Pandas
- NumPy

### Vision Processing
OCR
- PIL
- Torchvision


---

# Datasets

The project uses two main datasets.

### 1. Pharmaceutical Text Dataset (MID Dataset)

A structured pharmaceutical dataset containing drug information such as:

- drug name
- medical uses
- side effects
- pharmacological information

This dataset is used to build the **knowledge base for the RAG system**.

Missing values were handled during preprocessing and replaced with: "no information available"

to ensure consistent document construction for embedding generation.

link: https://data.mendeley.com/datasets/2vk5khfn6v/3
---

### 2. Pharmaceutical Image Dataset

A dataset of **medication packaging images** used to train and test the vision component of the assistant.

Images were preprocessed by:

- converting to RGB
- applying dynamic padding
- resizing to a standardized resolution
- exporting processed images for training

The final processed image size used in the pipeline is: 470x470

link: https://data.mendeley.com/datasets/sdfcbmjfnd/2

---

# Prerequisites

Before running the project, ensure the following dependencies are installed.

### Python

Python >= 3.10


### Required libraries

- torch
- transformers
- faiss-cpu
- sentence-transformers
- pandas
- numpy
- matplotlib
- unsloth


### API Keys

The project requires access to a language model API for RAFT dataset generation and evaluation.

- Groq


---

# Author

Final project developed by 'Les alucines' as part of an **AI Engineering / LLM Bootcamp**, focusing on building real-world multimodal AI systems combining vision, retrieval, and large language models.
