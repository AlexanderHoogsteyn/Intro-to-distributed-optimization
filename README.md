# Intro to distributed optimization
_This Jupyter notebook aims to provide an introduction to distributed optimization in energy system modelling by providing an example of a simple economic dispatch problem_

The energy transition is changing our power system from a top-down system with central generation of electricity to one with an increased number of distributed generation assets such as PV systems. Increased penetration of renewables is creating a drive to invest in more interconnection capacity to use for cross-border trade. Emerging technologies such as hydrogen and renewable gas and renewable heat are coupling sectors. These factors are increasing the complexity of energy models that aim to study the effects of the energy transition substantially. This is creating a need to improve the algorithms being employed in energy system modelling.

A common approach to keep increasingly complex optimization problems computationally tractable is to split the single optimization problem into pieces that represent single actors in the energy system and solve it using a distributed optimization method. This notebook aims to give a brief introduction to distributed ADMM (or dADMM), a commenly used distributed optimization technique. dADMM is applicable to a wide range of applications, energy system modelling being one of them.

Besides the computational argument, there is another reason a modeller might prefer to use a distributed formulation of an optimization problem. In energy system modelling, most commenly, the "central planner perspective" is used to model energy markets in which one central planner aims to minimize the costs of the system. However, a modeler can also take an "multi-agent equilibrium perspective" in which all participants in the market aim to maximize their profit. Such a "equilibrium model" formulation resembles micro-economic problems more closely and allows more modelling freedom in implementing distortions to the decision making of the agents.

The "central planner perspective" and "multi-agent equilibrium perspective" lead to the same optimum, under certain conditions, and in that case they are therefore equivalent. This can be shown by writing down their optimality conditions (https://en.wikipedia.org/wiki/Karush%E2%80%93Kuhn%E2%80%93Tucker_conditions). However, if a modeller makes use of the extra modelling freedom ofthe equilibrium approach, an equivalent "central planner perspective" optimization formulation does not exist.

## References
Orginal paper Boyd on ADMM:

- Boyd, Stephen. 2010. “Distributed Optimization and Statistical Learning via the Alternating Direction Method of Multipliers.” *Foundations and Trends® in Machine Learning* 3 (1): 1–122. https://doi.org/10.1561/2200000016.

Paper on how to apply ADMM to electricity markets:

- Höschle, Hanspeter, Hélène Le Cadre, Yves Smeers, Anthony Papavasiliou, and Ronnie Belmans. 2018. “An ADMM-Based Method for Computing Risk-Averse Equilibrium in Capacity Markets.” *IEEE Transactions on Power Systems* 33 (5): 4819–30. https://doi.org/10.1109/TPWRS.2018.2807738.

Example paper on coupling of multiple markets using ADMM (e.g. ETS and electricity):

- Bruninx, Kenneth, Marten Ovaere, and Erik Delarue. 2020. “The Long-Term Impact of the Market Stability Reserve on the EU Emission Trading System.” *Energy Economics* 89 (June): 104746. https://doi.org/10.1016/j.eneco.2020.104746.
