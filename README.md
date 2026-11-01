# Coffee Shop Knowledge Management System

## Project Overview

This project was developed for the *Knowledge Management Systems and Technologies* course. Its objective is to design and implement a basic knowledge management system prototype for a fictional specialty coffee shop.

The system uses machine learning techniques to automatically classify organizational documents and retrieve relevant information through natural language queries.

The prototype aims to improve how employees organize, access, and share knowledge during daily operations.

## Company Description

The fictional organization is a medium-sized specialty coffee shop with approximately 18 employees working across two shifts.

Its main activities include preparing coffee and meals, serving customers, managing inventory, following food safety regulations, and handling customer complaints.

The organization manages five main categories of documents:

- Recipes
- Service manuals and protocols
- Hygiene and food safety policies
- Inventory and suppliers
- Customer service

## Project Objectives

The main objectives of this project are:

1. Define the organizational context and identify its knowledge resources.
2. Represent the organizational knowledge life cycle.
3. Develop a basic ontology showing relationships between knowledge elements.
4. Implement automated document classification using machine learning.
5. Develop a basic semantic search component using TF-IDF and cosine similarity.

The knowledge life cycle map and the ontology are presented in the project progress report that accompanies this repository.

## Technologies Used

- **Python:** Main programming language.
- **Google Colab:** Development and execution environment.
- **Pandas:** Document organization and data manipulation.
- **Scikit-learn:** Machine learning, TF-IDF vectorization, and cosine similarity.
- **Multinomial Naive Bayes:** Automated document classification.

## Repository Contents

| File | Description |
|---|---|
| `kms_prototype.ipynb` | Jupyter Notebook with the classification and semantic search components. It also contains the 50 sample documents used for training and testing, defined in the `documents` and `new_documents` lists. |
| `README.md` | Project description and instructions to run the notebook. |

## Dataset

The dataset consists of 50 short sample documents related to the daily operations of the coffee shop. It was created in two stages: 25 initial documents and 25 additional documents to add more vocabulary variety.

Each document has one predefined category, with 10 documents per category:

| Category | Documents |
|---|---|
| Recipes | 10 |
| Service manuals and protocols | 10 |
| Hygiene and food safety policies | 10 |
| Inventory and suppliers | 10 |
| Customer service | 10 |
| **Total** | **50** |

The documents are defined inside the notebook, so no additional data files are needed.

## Automated Document Classification

The classification component supports the organization and classification stage of the knowledge life cycle.

The process consists of:

1. Loading and organizing the documents in a Pandas DataFrame.
2. Dividing the dataset into 80% for training (40 documents) and 20% for testing (10 documents), using stratified sampling and `random_state=42`.
3. Converting the document text into numerical representations using TF-IDF (217 features learned from the training documents).
4. Training a Multinomial Naive Bayes classifier.
5. Predicting categories for the testing documents, evaluating the results with accuracy and a classification report, and classifying a new document that was not part of the dataset.

## Basic Semantic Search

The semantic search component supports the knowledge-sharing stage of the life cycle. It retrieves the documents most related to a natural language query in four steps:

1. Receiving a natural language query.
2. Converting the query and the 50 documents into vectors using TF-IDF (248 features).
3. Calculating the cosine similarity between the query and each document.
4. Displaying the five most relevant documents with their category and similarity score.

## How to Run

1. Download `kms_prototype.ipynb` from this repository.
2. Open [Google Colab](https://colab.research.google.com), select **File > Upload notebook**, and choose the file.
3. Select **Runtime > Run all**.

The notebook contains the 50 documents, so no additional files are needed. The `sample_data` folder that Colab shows is created by Colab by default and is not part of this project.

## Results

| Component | Result |
|---|---|
| Classification | 9 of 10 testing documents classified correctly (accuracy: 0.90) |
| New document test | "The coffee supplier must deliver fresh coffee beans every Monday." was classified as *Inventory and suppliers* |
| Search: "How to prepare a vanilla latte?" | Top result: the vanilla latte recipe (similarity 0.7366) |
| Search: "How should employees handle customer complaints?" | Top result: the customer complaints policy (similarity 0.4347) |

The only classification error was a document about uniforms and protective equipment, predicted as a service manual instead of a hygiene policy. These two categories share vocabulary, and several words of that document did not appear in the training set.

## Limitations

- The dataset is small and made of short sentences.
- The testing set has only 10 documents, so one error changes the accuracy by 10 points. The results are a first indication of performance, not a final measurement.
- TF-IDF compares words without understanding their meaning, so the search can rank general documents above relevant ones when the vocabulary does not match.

## Future Work

- Use more real documents from the coffee shop.
- Expand search queries with related terms from the ontology.

## Authors

- Frida Sarahi Garza Gálvez
- Paola Guadalupe Urdiales Luna
- Pedro Francisco De León Salazar

Universidad Tecmilenio — *Knowledge Management Systems and Technologies*
Professor: Jesús Clemente Chío Rodríguez
