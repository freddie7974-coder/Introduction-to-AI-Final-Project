# English-Swahili Agricultural Chatbot

A bilingual (English/Swahili) question-answering chatbot prototype for agricultural questions, such as when and how to plant coffee seedlings. The goal is to give farmers answers in the language they are most comfortable with.

Built as the final project for an Introduction to AI course.

## Features

- Works with a bilingual dataset: each entry has a topic, a question and a response in English, and the same in Swahili
- Separate text preprocessing for English and Swahili
- TF-IDF vectorization of questions, so a user's question can be matched to the closest stored question
- Language detection support (`langdetect`)

## Dataset

- `Chatbot_dataset.csv`: 448 question/response entries
- Columns: `Topic`, `Question_EN`, `Question_SW`, `Response_EN`, `Response_SW`
- Example topic: Planting Coffee Seedlings
- Several phrasings of the same question per topic (for example, "When is the best time to plant coffee?" and "When should I plant my coffee?"), which helps matching

<!-- Add the dataset source here (self-written, collected, or provided by the course). -->

## How It Works

1. **Load and standardize:** read the CSV, rename columns, and check for missing values
2. **Preprocess:** lowercase and remove punctuation, separately for English and Swahili questions
3. **Vectorize:** build a TF-IDF matrix for each language (English: 607 terms, Swahili: 846 terms)
4. **Match:** compare a user's question against the stored questions and return the response for the closest one

## Tech Stack

- **Language:** Python
- **NLP:** NLTK, scikit-learn (TF-IDF, cosine similarity), Hugging Face Transformers and Sentence-Transformers, langdetect
- **Data:** pandas
- **Environment:** Google Colab

## Getting Started

1. Open `Introduction_to_AI_Final_Project.ipynb` in Google Colab
2. Upload `Chatbot_dataset.csv` to your Google Drive and update the file path in the data loading cell
3. Run the cells in order

## Limitations

- The dataset is small (448 entries) and covers a limited set of topics
- Matching is based on word overlap (TF-IDF), so it can miss questions that mean the same thing but use different words
- Swahili preprocessing is basic: no Swahili lemmatizer is used

## Future Work

- Expand the dataset to more crops and farming topics
- Add semantic matching with sentence embeddings
- Add a proper Swahili lemmatizer
- Deploy as a web, WhatsApp, or SMS chatbot

## Author

Fredrick: [github.com/freddie7974-coder](https://github.com/freddie7974-coder)

<!-- Add LinkedIn link here. -->
