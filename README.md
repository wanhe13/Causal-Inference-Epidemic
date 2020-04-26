# Causal-Inference-Epidemics
## Author: Wan He

For most of the experiments/simulations done for the project, compartmental parameters estimated by AJ Kucharski are adopted
https://www.thelancet.com/journals/laninf/article/PIIS1473-3099(20)30144-4/fulltext

Required packages:

numpy,matplotlib,gzip,networkx,random,scipy,collections,powerlaw

# Abstract
This project is focused on indentifying network properties that affects disease spreading under compartmental models. Simulations are used to target these underlying network properties through designated experiments. 




A summary of what the project has achieved:

1. Implemented the compartmental models such as the SIR and SEIRD on simulated networks with different structures or properties including the BA model, Watts-Strogatz model, Erdos-Renyi model and their configuration networks that preserve the same degree distribution or/and other network properties such as the total number of edges and nodes. 

2. Compared the spreading patterns of the disease with varying infection rate (beta) while controlling network and recovery rate.

When the social contact network is naively modeled by a BA network, simulation showed that when the infection rate ($\beta$) could be decreased to be a factor of <k> smaller than the recovery rate $\mu$, the spreading of the disease could be immediately stopped, where <k> denotes the average degree of the network. This result indicates that if the government intervention is able to reduce the chance of an individual contracting the disease when in contact of an infected individual, by strictly enforcing practices such as wearing face masks, the disease spreading could be stopped. Simulations also indicated that beta < mu/<k> is not a necessary condition to flatten the curve.

3. Compared the spreading patterns of the disease under different network structures controlling the number of edges and nodes. Simulation results suggest the key factor that characterise the disease spreading pattern (scale and speed) among the network properties is the degree distribution. Fixing total number of links in the model, for networks that reside high-degree nodes, i.e. potential super spreaders, it is easier for the disease to take off.

4. Experimented with running the SIR on the Watts Strogatz with different parameter settings. An observable trend is that as the network becomes more randomised, the epidemic takes off sooner.


5. Built the base toy decentralised-metapopulation network for the disease to spread in. The network is simulated as the following:
Initialisation: Generate nC cliques of which the number of local community nodes follows a Poisson distributin with mean mzero. Connect the cliques with a configurable probability p. At each time step, with the disease spreading model SIR being implemented simultaneously, each node could rewire its inter-community edges with a configurable parameter mobility. The community here could be interpreted as family units where the family members are in regular contact with each other and the mobility factor could be interpreted as a change in social circles. It is also worth noting that an increase in mobility here does not suggest an increase in social activities but just a change of the social activities.

Results from the experiment varying the mobility variable indicates that when the network is small, i.e. small population, mobility promotes disease spreading. Moreover, the rise in mobility is accompanied by an increase in skewness or kurtosis  of the degree distribution.

Interestingly, the spread-boosting effect of the mobility parameter that was significant when the number of communities was 100 seems to vanish when the number of communities was increased to 1000. When the network size becomes large, the effect of increasing mobility becomes insignificant. And that is consistent with the degree distribution of this larger network that seems to be relatively mobility-invariant.

On the other hand, quite intuitively, disease spreading is facilitated by increase in the inter-community connecting probability.


6.Finally, the SIR was implemented on a toy model with an embedded hierarchy and an intervention that immunises the top-degree node at each time step is applied. The effect of the intervention is compared against a randomised intervention strategy where one individual of the community is uniformly randomly chosen to be immunised at each time step. The simulation results suggest that in a hierarchical network, shut-down enforced on high connectivity places like restaurants could very-effectively distort the spreading of the disease, on the other hand, singular random immunisation poses insignificant effect on the spreading. Note this does not suggest collective staying-at-home is not helping with mitigating the disease spreading since the random immunisation in the simulation is applied only on a singular individual at a time.


Conclusion:

Disease Spreading is dependent on the population structure

1. Connectedness
2. Degree distribution
3. Mobility is less important in a decentralised population and its effect decreases as the population size increases
4. Decentralised population helps to prevent disease spreading, on the other hand, it's more efficient to apply immunisation strategy to hierarchically structured or centralised populations






