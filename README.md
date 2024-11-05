# Hot-Cold - GDG Data Science Challenge 2024-25

This repository documents my approach for the GDG Kaggle competition during the 2024-25 recruitment process. I successfully advanced to the third round, where I tackled this challenge focused on predicting temperature changes along a rod.

## Problem Overview
The dataset provided temperature measurements at 50 discrete points on a rod, with these temperatures changing over time. Based on the initial temperature values, our task was to predict the temperature at each of these points in the subsequent time step. Here’s a summary of the key dataset features:
- **L**: Length of the rod
- **nx**: Number of divisions along the rod
- **val_0** to **val_49**: Temperature values at each division point.

## Initial Thoughts and Approach

At first, I considered using multi-linear regression, where the rod could be represented by a line, with temperature predictions made based on the distance from the origin. However, the high dimensionality of the dataset made this approach inefficient and likely unoptimized.

I then explored using PCA to reduce dimensionality. However, with only 50 dimensions and over 1,000 values to predict, reducing further risked diminishing the model’s accuracy.

## Final Solution
Given the sequential nature of the temperature data, I opted for a BiLSTM or BiGRU model, treating the temperature distribution along the rod as a sequence. This approach captured temporal dependencies more effectively, providing a robust solution to the prediction task.
