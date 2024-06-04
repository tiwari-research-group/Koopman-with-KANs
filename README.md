# Koopman-with-KANs

This code is designed to implement the Koopman Operator using the method outlined in our paper 'Leveraging KANs for Enhanced Deep Koopman Operator Discovery'. It implements the dynamics of a pendulum and two-body problem and includes the data generation file, the code to train and predict the dynamics linearly.

Data Generation must be run prior to the actual running of the training and simulation as the data files will need to be created. Note that this runs on a CPU as outlined in the paper and data generation should take a few seconds. Additional dependencies will need to be installed but installing the kans package from Liu et. al installs a number of these.

data_generator_control.ipynb: Data generation code for PENDULUM which will automatically save the X,Y,U datasets as .pt files. It is possible to change parameters such as dataset size, simulation time, timestep, noise, dynamic properties (gravity and length), as well as the size of the random control input. Changing these parameters will alter the training dataset.

KAN_Pendulum.ipynb: Neural network training code and Koopman linear dynamic prediction. This code imports the data from the data generator and trains the KANs model. The KANs architecture is also defined, with the hyperparameters being able to be tuned. The training is ran for a pre-specified number of steps for a given number of grids. Linear prediticion of the dynamics is also displayed with the true nonlinear dynamics and comparison error plots given. Finally a plot of the LQR response is given based on the simple LQR controller developed in the code.

Data_Generator.ipynb: Data generation code for TWO BODY PROBLEM, which will automatically save the X,Y,U datasets as .pt files.

KAN_2BP.ipynb: Same as the Pendulum version except modified for Two-Body problem dynamics.
