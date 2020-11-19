# Mechanis-of-Action
Kaggles - Mechanisms of Action (MoA) Prediction: https://www.kaggle.com/c/lish-moa

This is a competition that was set by MIT and Harvard, the Laboratory for Innovation Science at Harvard (LISH), and the NIH Common Funds Library of Integrated Network-Based Cellular Signatures (LINCS). The objective of this challenge is to define the several mechanisms of action that a determined drug has.

The biggest problem of this challenge was the lack of knowledge about the variables. Our dataset has only 4 different variables:\
one expressing the dosage of the drug;
another expressing the durantion;
several (more than 700) variables expressing the genes; and
several (100) variables expressing the cell.

It would be of great help if we had someone of the field that could explain the meaning of these variables. Ther was not only a lack of understanding about what is a gene variable or a cell variable, but also a lack of understanding in how the dosage and duration variable are intertwined with the genes and cell variables.\
Moreover, there are 206 mechanisms of action. If we had knownledge of someone in the field, we would be able to tune our model better, e.g., excluding predictions that results in more than one MoA that are impossible to happen.

Having said that, we tryed two approachs. First, modeling the probabilities of one mechanism of action per time using LightGBM. Second, model all MoAs togheter using a feedforward neural network.

The biggest problem of LightGBM is that its multilabel algorithm doest not support one observation with more than one label. Therefore, to try this model we had to do 206 different models, one per MoA. This disconsider any correlation that may exist among the several MoAs and is too time consuming.\
To solve this problem, we tried a second model using feedforward neural network. We had an increase in performance in doing so.\
After, we tried to construct new variables. However, we did not achieve a lower log loss. In this part of the project it would be of a great help if we could talk with someone that grasps drugs development.\
Considering new variables, we only got luck when using unobserved learning. With it we were able to group some drugs considering only the cell variables.

To help in the navigation of this project, here is a briefly description of each file or paste.
