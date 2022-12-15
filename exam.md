Что такое виртуализация? Какие виды бывают, чем виртуализация отличается от контейнеризации и отличается ли?

virtualization is the provision of a set of computing resources or their logical association, abstracted from the hardware, 
through the separation of physical resources.
types of virtualizing :

1. Application Virtualization: 
Application virtualization refers to the process of deploying a computer application over a network (cloud). 
The deployed application is installed locally on the server, and when the user requests it,
the application instance is shown to the user. The user can then interact with that application as if it were installed on their system.
2. Network Virtualization: 
3. Desktop Virtualization: 
4. Server Virtualization:

hardware virtualization allows virtual computers to be independent and isolated from each other using software simulation of resources
(processor, memory, network, disk, etc.) of a physical server.

containerization is another type of virtualization.

![exam.png](https://github.com/blackberry22/2022_2023-introduction_to_distributed_technologies-k4111c-avdeeva_ml/blob/main/png.png)
containerization is more lightweight. applications inside containers are isolated from each other


- Алгоритмы консенсуса. PoW, PoS, DPoS и прочие.

POW proof of work
The essence of PoW is as follows: network nodes (miners) must solve complex mathematical problems (hash functions)
to confirm transactions and prevent other participants from spending the same coins twice.
The node that found the solution first is rewarded with new  coins.

POS proof of stake
The nodes of such a network are called validators, and their balance is called a stake. 
The more coins a node has in its wallet, the more likely it is to confirm a new block and receive a reward.

PoB
Proof-of-Burn (PoB) is alternative for Pos и Pow. 
The miner sends coins to a special address, to which it is impossible to pick up private keys. 
This means that coins from this wallet cannot be spent either - they are burned.
As a reward for this, the miner creates a new block and receives a reward for it in the form of new coins.
The more coins you burn, the higher the chances of getting a block reward.

DPos
Delegated Proof-of-Stake (Delegated Proof of Stake, DPoS) is a variation of the PoS algorithm. 
The difference is that coin holders pre-select a delegated validator.

LPos
Leased Proof-of-Stake (Leased Proof of Stake, LPoS) is another variation of the PoS algorithm. 
the difference is that everyone will receive the reward, even if they invested a small share

PoI
Proof-of-Importance (PoI) is another kind Pos.
The difference lies in the fact that not only the number of coins in staking is important for receiving a reward, but also the number of transactions.



