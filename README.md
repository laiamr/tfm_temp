# tfm_temp
Temporary repo for the TFM

There are several folders:

1-	**Data**: contains the main files for the pipeline<br>
  -	*CAT_Lexicon*: contains the Catalan keywords and the typology of borrowing<br>
  -	*CAT_Tweets_20250513*: dataset collected during the previous run of scraping<br>
  -	*Manual-partial_annotated*: dataset with the first 300 tweets annotated with social media sense 1 (yes) or 0 (no)<br>
  -	*cleanDataset*: generated in the Dataset_handling script, and used in the model training script. It contains the dataset filtered by keyword and language, and cleaned of hashtags and links<br>
  
2-	**Inflect_Cat_forms**: contains a datafile and script to extract inflected forms from the lemmas using the vocabulary of a SpaCy language model (I haven’t found any library to generate inflections for Catalan)<br>

3-	**MostCommonPOS**: contains a datafile and a script to extract the most common verbal forms from a corpus of Catalan data (Ancora, Projecte Aina)<br>

4-	**Scripts**: contains the scripts for the main pipeline<br>
  -	First, the *Dataset_handling* file pre-process the data until the word sense disambiguation, and tries to extract a small context for each of the keywords in the tweets (don’t know what to use this last part for, yet)<br>
  -	Then, the *SenseDisambiguationModel_BERT* script trains a classifier to detect the senses related to social media, based on a pretrained BERT model for Catalan and a Logistic Regression.<br>
