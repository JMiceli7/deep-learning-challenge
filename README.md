# deep-learning-challenge

1. **Overview** 
This project attempts to create a binary classification neural network model that can predict whether applicants will be successful if funded by fictional company, Alphabet Soup. The model takes into consideration a large data set of over 34,000 organizations, their details, and how successful they were. The model had an initial accuracy of 0.7261807322502136. I then created another file in which I made 4 attempts to increase the accuracy of the model with the adjustment of varying optimization factors. 

2. **Results**:

* Data Preprocessing
    * The target variable for this model is the 'IS_SUCCESSFUL' column, as we are attempting to classify a sample of given inputs into either a successful or unsuccessful category

    * The features for this model are the remaining columns of the data set. This would be the information from the APPLICATION_TYPE	AFFILIATION	CLASSIFICATION	USE_CASE	ORGANIZATION	STATUS	INCOME_AMT	SPECIAL_CONSIDERATIONS	ASK_AMT columns

    * The EIN and NAME columns were removed from this model as they are neither features or target variables

* Compiling, Training, and Evaluating the Model
    * In the first iteration of the model, I chose 8 neurons for first layer, 5 neurons for the second layer, two overall layers, the relu activation function, and 100 epochs. I chose 2 layers to begin with to avoid risk of overfitting the model, and same idea for my choice of neurons. I did not want to create too complex of a model in the first iteration. 

    * Unfortunately, the first attempt did not produce the target > 0.75 accuracy output. The value was 0.7261807322502136

    * In an attempt to improve the accuracy I attempted 4 additional optimization methods:
        * 1st improvement attempt: In this attempt, I greatly increased the number of neurons and layers, moving from 2 to 4 layers and from 8 and 5 neurons to 128, 64, 32, and 16 respectively across the layers. I also used 500 epochs compared to the 100 in the original iteration as well as the 'leaky_relu' compared the the 'relu' activation function to better handle the dataset. This attempt yieled slightly weaker results at 0.7244315147399902.

        * 2nd improvement attempt: Here I went even bigger. 5 layers, 128, 100, 70, 40, 20 neurons respectively, epoch set to 1000 and the use of the originally attempted relu activation function. This resulted in slightly improved from the previous attempt but not better than the original at 0.7257142663002014.

        * 3rd improvement attmept: Here I used a new type of optimizer, the RMSprop. This optimizer allowed me to adjust the learning rate and to normalize gradiants in a way adam optimzer did not. I also returned to 2 layers, fewer neurons, and lower epoch number since the increases had so far not improved beyond the specs of the original iteration of the model. This attempt yeilded a similar accuracy still at 0.7252478003501892.

        4th improvement attempt: This final attempt involved the use of 2 layers but increased number of neurons. This is a change from the original iteration, same number of layers but an increased number of neurons, 32 and 16, and the leaky relu activation function

3. **Summary**: 
After several attempts to improve the deep learning model, the highest accuracy achieved was the original model interation with an accuracy score of 0.7261807322502136, which is still below the goal of 0.75. Despite trying a wide variety of layer numbers, neuron amounts, epochs, and activation functions, the improvements were minimal. It is possible that this model’s structure may not be enough to achieve an accuracy at the target level. It is possible this is due to issues in the data set as well. Researching alternative approaches, it seems an ensemble method may be an improvement from the model attempted in this project. Random forest is an example of an ensemble method that could better handle complex categorial features.
