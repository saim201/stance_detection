================================================================================
                                 STANCE DETECTION 
================================================================================

OVERVIEW
--------
Its a transformer-based stance detection system on twitter dataset.
The model classifies tweets into three stance categories toward controversial
topics: FAVOR, AGAINST, or NONE (neutral).

FINAL PERFORMANCE:
  • Test Accuracy: 66.37%
  • Macro-F1 Score: 0.6360

================================================================================
WHAT THIS PROJECT DOES
================================================================================

✓ Loads and aggregates tweets from 5 controversial topics
  (abortion, atheism, climate change, feminism, Hillary Clinton)

✓ Preprocesses tweets by removing noise
  (URLs, user mentions, hashtags, demojizes emojis, adds topic context etc)

✓ Fine-tunes BERTweet (Twitter-specific BERT) for stance classification
  Classifies into 3 categories: FAVOR, AGAINST, NONE (neutral)

✓ Addresses class imbalance using weighted cross-entropy loss

✓ Performs error analysis to identify failure patterns
  (negation, sarcasm, rhetorical questions)

================================================================================
QUICK START
================================================================================

1. INSTALL DEPENDENCIES
   $ pip install -r requirements.txt

2. PREPARE DATA STRUCTURE
   Stack detection/
   ├── abortion/
   │   ├── train_text.txt, train_labels.txt
   │   ├── val_text.txt, val_labels.txt
   │   ├── test_text.txt, test_labels.txt
   ├── atheism/
   ├── climate/
   ├── feminist/
   ├── hillary/
   └── mapping.txt  (label encoding: 0=none, 1=against, 2=favor)

3. RUN THE NOTEBOOK
   $ jupyter notebook main.ipynb

4. TRAINING PIPELINE (automated in notebook)
   - Load and preprocess all data
   - Perform exploratory data analysis (EDA)
   - Fine-tune BERTweet on aggregated dataset
   - Evaluate on test set and generate confusion matrix
   - Analyze error patterns

================================================================================
