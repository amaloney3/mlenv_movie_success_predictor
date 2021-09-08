# mlenv_movie_success_predictor

## Data Model

Objective: Predict whether or not a movie will be successful. Success can be measured in various ways, such as: profit = revenue - budget, voter ratings, and awards won. As we learn more about the quality and characteristics of the input and output variables we will refine these metics.

We will build a deep learning model, but our first pass will be a simple neural network with one hidden layer. The output variable will be based on the probability of (average voter rating > 5). (Ratings are on a scale of 0-10) Probability greater than 50% is considered a successful movie.

Although the dataset will ultimately be a mashup of three datasets, our initial demonstration of the model will use data from one source input as a csv file. This will be replaced later by a cloud-based database, but this does not impact the model demonstration.

To support the incremental use of additional hidden layers, and allow visualization with tensorflow, we use the Keras sequential model with one hidden layer containing 10 nodes. The ReLU activation function will be used in the expectation there are nonlinear relationships in the data. The output layer will use the sigmoid activation function and one neuron to produce a probability.

The dataset comes from the The Movies Database in Kaggle. It has been filtered to movies produced in the US and released after 1989. The years 2018 forward are sparse. There are 12,906 movies.

The features dataset contains 7 variables:
* movie runtime in minutes, numeric
* release year, numeric
* movie has a website
* movies does not have a website
* movie is part of a collection
* movie is not part of a collection

This model was trained and tested. After 50 epochs, the model produced loss=54% and accuracy=74%
