# What is the Siacoin total supply?

Siacoins are the utility token powering the Sia network and are intended to be used for the fulfillment of smart storage contracts on the decentralized network.

## So what's the total supply?

**Unlimited** – there will never be a cap on the number of Siacoins generated. Humans produce so much data that it is effectively a limitless amount – and when Sia is the industry-standard storage layer of the Internet, we'll need lots of Siacoins to fulfill all those contracts. Additionally, the Proof of Burn mechanic \(more on this later\) functions to eliminate coins from the supply, so there needs to be a constant allowance of new Siacoins being created. As of July 2018, about 35.4 billion coins have been created, but the number of new coins introduced will slow as each new block is produced. By 2020, we should have about 45 billion coins in circulation.

Additionally, if the block reward were to stop miners would be disincentivized to continue providing their service to the network.

## How are Siacoins created?

Siacoins are created only as block rewards during mining on the Sia Proof of Work blockchain.

## Let's get a little more technical

The number of Siacoins created each block is \(300,000 - height\). This means that a block with a block height of 165,000 created 135,000 Siacoins \(300,000 - 165,000\). After height 270,000, the block reward won't get lower and all blocks will have a reward of 30,000 Siacoins.

By about July of 2020 when Sia hits the 270,000 block height, there will be about 44.55 billion \(\(\(300,000+30,000\)/2\)x270,000=44.55 billion\) Siacoins available in the market. From there, there will be about 1.57 billion \(30,000x144x365=1.5678 billion\) Siacoins created from the mining every year, forever. For example, by March of 2021, there will be about 45.6 billion Siacoins available. By March of 2026, there will be about 53.5 billion Siacoins created.

## Will the number of coins ever be reduced?

In the future, we'll be implementing a mechanic called Proof of Burn. Using this, sellers of storage on the network will burn coins to prove that they are real and have good intentions towards the network. It also offers another layer of network security. Here's more explanation from Sia lead dev David Vorick on the mechanic:

> Hosts burn coins by sending them to a provably unspendable address. Hosts are expected to burn a portion of their revenue \(~4%\) as a demonstration that they are real. Renters will select hosts that have burned coins with a probability that grows in a linear relationship to the total number of coins burned. Therefore, a host that has burned 2x as many coins will be twice as likely to be selected as another host that has all other factors the same. This provides a very important defence against Sybil attacks. An attacker that is trying to manipulate a renter will need to have all of the excess redundancy of a file before being able to commit an attack. For a file with 3x redundancy, that means the attacker will need to get at least 2.1x of that redundancy, which means that the attacker will need to burn enough coins to look like 67% of the network. That entails burning 1.5x as many coins as the rest of the network has burned combined. Especially as the network grows and matures, collecting that many coins is going to be prohibitive. \([Source](https://forum.sia.tech/topic/108/how-sia-works)\)

## Isn't too many coins a bad thing?

We've built inflation in with Siacoin to account for the many factors over time that will cause coins to disappear, such as the Proof of Burn mechanic, lost coins, and un-refunded collateral due to bad hosting. This inflation becomes very small over time, but still provides security to the network in the form of block rewards for the miners.

|  | % Growth in total Siacoins |
| :--- | :--- |
| Year 1 | 90 |
| Year 2 | 39 |
| Year 3 | 21 |
| Year 4 | 11.4 |
| Year 5 | 4.4 |
| Year 8 | 3.2 |
| Year 20 | 2.3 |

