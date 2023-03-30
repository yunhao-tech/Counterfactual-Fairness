# Counterfactual Fairness Reproduction
Project repo for MAP670M - Causal Inference at Institut Polytechnique de Paris

Instructor : Marianne Clausel; Contact: marianne.clausel@univ-lorraine.fr

This project is based on the paper: Counterfactual Fairness by Kusner, Loftus, Russell, and Silva (https://arxiv.org/abs/1703.06856)

Team members: Yunhao Chen, Hugo Peltier

Please refer to the [notebook](Counterfactual_Fairness.ipynb) for a detailed explanation. To install the required Python dependencies, you can run the following command in  the project working folder:
```cmd
conda env create -f environment.yml
```

## Description
Using the real data of law school success example from the paper, we reproduce our version of four methods mentioned in the paper, including two unfair models as baseline and two proposed fair models.

More precisely, the four models are implemented:

- `full` model: using all attributes including the protected ones (race and sex in this case)
- `unaware` model: using only non-protected observed attributes (GPA and LSAT) to predict FYA
- `fair K` model: inferring the latent variable K from observations, to predict FYA
- `Fair Add` model: consider the observed attributes (GPA, LSAT and FYA in this example) as continuous variables with additive error terms independent of protected attributes (race and sex).

The framework is on `Pyro` which is a probabilistic programming language built on Python and PyTorch.

## Remark
The dataset is imbalanced in terms of "race". We have split the train/test set while preserving the data balance. What we could do better, is to weight the loss according to the proportion of each race, trying to penalize more for the overrepresented race class. 





