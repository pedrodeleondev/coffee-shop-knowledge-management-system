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

## Technologies Used

- **Python:** Main programming language.
- **Google Colab:** Development and execution environment.
- **Pandas:** Document organization and data manipulation.
- **Scikit-learn:** Machine learning, TF-IDF vectorization, and cosine similarity.
- **Multinomial Naive Bayes:** Automated document classification.

## Automated Document Classification

The classification component uses a dataset containing 50 sample documents distributed across five predefined categories.

The process consists of:

1. Loading and organizing the documents.
2. Converting document text into numerical representations using TF-IDF.
3. Dividing the dataset into training and testing sets.
4. Training a Multinomial Naive Bayes classifier.
5.
