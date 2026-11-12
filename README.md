# OIBSIP-DataAnalystics-L2-Task5-Autocomplete-and-Autocorrect-Data-Analytics-
# Autocomplete and Autocorrect Data Analytics

## Project Overview

This project explores autocomplete and autocorrect techniques using Natural Language Processing (NLP). It analyzes text from Project Gutenberg books to build word-prediction models and spelling-correction algorithms.

The autocomplete system uses bigram and trigram frequency models to predict the next word based on previously typed words. The autocorrect system compares PySpellChecker with a custom Levenshtein-distance algorithm to identify and correct spelling errors.

The project evaluates the algorithms using performance metrics and visualizations to understand their effectiveness, limitations, and potential applications in real-world typing systems.

## Objectives

- Collect and process a text corpus from Project Gutenberg.
- Perform NLP preprocessing, including lowercasing, tokenization, and punctuation removal.
- Analyze word frequencies and common word sequences.
- Implement bigram and trigram autocomplete models.
- Test autocomplete predictions on at least 10 input prefixes.
- Implement spelling correction using PySpellChecker.
- Develop a custom Levenshtein-distance spelling-correction algorithm.
- Evaluate correction performance using at least 20 deliberately misspelled words.
- Calculate accuracy, precision, recall, and F1-score.
- Compare different autocomplete and autocorrect approaches.
- Visualize the top 20 most frequent words and correction evaluation results.
- Discuss the limitations of simple NLP algorithms compared with production keyboard systems.

## Technologies Used

- **Python** — Programming language
- **Pandas** — Data processing and result analysis
- **NumPy** — Numerical calculations
- **NLTK** — Tokenization, n-grams, and frequency distributions
- **PySpellChecker** — Dictionary-based spelling correction
- **TextDistance** — Edit-distance utilities
- **Collections** — Word and n-gram frequency counting
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical charts
- **Scikit-learn** — Evaluation metrics and confusion matrices
- **Jupyter Notebook** — Interactive development environment

## Dataset

The project uses English-language text from Project Gutenberg.

**Dataset source:** https://www.gutenberg.org/

Multiple plain-text books are combined into a corpus to learn common words, bigrams, and trigrams. The training corpus is used to build the autocomplete models and custom vocabulary-based spelling corrector.

Before using or redistributing texts, check the copyright status and applicable terms for each book.

## Project Structure

```text
Autocomplete-Autocorrect-Analytics/
│
├── data/
│   └── books/
│       ├── book1.txt
│       ├── book2.txt
│       └── book3.txt
│
├── autocomplete_autocorrect.ipynb
├── requirements.txt
│
└── outputs/
    ├── autocomplete_prefix_tests.csv
    ├── autocomplete_metrics.csv
    ├── autocorrect_test_results.csv
    ├── autocorrect_metrics.csv
    ├── autocorrect_detection_results.csv
    ├── top_20_words.csv
    ├── top_20_words.png
    ├── autocomplete_model_comparison.png
    ├── autocorrect_model_comparison.png
    ├── autocorrect_confusion_matrices.png
    └── before_after_correction_matrix.png
```

## Installation

Install Python and Jupyter Notebook, then install the required packages:

```bash
pip install pandas numpy nltk pyspellchecker textdistance matplotlib seaborn scikit-learn
```

Alternatively, create a `requirements.txt` file containing:

```text
pandas
numpy
nltk
pyspellchecker
textdistance
matplotlib
seaborn
scikit-learn
```

Install the dependencies with:

```bash
pip install -r requirements.txt
```

## How to Run the Project

1. Download several English plain-text books from Project Gutenberg.
2. Place the `.txt` files in the `data/books/` directory.
3. Open a terminal in the project directory.
4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `autocomplete_autocorrect.ipynb`.
6. Run all cells in order, beginning with library imports and corpus loading.
7. Review the prediction tables, correction results, evaluation metrics, and generated charts.
8. Check the `outputs/` directory for saved CSV files and visualizations.

## Project Workflow

### 1. Data Collection

Download public-domain or otherwise appropriately licensed English texts and combine them into a corpus. Record which books were used and the size of the resulting corpus.

### 2. Text Preprocessing

- Convert text to lowercase.
- Tokenize text into individual words.
- Remove punctuation and non-alphabetic characters for the basic English-language experiment.
- Examine stopwords and word frequencies.

Stopword removal is useful for an additional content-word frequency analysis, but the main autocomplete corpus retains common words because they are essential for predicting natural language.

### 3. Autocomplete Implementation

Build frequency-based bigram and trigram models.

- **Bigram model:** predicts the next word using the previous word.
- **Trigram model:** predicts the next word using the previous two words.
- **Fallback mechanism:** uses the bigram model when an appropriate trigram context is unavailable.

Test at least 10 prefixes and display the top three predictions for each model.

### 4. Autocomplete Evaluation

Evaluate autocomplete using:

- **Top-1 Accuracy:** percentage of evaluated contexts where the first suggestion matches the actual next word.
- **Precision@3:** proportion of returned top-three suggestions that match the actual next word across evaluated contexts.
- **Recall@3:** percentage of evaluated contexts where the actual next word appears among the top three suggestions.

Record the number of evaluated contexts because models may have different prediction coverage.

### 5. Autocorrect Implementation

Compare two spelling-correction approaches:

- **PySpellChecker:** uses a dictionary-based vocabulary and ranks likely spelling corrections.
- **Custom Levenshtein Algorithm:** finds candidate words by edit distance and prefers frequent candidates among equally close matches.

Test at least 20 deliberately misspelled words against their intended spellings.

### 6. Autocorrect Evaluation

Calculate:

- Exact correction accuracy
- Correction precision
- Correction recall
- Correction F1-score

Also test correctly spelled control words to determine whether the algorithms make unnecessary changes.

Use confusion matrices to analyze spelling-error detection and before-and-after correctness transitions to evaluate correction outcomes.

### 7. Data Visualization

Generate visualizations showing:

- The 20 most frequent words.
- Autocomplete model performance.
- Autocorrect model performance.
- Confusion matrices for error detection.
- Spelling correctness before and after correction.

### 8. Algorithm Comparison

Compare the strengths and weaknesses of both approaches. Consider prediction accuracy, vocabulary coverage, handling of unseen word sequences, correction quality, and computational cost.

## Expected Results

The project produces:

- A cleaned and tokenized text corpus.
- Bigram and trigram autocomplete models.
- Top-three predictions for at least 10 input prefixes.
- Autocorrect results for at least 20 misspelled words.
- Accuracy, precision, recall, and F1-score summaries.
- Word-frequency and algorithm-comparison charts.
- Confusion matrices and before-and-after correction visualizations.
- A discussion of the limitations of simple NLP algorithms.

Actual performance values depend on the books selected, vocabulary coverage, test words, and model implementation.

## Limitations

- Frequency-based autocomplete models consider only short word sequences and do not fully understand sentence meaning.
- Trigram models may not predict well when a word sequence is rare or absent from the training corpus.
- A book-based vocabulary may not contain modern words, names, abbreviations, or technical terms.
- Edit-distance correction can replace a word with another valid but unintended word.
- A small set of deliberately misspelled words may not represent real-world typing mistakes.
- The implementation does not include neural language models, user personalization, multilingual prediction, or mobile-device optimization.

Production keyboard systems use more sophisticated language modeling, context, and engineering techniques.

## Applications

- Smartphone keyboard autocomplete.
- Spelling correction in text editors.
- Search-box query suggestions.
- Writing assistants and messaging applications.
- Text-entry systems and basic NLP research.
- Educational tools for spelling and vocabulary support.

## Conclusion

This project demonstrates how NLP and frequency-based language modeling can be used to build autocomplete and autocorrect systems. Bigram and trigram models provide next-word suggestions, while PySpellChecker and Levenshtein distance offer alternative approaches to spelling correction. Performance evaluation and visualization help identify the strengths and weaknesses of each method. The project provides a practical foundation for understanding text prediction and spelling correction while highlighting the need for richer contextual models in production systems.

## References

- Project Gutenberg: https://www.gutenberg.org/
- NLTK documentation: https://www.nltk.org/
- NLTK frequency distributions: https://www.nltk.org/api/nltk.probability.FreqDist.html
- NLTK n-gram utilities: https://www.nltk.org/api/nltk.util.html
- PySpellChecker documentation: https://pyspellchecker.readthedocs.io/en/latest/
- TextDistance repository: https://github.com/life4/textdistance
- Scikit-learn metrics: https://scikit-learn.org/stable/modules/model_evaluation.html
