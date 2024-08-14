# YELP-POLARITY-LLM
**Introduction**

Sentiment analysis provides insightful information about the beliefs and experiences of the audience by using Large Language Models (LLMs) to extract the text's emotional content. DistilBERT, a condensed and effective version of BERT, is used in this project to classify Yelp reviews' sentiment. The objective is to create a dependable model that can reliably identify positive and negative sentiments in Yelp reviews. A smaller sample of the Yelp Polarity dataset was used for fine-tuning due to limitations like high memory consumption and frequent RAM crashes.

**METHODOLOGY**

Pandas format was used to load the Yelp Polarity dataset, which was obtained from the Hugging Face dataset repository. This dataset, which includes many Yelp reviews labeled by sentiment polarity, is intended for binary sentiment classification. Because of the

Subsets of the dataset were set aside for testing and training. Tokenization was performed using the DistilBERT autotokenizer, which converted unprocessed text into numerical representations that the model could understand. The sequences had a maximum length of 128 tokens before being padded and truncated. TensorFlow tensors were generated from labels, and training and testing TensorFlow datasets were established.


