# mlenv_movie_success_predictor

## Data Model

Objective: Predict whether or not a movie will be successful. Success can be measured in various ways, but we start with these metrics: profit = revenue - budget, voter ratings, and awards won. As we learn more about the quality and characteristics of the input and output variables we will refine these metics.

We will build a deep learning regression model, but our first pass will be a simple neural network with one hidden layer. The output variable will be based on the probability of average voter rating > .5, where a rating over 5 (out of 10) is considered a successful movie.

Although the dataset will ultimately be a mashup of three datasets, out initial demonstration of the model will use data from one source input as a csv file. This will be replaced later by a cloud-based database, but this does not impact the model demonstration.

To support the incremental use of additional hidden layers, and allow visualization with tensorflow, we use the Keras sequential model with one hidden layer. The ReLU activation function will be used in the expectation there are nonlinear relationships in the data. The output layer will use the sigmoid activation function and one neuron to produce a probability

I'm getting an error that I haven't yet figured out.
