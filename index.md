```reference draft whitepaper``` 
# Oracle Performance Metrics
Decentralised applications and the oracles on which they depend need some way to demonstrate their ongoing utility and reliability.

This proposal investigates the idea of recording performance metrics using blockchain metadata and then aggregating metadata entries to produce metrics that can be used to assess performance of automated services.

## Example Problem
Let's say that you have a decentralised application protocol, enforced as a smart contract which allows a user to take out a loan, and the interest rate they pay is determined based on some credit scoring model. A high score means a lower interest rate due to a lower risk.

The value returned by that credit scoring model is based on an invocation of some model that operates as a smart contract Oracle.

Consider the actors in this decision making process:

* The borrower needs to be assured that this score is based on a fair assessment of their risk.

* The lender needs to be assured that the score does a good job at differentiating low and high risk borrowers.

* The maintainers of the lending protocol need to demonstrate to the community that their score is performant and secure.

We propose that metadata, stored on the very blockchain where the transaction is taking place is the best place to give all actors assurance that the process is fair, reliable, performant and secure.

#### Blockchain Metadata

A set of publicly accessible perfomance metrics - appropriately signed by the maintainer's of the protocol - can be used to provide assurance of the credit score's authenticity, reliability and utility. These metrics, stored on the very blockchain the smart contract is being applied, in periodic transactions could be used to provide assurance to both parties involved in the transaction while giving the maintainers of the lending protocol a reference point for any assessment of their protocol.

#### Implementation Steps

##### Registration
The maintainer of the protocol registers the credit score transaction oracle on the blockchain

##### Storage
The application which determines the credit score needs to keep a record for all requests and responses (eg a transaction log)

##### Collation
Periodically, after the credit score performance window has elpased (say, 3 months - enough time to determine if the borrower has defaulted) for each set of transactions, the system running the credit risk model aggregates and collates performance metrics for the model.

Example of performance metrics could be:
* Gini of the score (How good the model is at separating goods from bads)
* Percentage of bad loans where a score over a certain threshold was determined
* Percentage of good loans where a score under a certain threshold was determined

##### Submission
These metrics can then be published to the blockchain, along with:
* a reference to the registration blockchain request
* a link to the raw data used to determine the performance metrics
* a hash of the performance metric data to ensure authenticity of the raw data

#### Aggregating the Data

As a time series of these performance metrics buids up, the blockchain meta data can be queried, summarised, aggregated and referenced to build some incredible potential into the ecosystem.


#### Conclusion and Extensions
The blockchain is a good fit for referencing persistant performance metrics via metadata.

Further, if the approach taken was generic enough - that is, a generic schema was created to register applications and another generic schema could be used to report performance metrics - then this method and reporting mechanism could be extended to any type of automated service which needs a mechanism to demonstrate its reliability or utility.

##### Competiton
What if we had an ecosystem that had many nodes competing to provide the best credit risk algorithm? If all of the nodes periodically reported their results, a natural competitive market place would form.

##### Reinforcement Learning
What if each node in the ecosystem could get better at predicting credit risk based on the raw data referenced in each of these reports? A natural reinforcement learning pattern would evolve.

##### AI Service Selection
What if Artificial Intelligent agents could use this performance meta data to determine which node in the ecosystem is best to use depending on a particular purpose or context? A natural AI choice model would start to develop.

### Authors

* Michael Hodder
* Thushare Dissanayake 
* Steven Pirois

### Cardano Proposal
The Cardano blockchain's capacity to store 16k worth of meta data in a single transaction makes it the ideal blockchain to carry out a proof-of-concept for the idea and is planned for a Catalyst Project Fund 5 Proposal

