# Consumption-Case-Study
Analyzing features that influence consumption (energy, production, temperature)

In this case study, I analyzed various factors that influence different types of consumption including
energy, production, and temperature as time progresses.
A more detailed report in located in the `Case Study` PowerPoint.
Below is a summary of my analysis of the Case Study.

## Energy

In order to find a method to predict energy consumption accurately, I built 4 different models:
Linear, Decision Tree, Random Forest, and Recurrent Neural Net.
To build these models, I used 30 lagged variables for a total of 30 minutes look back in time
to predict 5 minutes into the future.
Very surprisingly, energy consumption is most influenced by its most recent known apparent power
and has a very step dropoff the further the information is in the past.
The Linear model performed the best with Decision Tree, Random Forest, and RNN having comparable results.
None of the models can forecast anomalies well with RNN being the least likely to predict an extreme value.

## Temperature

Similar to predicting energy consumption, I built 4 different models as specified previously and
used 12 lagged variables for a total of 12 hours look back in time to predict 3 hours into the future.
Contrasting energy consumption, temperature appears to be more influenced by past temperatures within a time period of 3 hours.
Still, the best performing model is Linear with Random Forest having comparable results.
RNN still performed slightly worst than every other model.

## Production

In order to determine which predictors (i.e. group, sku, Poste de travail, Centre de coûts) have the most influence on units, weights,
and scraps produced, I built 2 different models: Decision Tree and Random Forest. Both models have comparable results.
In general, units, weights, and scraps imply one another so if the number of units produced increases, the amount of weight produced
generally increased and also the amount of scraps. The amount of units produced is also depends on what sku (i.e. product reference) the unit
belong to and the amount of weights produced is also depends on the group of machines the unit belongs to.
Amount of scraps are generally dependent only on the number of units and the weights produced.
Although there are apparent differences in production consumption by different Poste de travail or Centre de coûts,
the differences can mostly be attributed to the sku of the unit and the specific group of machines the unit belongs to.