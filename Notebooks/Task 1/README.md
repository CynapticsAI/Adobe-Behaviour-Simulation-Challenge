# Task 1

- All the dataset used in this task have been provided in [this](./dataset%20names.txt) file.

## Steps to run 

### Training:

- First create the BERTweet embeddings for all attributes of each dataset , ie the 3 train datasets , by running the  embeddings-generator-test-or-train book.
You'll need to change the paths of the dataset or the column name to generate embeddings of different attributes.
The attributes whose embeddings are to be extracted are username, date, content, content+date+username.
The content+date+username will be termed as combined embeddings/full-content embeddings.
The username, date and content embeddings will be termed as individual embeddings.

- Once all the embeddings are been extracted, feed them into the classifiers.
We have used two different types of classifiers namely bert-classifer which uses BERTweet embeddings(all the individual attributes embedding) as an input and also a normal-classifer which only uses the dataset as an input only. Train the respective classifiers and save their weights.

- Now run the regressor notebooks to train the regressor. We have used two types of regressors name **m1** and **m2** which give almost the same output.
The two regressors take full-content embeddings and content embeddings fo each dataset as an input respectively. Set the paths of the dataset and the regressor will classify the dataset into different classes and will be trained on each class. Save the regressor weights which will be loaded for inference later.

### Inference 

- First create the BERTweet embeddings for all the attributes of each dataset, i.e. test dataset, by running the embeddings-generator-test-or-train book.
You'll need to change the paths of the dataset or the column name to generate embeddings of different attributes.
The attributes whose embeddings are to be extracted are username, date, content, content+date+username.
The content+date+username will be termed as combined embeddings/full-content embeddings.
The username, date and content embeddings will be termed as individual embeddings.

- Once the embeddings are being extracted, feed the individual embeddings into the classifier for prediction of classes. Along with the embeddings, we also have to load the classifier model.(You can directly download the weights from the Kaggle datasets we've mentioned later)

- We have used two different types of classifiers. One uses the BERTweet embeddings of the individual attributes and is termed as bert-classifier and the other classifier only takes the dataset as as input and uses its own vectorization method to predict the class, and is termed as normal-classifier.Both of these classifiers were benchmarked and both of these gave nearly the same result. Through both of these classifiers youll get the predictions of the class of each tweet. Convert these predicted classes into a csv file.

- The predicted classes by the classifier, the embeddings and the stored regressor model weights are used as an input to predict the exact number of likes for each tweet. There are two types of regressor we used namely **m1** and **m2** which uses combined embeddings, i.e. full content embeddings and only tweet content embeddings, i.e. content embeddings respectively. Both the models were benchmarked and both gave nearly the same result. Use the inputs stated before and predict the likes of each tweet. Convert these predictions into a csv file.

- The tweets predicted were in decimal numbers. Therefore, we decided to round-off them by using the built-in excel function.
There were also some unwanted columns generated which were then deleted in excel itself.

- m1-regressor and normal-classifier gave the best results for unseen time-period and m2-regressor and bert-classifier gave the best results for unseen company task. Hence, these were used for final result evaluation.

**NOTE** - Please load the embeddings from the Kaggle datasets provided by us. Since, the content depends on filename and relative file orders in the dataset. Therefore, it is advised to manually the datasets and preoceed with it.
Sorry for the inconvenience.

The embeddings and model weights are stored and can be loaded from Kaggle. The datasets are under the user TheNetherWatcher in its shared-with-you datasets section.

Also we have given a text file containing all the datasets which will be required **for training and inference** to be downloaded in a [here](./dataset%20names.txt).

## Final results

#### For unseen comapany - [Here](../../team_22_results/behaviour_simulation_test_company.xlsx)

#### For unseen time period - [Here](../../team_22_results/behaviour_simulation_test_time.xlsx)
