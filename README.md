# Bayesian Registration of Functional Data

Functional data often present a common shape, but with variation in amplitude and phase across curves. <br/>
The goal of this project is to synchronize data through curve registration in a Bayesian framework. <br/>
We propose a hierarchical model whose job is to account the amplitude variability of the features and to find a warping function that synchronizes all curves.

## Dataset 

Data are a collection of observations regarding a one leg hoop over time for some people. <br/>
They are divided into three groups: healthy people, people who had physiotherapy and people who had surgery. <br/>
Unfortunately, we are not allowed to upload the original data-set, since these data are medical records. But for a better understand you can see the plotted curves in the folder [Plots](https://github.com/PrincipeFederica/Bayesian-Principe-Mattina-Bighignoli/tree/main/Plots) under the name *gruppo_controllo*, *gruppo_fisioterapia*, *gruppo_surgery*. <br/> [Here](https://github.com/PrincipeFederica/Bayesian-Principe-Mattina-Bighignoli/blob/main/Import_data.R) is the code we used to read and plot the original curves.

In order to let you run the code we developed, we built up a set of fake-observations. You can find them in [Simulated Data](link).


## Model 

We implemented a Gibbs Sampler algorithm with one step of Metropolis-Hastings for the time transformation parameters.
The hierarchical model is the following one: <br/>
Consider: <br/>
![alt text](https://github.com/PrincipeFederica/hello-world/blob/main/Schermata%202021-02-11%20alle%2021.49.54.png)  <br/>
And the composite function: <br/>
![alt text](https://github.com/PrincipeFederica/hello-world/blob/main/model2.png) <br/>
The observed value of each curve i at time t is modeled as: <br/>
![alt text](https://github.com/PrincipeFederica/hello-world/blob/main/model3.png) <br/>
We assumed the error terms to be independent and normally distributed with null mean and common variance &sigma;^2.  <br/>
In the end, we identify the i-th aligned curve at time t as: <br/>
![alt text](https://github.com/PrincipeFederica/hello-world/blob/main/Schermata%202021-02-11%20alle%2021.59.10.png) <br/>


If you are insterested in a more detailed description of the model, please rely on the report uploaded in the repository.


## Contents and structure of the codes

1. Data preprocessing 
2. Simulated Data 
3. Metropolis-Hastings step : implementation of the Metropolis-Hastings step for the time transformation parameters;
4. Gibbs Sampler : application of the Gibbs sampler with one step of Metropolis-Hustings to the data;
5. Chain convergence : analysis of the chains;
6. Comparison : this folder cointains a comparison among the three groups previously presented. <br/>
We are aware that you have no access to original data and in particular to the three different groups, but we thought it could be interesting to take a look at it anyway. <br/>
Do people who had surgery have less or more difficulty in jumping with respect to people who had physiotherapy? We tried to answer to this question and more.<br/>
In order to do this, we performed analysis such as the comparison of the posterior shape parameter a and the posterior mean derivative of each group.
7. Report : the report highlights in detail the steps of our work: model building, posterior inferences, comparisons.
8. References : this folder contains the article we consulted during our study;



## Authors
* **Paolo Bighignoli** - MSc in Mathematical Engineering, Quantitative Finance, Politecnico di Milano
* **Federica Mattina** - MSc in Mathematical Engineering, Applied Statistics, Politecnico di Milano
* **Federica Principe** - MSc in Mathematical Engineering, Applied Statistics, Politecnico di Milano


## References
* **Bayesian Hierarchical Curve Registration.** Donatello Telesca, Lurdes Y. T. Inoue. 
Journal of the American Statistical Association (2008).
* **Bayesian analysis for the social sciences.** Simon Jackman. Wiley, New York (2009).
* **An Adaptive Metropolis Algorithm.** Heikki Haario, Eero Saksman, Johanna Tamminen. Bernoulli Journal (2001).
