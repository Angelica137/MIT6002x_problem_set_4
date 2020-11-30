# Introlduction

In this problem set, you will use regression analysis to model the climate of different areas and try to find evidence of global warming. You will create models to analyze and visualize climate change in terms of temperature.

Download ps4.zip.

Please do not rename the files we provide you with, change any of the provided helper functions, change function/method names, or delete provided docstrings. You will need to keep data.csv in the same folder as ps4.py.

To model the change in climate of an area, you will need some data. For this problem set, we will use temperature data obtained from the National Centers for Environmental Information (NCEI). The data, stored in data.csv , contains the average temperatures observed in 21 U.S. cities from 1961 to 2015. Open the file, and take a look at the raw data.

In order to parse the raw data, in ps4.py w e have implemented a helper class Climate. You can initialize an instance of the Climate class by providing the filename of the raw data. Look over this class and read its docstrings to figure out how to get data for the following problems.

# Problem 1: Curve Fitting

Implement the generate_models function.

x and y are two lists corresponding to the x-coordinates and y-coordinates of the data samples (or data points); for example, if you have N data points, x = [x1 , x2 , ..., xN ] and y = [y1 , y2 , ..., yN ], where x_i and y_i are the x and y coordinate of the i-th data points. In this problem set, each x coordinate is an integer and corresponds to the year of a sample (e.g., 1997); each corresponding y coordinate is a float and represents the temperature observation (will be computed in multiple ways) of that year in Celsius. This representation will be used throughout the entire problem set.
degs is a list of integers indicating the degree of each regression model that we want to create. For each model, this function should fit the data (x,y) to a polynomial curve of that degree.
This function should return a list of models. A model is the numpy 1d array of the coefficients of the fitting polynomial curve. Each returned model should be in the same order as their corresponding integer in degs.
Example:

print(generate_models([1961, 1962, 1963],[4.4,5.5,6.6],[1, 2]))
Should print something close to:

[array([ 1.10000000e+00, -2.15270000e+03]), array([ -8.86320195e-14, 1.10000000e+00, -2.15270000e+03])]
The above example was generating a linear and a quadratic curve on data samples (xi, yi ) = (1961, 4.4), (1962, 5.5), and (1963, 6.6). The resulting models are in the same order as specified in degs. Note that it is fine you did not get the exact number because of numerical errors.

Note: If you want to use numpy arrays, you should add the following lines at the beginning of your code for the grader:
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"
Then, do import numpy as np and use np.METHOD_NAME in your code. Unfortunately, pylab does not work with the grader.
