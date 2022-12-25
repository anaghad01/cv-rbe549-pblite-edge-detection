# Pb-lite edge detection algorithm.

## Overview
In this assignment, a simplified version of Pb probability of boundary was to be implemented. This algorithm finds boundaries by examining brightness, color, and texture information in multiple scales.The implementation of this algorithm was intended to outperform the standard Sobel and Canny filter edge detection algorithms. The algorithm has five main basic steps:
- Filters- Three different filters: Oriented Derivative of gaussian Filter, Leung-Malik Filter and Gabor filter are implemented.
- Create Half-Disc masks
- Generate Texton Map and Texton Gradient.
- Generate Brightness Map and Brightness gradient.
- Generate Color Map and Color Gradient.
- Combine information from the features with a Sobel and
Canny methods (Average).

## Filters
### 1. Oriented Derivative of Gradient filter
The first order derivative is computed by convolving the Gaussian with Sobel in respect to horizontal and vertical axes. The resultant derivative of Gaussian is then oriented by given number of orientations. This oriented Derivatives of Gaussian are appended to form the DoG filterbank. For the code implementation, 2 scales and 16 orientations were used resulting in 2 ×16 filters

### 2. Leung-Malik filter
The implemented Leung-malik filterbank has 48 filters in total. Two versions of Filterbanks are implemented for the scope of the assignment: LM Large and LM Small. The basic flow for generating a LM filter is to start with generating a gaussian filter. Then the computation of Laplacian of Gaussian is done. While calculating the LoG, The Gaussian Filter is convolved with the Laplacian Negative matrix to get the LoG filter matrix. The other Derivative of Gaussian and Second derivative of Gaussian are added to the filterbank in the next step.

### 3. Gabor filter
A 2-D Gabor filter is a Gaussian kernel function modulated by a sinusoidal plane wave. A Gabor filter can be used to automatically extract features using a filter bank.

## Running
```sh
cd Phase1
python Wrapper.py
```
