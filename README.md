# YELP-POLARITY-LLM
**INTRODUCTION**

Sentiment analysis provides insightful information about the beliefs and experiences of the audience by using Large Language Models (LLMs) to extract the text's emotional content. DistilBERT, a condensed and effective version of BERT, is used in this project to classify Yelp reviews' sentiment. The objective is to create a dependable model that can reliably identify positive and negative sentiments in Yelp reviews. A smaller sample of the Yelp Polarity dataset was used for fine-tuning due to limitations like high memory consumption and frequent RAM crashes.

**METHODOLOGY**

Pandas format was used to load the Yelp Polarity dataset, which was obtained from the Hugging Face dataset repository. This dataset, which includes many Yelp reviews labeled by sentiment polarity, is intended for binary sentiment classification. Because of the

Subsets of the dataset were set aside for testing and training. Tokenization was performed using the DistilBERT autotokenizer, which converted unprocessed text into numerical representations that the model could understand. The sequences had a maximum length of 128 tokens before being padded and truncated. TensorFlow tensors were generated from labels, and training and testing TensorFlow datasets were established.

**Model Architecture**:  DistilBERT is a faster, smaller, and more resource-efficient variant of the original BERT model that still retains the majority of its functionalities. It accomplishes this by employing a number of optimizations, such as knowledge distillation to draw lessons from the original BERT model, lowering the number of transformer layers, and utilizing dynamic masking.

**Model Compilation and Training**: The AdamW optimizer, which improves regularization with better weight decay, was used to compile the model. Sparse_categorical_crossentropy, an appropriate loss function for multi-class classification with integer-encoded labels, was employed. In order to track the model's development and avoid overfitting, ten epochs of training with a batch size of 64 were carried out, and performance evaluation was done on a different test dataset on a regular basis.

Attempts were made to fine-tune the DistilBERT model by freezing its final three layers in an attempt to increase accuracy, especially considering the smaller dataset and fewer training epochs. Unfortunately, only modest accuracy gains were obtained with this method, most likely as a result of the small dataset size and the model's decreased ability to fully adapt to the task.

**RESULT**
Through a rapid decrease in training loss and an increase in accuracy, the training process demonstrated that the model quickly learned from the training data within the first epoch. But in later epochs, neither training loss nor accuracy increased and instead reached an early plateau. The fact that validation metrics did not change during training raises the possibility that the model underfit the data. The model's performance did not improve with additional training, indicating the need for additional fine-tuning adjustments.

**CONCLUSION**

After being adjusted for a smaller sample of the Yelp Polarity dataset, the DistilBERT model displayed possible underfitting and generalization issues. Across several epochs, the model's performance stayed low but steady, indicating problems with the size of the dataset and the impact of layer freezing during fine-tuning. To increase accuracy, future research might investigate employing a bigger dataset, more training epochs, or alternative fine-tuning techniques.
