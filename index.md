```reference draft whitepaper``` 
# Oracle Performance Metrics
Decentralised applications and the oracles on which they depend need some way to demonstrate their ongoing utility and reliability.

This proposal investigates the idea of recording performance metrics using blockchain metadata and then aggregating metadata entries to produce metrics that can be used to assess performance of automated services.

## Example Problem
Let's say that you have a decentralised application protocol, enforced as a smart contract which allows a user to take out a loan, and the interest rate they pay is determined based on some credit scoring model. A high score means a lower interest rate due to a lower risk.

The value returned by that credit scoring model is returned based on an invocation of some model that operates as a smart contract Oracle.

The borrower needs to be assured that this score is based on a fair assessment of their risk.

The lender needs to be assured that the score does a good job at differentiating low and high risk borrowers.

The maintainers of the lending protocol need to demonstrate to the community that their score is performant and secure.

#### Blockchain Metadata

A set of publicly accessible, perfomance metrics - appropriately signed by the maintainer's of the protocol - could be used to provide assurance of the credit score's authenticity, reliability and utility. These metrics, stored as blockchain meta data information in periodic transactions could be used to provide assurance to the both parties involved in the transaction while giving the maintainers of the lending protocol a reference point for any assessment of their protocol.

##### Implementation Steps
1. The maintainer of the protocol registers the credit score transaction oracle on the blockchain
2. The application which determines the credit score should record all requests
3. Periodically, after the credit score performance window has elpased (say, 3 months - enough time to determine if the borrower has defaulted) for each set of transactions, the maintiner of the protocol should aggregate and collate performance metrics for the model. Eg:

    - Gini of the score (How good the model is at separating goods from bads)
    - Percentage of bad loans where a score over a certain threshold was determined
    - Percentage of good loans where a score under a certain threshold was determined


4. These metrics can then be published to the blockchain, along with:

    - A reference to the registration blockchain request
    - A link to the raw data used to determine the performance metrics
    - A hash of the performance metric data

#### Aggregating the Data

As a time series of these performance metrics buids up, the blockchain meta data can be queried, summarised, aggregated and referenced to build some incredible potential into the ecosystem.


#### Conclusion and Extensions
The blockchain is a good fit for referencing persistant performance metrics via metadata.
If the approach taken was generic enough - that is, a generic schema was created to register applications and another generic schema could be used to report performance metrics - then this method and reporting mechanism could be extended to any type of automated service which needs a mechanism to demonstrate its reliability or utility,

##### Competiton
What if we had an ecosystem that had many nodes competing to provide the best credit risk algorithm? If all of the nodes periodically reported their results, a natural competitive market place would form.

##### Reinforcement Learning
What if each node in the ecosystem could get better at predicting credit risk based on the raw data referenced in each of these reports? A natural reinfocment learning pattern would evolve.

##### AI Service Selection
What if Artificial Intelligence agents could use this performance meta data to determine which node in the ecosystem it wished to use depending on particular purposes and contexts?=A natural AI choice model would start to develop.

### Authors

* Michael Hodder
* Thushare Dissanayake 
* Steven Pirois

### Cardano Proposal
The Cardano blockchain's capacity to store 16k worth of meta data . A proof-of-concept of the idea is planned for a Catalyst Project Fund 5 Proposal

