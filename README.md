# Contradictory, My Dear Watson - Natural Language Inferencing Project Overview
- Implemented BERT multilingual model to classify sentence pair relationships as 'entailed', 'contradictory' or 'neutral' across several languages with ~64% accuracy.
- This project is currently in progress, looking to compare and optimize several NLP models in order to improve accuracy and deepen understanding of NLP and Tensorflow.
- BERT implementation adapted from tutorial notebook by Ana Uzsoy: https://www.kaggle.com/code/anasofiauzsoy/tutorial-notebook/notebook
- Project versions will be periodically uploaded to relevant Kaggle competition: https://www.kaggle.com/competitions/contradictory-my-dear-watson/overview

## Code and Resources Used
**Python Version:** 3.7

**Packages:** pandas, numpy, matplotlib, transformers (BertTokenizer and TFBertModel), tensorflow'

**Dataset Documentation:** https://www.kaggle.com/competitions/contradictory-my-dear-watson/data

## Data Exploration
The training data contains several thousand sentence pairs across multiple languages. The pairs each have a unique identifier, language labels, and a label indicating human classification of the pair-relationship: 0 = 'entailment', 1 = 'neutral', 2 = 'contradiction'. 

![image](https://user-images.githubusercontent.com/97380323/177219591-34394858-6391-4820-87f8-a228edd18e47.png)

## Data Preparation - Tokenization
As a starting point for the project, I used the pre-trained BERT multilingual classifier. In order to perform multilingual classification, I had to pass the data through a tokenizer that transforms words into number arrays. BERT takes in input word IDs, input masks, and input type IDs. I added CLS tokens to signify the beginning of inputs and SEP tokens to designate separation between premises and hypotheses. I padded inputs so that they were the same size.

## BERT Model Building and Training
I incorporated the BERT transformer into a Keras Functional Model, which allows more flexibility.

## BERT Model Performance
With 20% validation, the model performed with 65% accuracy on validation data. After generating predictions on the test set, I submitted my predictions to Kaggle and received an accuracy score of 64.85%. This is a good start, but there is a lot of room to grow!

## Future Plans
The top-scoring models on Kaggle achieve 98%+ accuracy. This BERT implementation served as a good introduction to Tensorflow and NLP for me, but I plan to continue implementing other models and comparing performance to get the highest score I can.
