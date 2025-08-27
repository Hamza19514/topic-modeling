# topic-modeling

This project applies **topic modeling (LDA)** and **word cloud visualization** to a dataset of tweets.  
It identifies dominant topics in the text and assigns human-readable labels (e.g., *Energy & Oil Markets*).

## Preprocessing

Before applying topic modeling, we clean and standardize the raw tweets.  
This step is essential because raw text often contains noise (symbols, stopwords, links, etc.) that can distort results.  

### Steps performed
1. **Lowercasing**  
   - Convert all text to lowercase.  
   - Ensures `Oil` and `oil` are treated as the same token.  

2. **Tokenization**  
   - Split each tweet into individual words.  
   - Needed so the model works with word units instead of whole sentences.  

3. **Removing punctuation, numbers, and special characters**  
   - Gets rid of characters that don’t contribute to meaning in topic modeling.  

4. **Stopword removal**  
   - Remove very common words (e.g., *the, and, is, on*).  
   - Prevents them from dominating topics.  

5. **Lemmatization NLP**  
   - Reduce words to their base form (e.g., *running → run*).  
   - Groups similar words together, strengthening topic coherence.  

6. **Vectorization**  
   - Convert cleaned text into a numerical format using CountVectorizer or TfidfVectorizer.  
   - This creates the input matrix for LDA models.
   - 
### Why preprocessing is important
- **Reduces dimensionality**: Fewer unique words after cleaning → faster training.  
- **Standardizes input**: Makes sure similar words are treated consistently.

## Train the Model
We use **Latent Dirichlet Allocation (LDA)** to discover latent topics from the tweets.  

### Steps
1. Fit the model on the vectorized text.  
2. Extract word distributions for each topic.  
3. Identify **dominant topic per tweet** by selecting the topic with the highest probability.  


## Results
- Generated **topic–word lists** showing top terms for each topic.  
- Assigned a **dominant_topic** label for each tweet (e.g., *Energy & Oil Markets*).  
- Created **word clouds** to visualize frequent words.  

Example topics from 3-topic LDA:  
- Topic 0 → *Energy & Oil Markets*  
- Topic 1 → *Crude Oil Prices*  
- Topic 2 → *OPEC and Petroleum Industry*  

## Save Outputs
-`tweets__topics.csv` 
