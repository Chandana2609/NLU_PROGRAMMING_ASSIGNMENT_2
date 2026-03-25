 Problem 1 :Learning Word Embeddings from IIT Jodhpur Data

 Overview
This project implements Word2Vec models (CBOW and Skip-gram) on textual data collected from IIT Jodhpur sources. The goal is to learn meaningful word embeddings and analyze semantic relationships between words.



Dataset

The dataset consists of textual data collected from:
- Academic regulation documents (mandatory)
- Department webpages
- Course syllabus and academic content

Only English language  text was considered.

Dataset Link
https://drive.google.com/file/d/1USFuJ4TbjH9qCGkm77ocgHDiKhOXmini/view?usp=sharing


Preprocessing Steps

1. Removed HTML tags and formatting artifacts  
2. Removed numerical values  
3. Removed punctuation  
4. Converted text to lowercase  
5. Removed extra whitespace  
6. Tokenized text into words  
7. Combined all data into a single corpus  



Models Implemented

1. CBOW (from scratch)
- Predicts target word from context
- Embedding size: 100
- Optimizer: SGD

2. Skip-gram with Negative Sampling (from scratch)
- Predicts context words from target
- Embedding size: 100
- Negative sampling used

3. Gensim Word2Vec
- CBOW (sg=0)
- Skip-gram (sg=1)
- Used for comparison

---
 Results & Analysis

- Computed cosine similarity between words
- Extracted nearest neighbors for:
  - research
  - student
  - phd
  - exam
- Performed analogy tasks between different words 



Visualization

- PCA used to project embeddings into 2D space
- Observed partial clustering of semantically related words



How to Run

1. Run preprocessing script to generate corpus  
2. Train CBOW and Skip-gram models  
3. Run similarity and analogy evaluation  
4. Run visualization code  



Requirements

- Python 3.x  
- PyTorch  
- Gensim  
- NumPy  
- Matplotlib  

Problem 2: Character-Level Name Generation using RNN Variants

Overview

This project implements and compares different recurrent neural network architectures for generating Indian names at the character level.

The models implemented are:
- Vanilla RNN
- Bidirectional LSTM (BLSTM)
- RNN with Attention Mechanism

---

 Dataset

- A dataset of **1000 Indian names** was generated using a language model.
- Stored in: `TrainingNames.txt`

Format:
Each line contains one name.



 Data Processing

- Converted all names to lowercase
- Added special tokens:
  - `<SOS>` (Start of Sequence)
  - `<EOS>` (End of Sequence)
- Built character-level vocabulary
- Encoded names as sequences of indices



  Models Implemented

 1. Vanilla RNN
- Architecture: Embedding → RNN → Linear
- Learns sequential character dependencies



 2. BLSTM (Bidirectional LSTM)
 Architecture: Embedding → BiLSTM → Linear
 Captures both forward and backward context


3. Attention Model
- Architecture: Embedding → LSTM → Attention → Linear
- Focuses on important parts of sequence during prediction


##  Hyperparameters


Embedding Size
Hidden Size 
Learning Rate 
Batch Size 
 Epochs 



 Training Details

- Loss Function: CrossEntropyLoss
- Optimizer: Adam
- Sequence modeling using prefix prediction



 Name Generation

- Starts with `<SOS>`
- Generates characters one-by-one
- Stops at `<EOS>` or max length
- Uses probabilistic sampling



 Evaluation Metrics

Two metrics were used:
 1. Novelty
- Measures how many generated names are new

 2. Diversity
- Measures uniqueness of generated names




  Observations

- RNN generates more random names
- BLSTM improves structure and coherence
- Attention produces the most realistic names



 Failure Modes

- Repetition of characters (e.g., "aaaa", "juju")
- Unnatural or incomplete names
- Random character sequences



Files Included

- `TrainingNames.txt` → https://drive.google.com/file/d/1GzQAYCoa-2O-C-wkadKgFaJtaoVlBy0y/view?usp=sharing
- Model implementation code
- Evaluation script (`evaluation.csv`)
- Generated samples

 How to Run

1. Train models (RNN, BLSTM, Attention)
2. Generate names
3. Run problem2.py
4. Analyze generated names


 Requirements

- Python 3.x
- PyTorch
- NumPy
- pandas
- matplotlib



Notes

- Character-level modeling allows generation of new names
- Attention improves sequence understanding
- Evaluation includes both quantitative and qualitative analysis

