
# TEXT SUMMARIZER

The process of producing summaries from the huge sets of information while maintaining the actual context of information is called Text Summarization. The summary should be fluent and concise throughout.


## About The Project

In this project, we will use many to many sequence models using the Abstractive Text Summarization technique to create models that predict the summary of the reviews. The model will be trained and tested on the first 1,00,000 rows of the dataset file ‘Reviews.csv’.
## Types

- Extractive Summarization
- Abstract Summarization
## Models Used

**SEQUENCE TO SEQUENCE (SEQ2SEQ)**:-    

Seq2Seq model is a model that takes a stream of sentences as an input and outputs another stream of sentences. This can be seen in Neural Machine Translation where input sentences is one language and output sentences are translated versions of that language. Two main techniques used in this model are:-

- Encoder
- Decoder

**Encoder**     
The encoder model transforms input sentences, preserving context and capturing essential information through internal states like hidden or cell states, especially in LSTM layers. In neural machine translation, the input language undergoes encoding to maintain contextual information without altering the input's meaning, followed by passing the encoded outputs to the decoder for generating the output sequences.

**Decoder**     
The decoder model predicts target sentences word by word, taking target sentence inputs and generating subsequent words sequentially. It utilizes '<start>' and '<end>' tokens to indicate the beginning and end of sentences, guiding the prediction process. During training, the model starts with '<start>', predicts subsequent words, and feeds these predictions as inputs for the next time step to generate the full sentence.

## Dataset

For dataset, we referred to Kaggle and chose "Amazon Fine Food Reviews". This dataset consists of reviews of fine foods from amazon. The data span a period of more than 10 years, including all ~500,000 reviews up to October 2012. Reviews include product and user information, ratings, and a plain text review. It also includes reviews from all other Amazon categories.

You can download the dataset from here:-

[Amazon Fine Food Reviews](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
## Steps for Text Summarization

Our project consists of the following steps. By completing these steps it will ensure that the project runs smoothly and error-free.

- Import the Libraries
- Parse the Dataset file
- Preprocessing
- Splitting the records
- Text Vectorization
- Build the model.
- Train the model.
- Inference Model

## Working and Detailed Explanation

- We will traverse to the dataset file i.e. ‘ Reviews.csv ’ and extract all the input and target texts. For this we will be using the first 1,00,000 rows of our dataset for the training and testing part. It can be changed tho. Our input will be the ‘Text’ column which is the review column and target will be the ‘Summary’ column.
- We will also drop the duplicate records and NA values from our dataframe.
- Real-world texts are incomplete. So, we clean all our texts and convert them into a presentable form for prediction tasks. Remove all the html tags using ‘BeautifulSoup library’. After that, we tokenize our texts into words. We will also check the following conditions and remove them if they exists:

        1) contains integers
        2) are less than 3 characters or
        3) they are in stop words

- Expand all the contraction words, then we will stem all the input words to their root words. If we don’t stem our words then the model will treat them as two different words. Stemmer will stem or reduce that error word to its root word.

- Split the dataset records into training and testing sets. We will be splitting in the 80:20 ratio where 80% record will be for training sets and 20% for testing sets.

- We will convert our word into integer sequence using vectorization technique.

- We are using Stacked LSTM containing 3 layers of LSTM stacked on top of each other. This will make our prediction much better. As per your requirement, you can have more also.

  ![model_plot](https://github.com/sameewyne/Text-Summarizer-AI-/assets/113854930/424959f5-3412-4e25-bf03-c69b76892afc)

- We will be using the saved model to create an inference architecture for the encoder and decoder model. The inference model is used to test the new sentences for which the target sequence is not known.

- After training and testing the data on our model, we obtain the following graph:

  ![graph](https://github.com/sameewyne/Text-Summarizer-AI-/assets/113854930/888603c5-2083-4588-8082-9cdea7b80cbf)

## Summary

In this project, we have developed a Text Summarizer model which generates the summary from the provided review using the LSTM model and Attention Mechanism. We got an accuracy of 87.82% which is good as we have taken only 1,00,000 records for training and testing sets.
## Submitted By

- Samee Wyne (21L-5626)
- Raahim Naeem (21L-5610)
