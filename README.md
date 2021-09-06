# mlenv_movie_success_predictor

## Data Model

Objective: Predict whether or not a movie will be successful. Success can be measured in various ways, but we start with these metrics: profit = revenue - budget, voter ratings, and awards won. As we learn more about the quality and characteristics of the input and output variables we will refine these metics.

We will build a deep learning regression model, but our first pass will be a simple neural network with one hidden layer. The output variable will be based on the probability of average voter rating > .5, where a rating over 5 (out of 10) is considered a successful movie.

To support the incremental use of additional hidden layers, and allow visualization with tensorflow, we use the Keras sequential model with one hidden layer. The input layer has xx variables. the ReLU activation function will be used in the expectation there are nonlinear relationships in the data.

insert info about input data, optimization fn and loss metric when finished debugging the model.

The output layer will use the sigmoid activation function and one neuron to produce a probability.

insert description of output
