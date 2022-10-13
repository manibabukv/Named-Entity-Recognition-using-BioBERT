# NER_Using_BioBERT_On_Sjogren-s_Syndrome_Dataset
We are using BioBERT to do Named Entity Recognition on Sjogren's Syndrome Dataset
## Data Preparation:
We created Sjogren’s syndrome dataset (SSD) with 2530 PubMed abstracts retrieved using keywords Sjogren’s syndrome and its variants. We tokenized these abstracts into a list of sentences. We have round 26000 sentences from this 2350 abstracts, we removed the unnecessary words from these sentences and made the dataset ready for analysis. The next step is identifying the causal sentences within these sentences to identify cause and effect factors related to Sjogren’s syndrome. For this we created a list of causal words and tried to filter out the sentences that are having these causal words, we used Python for this process. By this process we got around 21770 sentences out of those 26000 sentences as causal. The problem with this approach is the causal word might not be the root word in the sentence but still the sentence might return as causal sentence because it has the word. To overcome this problem, we ran a classification model on this 21770 sentence that gives a probability score whether the sentence is causal or not. Out of 21770 we have around 5655 sentences with probability more than 90 percent of being causal sentences. We cleared the unnecessary data that is not required for our analysis and finalized the sentences.
## Model
The model description and how to use it, is cleared explaned in the notebook file.
## Sample Results:
### Sentence:
Pulmonary arterial hypertension (PAH) is a severe complication and leading cause of mortality in patients with primary Sjogren's syndrome (pSS).
### Output:
[{'Pulmonary': 'B-Entity'}, {'arterial': 'I-Entity'}, {'hypertension': 'I-Entity'}, {'(PAH)': 'O'}, {'is': 'O'}, {'a': 'O'}, {'severe': 'O'}, {'complication': 'O'}, {'and': 'O'}, {'leading': 'O'}, {'cause': 'O'}, {'of': 'O'}, {'mortality': 'O'}, {'in': 'O'}, {'patients': 'O'}, {'with': 'O'}, {'primary': 'B-Entity'}, {"Sjogren's": 'I-Entity'}, {'syndrome': 'I-Entity'}, {'(pSS).': 'O'}]
## Conclusion:
From our observation, the model is performing pretty well. It able to recognize most of the entities that are related to diseases. To run the model on our, we divided data 6 datasets and ran the model on the datasets.
