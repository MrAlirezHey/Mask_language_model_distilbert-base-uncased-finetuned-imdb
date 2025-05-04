In this code, we used the distilbert-base-uncased model and fine-tuned it on our custom IMDB dataset. This model is suitable for the masking task, but you can also use it for sentiment classification—determining whether IMDB reviews are positive or negative.

Challenges We Faced:
One of the main challenges was handling the dataset. We first tokenized each review, then concatenated all the tokenized texts together into a single sequence. After that, we divided the sequence into chunks to prepare our training data.

We trained the model using the Trainer API from the Hugging Face Transformers library.

Evaluation Metric:
Our evaluation metric is perplexity, which is commonly used for generative models. Perplexity measures how "surprised" the model is when predicting the next word. A lower perplexity indicates that the model assigned a higher probability to the correct next word, meaning it was less surprised.

We chose this metric because, in tasks like masked language modeling, the model isn't predicting a single label. Instead, it outputs probabilities over many possible tokens, and we're interested in whether the model gives high probability to the correct masked word.

