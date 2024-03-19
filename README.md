<p align="center"><img width=100% src="https://github.com/sridhar-gd/sridhar-gd/blob/main/Banner.png"></p>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![Python](https://img.shields.io/badge/python-v3.11+-blue.svg)
![Dependencies](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)


# MEDIUM APP REVIEWS SENTIMENT ANALYSIS

The objective of sentiment analysis on Medium app reviews is to determine the overall sentiment or emotion expressed in the reviews. This can help businesses understand how their customers feel about their product, identify areas for improvement, and track their brand health. Sentiment analysis tools can process text and audio data, identifying positive, negative, and neutral sentiments. They can also handle complex expressions and negations, and be unbiased in their analysis.

For example, in the context of Medium app reviews, sentiment analysis can help identify common themes or issues in customer feedback, such as difficulty navigating the app or issues with the user interface. By analyzing the sentiment of these comments, businesses can prioritize which issues to address first and measure the impact of any changes they make.

Additionally, sentiment analysis can help businesses monitor their brand reputation on social media, automatically tracking mentions of their company and identifying the overall sentiment expressed in these posts. This can help businesses stay on top of customer feedback and respond quickly to any negative sentiment.


## Table of Contents

1. Data Description
2. Data Preprocessing
3. Model Architecture
4. Model Training
5. Model Evaluation
6. Deployment
7. License


## Data Description

The dataset consists of 53,321 reviews and the target variable indicating whether the news is positive, negative or neutral.
- reviewId: Review ID for the review
- content: Review text
- score: Given score to the application
- thumbsUpCount: People can upvote the other reviews, the total upvotes for the review
- reviewCreatedVersion: The application version when the review sent
- at: Review date
- replyContent: Reply text to the review (if any)
- repliedAt: Reply date (if any)
- predicted_category: Predicted category using fine-tuned model
- sentiment: Predicted sentiment using a NLP model
- appVersion


## Data Preprocessing

- Removing irrelevant columns like replyContent, repliedAt, appVersion, at, thumbsUpCount, reviewCreatedVersion.
- Converting uppercase letters to lowercase letters.
- Removing punctuation marks, digits, and extra spaces.
- Tokenization to break down a stream of text into individual words, phrases, symbols, or other meaningful elements called tokens.
- Identifying and removing stop words


## Model Architecture

The model architecture is a simple deep learning model for text classification using Keras. It consists of three layers: an embedding layer, a long short-term memory (LSTM) layer, and a dense layer.
- Embedding Layer: The first layer is an embedding layer, which converts the input text data into a dense vector representation. The input to this layer is a sequence of integers, where each integer represents a word in the vocabulary. The embedding layer has three parameters:
-- max_words: The maximum number of unique words in the vocabulary.
-- 64: The dimensionality of the embedding space.
-- input_length: The length of the input sequence.
- LSTM Layer: The second layer is a long short-term memory (LSTM) layer, which is a type of recurrent neural network (RNN) designed to handle sequential data. The LSTM layer has one parameter:
-- 64: The number of units in the LSTM layer.
- Dense Layer: The third layer is a dense layer, which is a fully connected neural network layer. The dense layer has two parameters:
-- 3: The number of output classes.
-- activation='softmax': The activation function used in the dense layer.


## Model Training
X represented the independent variables (i.e., the reviews) and y represented the target/dependent variable (i.e., the sentiment involved)
The model was trained using the training dataset with the following specifications:

- Loss function: Categorical Cross Entropy
- Optimizer: Adam
- Epochs: 50
- Batch size: 128


## Model Evaluation

The accuracy of the model was evaluated the accuracy achieved was 98%.


## Deployment

Taking the model from development to deployment, Flask - a powerful web framework for Python - was utilized.


## License

MIT License

Copyright (c) 2024 Sridhar GD

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
