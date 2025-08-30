ATS Model for AI Sem 5 Project
This project contains two distinct models for building an Applicant Tracking System (ATS), both of which are based on a BERT model for processing text. The models are designed to match resumes to specific job categories.

Model Architecture
1. XGBoost Classification Model (ATS_Model.ipynb)
This model is a classifier that predicts a job category for a given resume based on its skills.

Embedding Generation: It uses the SentenceTransformer model "all-MiniLM-L6-v2" to convert a resume's skills into numerical vectors, also known as embeddings.

Training: An XGBoost classifier is trained on these embeddings to predict the job category. The model parameters are configured for multi-class classification and are set to use GPU acceleration.

Output: The model outputs a probability distribution over the different job categories, indicating the likelihood of a resume belonging to each one.

2. Sentence Similarity Matching Model (match_model.ipynb)
This model matches a resume to job categories by calculating the similarity between their embeddings.

Data Aggregation: The model first merges multiple resume datasets.

Centroid Calculation: It then uses the "all-MiniLM-L6-v2" SentenceTransformer model to create embeddings for all resumes and calculates the centroid (average vector) for each job category.

Similarity Scoring: To score a new resume, the model computes the cosine similarity between the resume's embedding and the centroid of each job category. This score is then normalized to a value between 0 and 1.

Output: The model provides a list of job categories ranked by their similarity score, with the highest score indicating the best match.

Checkout the implementation here - https://github.com/ishandeep48/ATS_Checker
