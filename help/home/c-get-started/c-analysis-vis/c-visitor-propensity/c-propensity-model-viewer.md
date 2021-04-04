---
description: A model viewer lets you generate a logistic regression model using the Propensity Scoring feature.
solution: Analytics
title: Model Viewer
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
---
# Model Viewer{#model-viewer}

A model viewer lets you generate a logistic regression model using the Propensity Scoring feature.

The Model Viewer displays the coefficient weights of each input variable (including the constant term) and their statistical error range. Input variables showing a high absolute coefficient and small margin of error are the most significant predictors in the model.

**To Open a Model Viewer chart**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] . 
1. Hover over Model Complete of a saved score.

![](assets/propensity_model_viewer.png)

The input variables with a coefficient >= 1 are positive influences on the propensity model. The coefficients that are < 1 are negative influences on the propensity model. The range defined within the parentheses is the error, and indicates the consistency of the input variable across the successful population.
