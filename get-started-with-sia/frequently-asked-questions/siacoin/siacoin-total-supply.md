# What is the Siacoin total supply?

Siacoins are the utility token powering the Sia network and are intended to be used for the fulfillment of smart storage contracts on the decentralized network.

## What is the total supply?

**Unlimited** – there will never be a cap on the number of Siacoins generated. Humans produce so much data that it is effectively a limitless amount – and when Sia is the industry-standard storage layer of the Internet, the network will need lots of Siacoin to fulfill all those contracts. Additionally, the Proof of Burn mechanic (more on this later) functions to eliminate coins from the supply, so there needs to be a constant allowance of new Siacoins being created.

Additionally, if the block reward were to stop, miners would be dis-incentivized to continue providing their service to the network.

## How is Siacoin created?

Siacoins are created only as block rewards during mining on the Sia Proof of Work blockchain.

## Let's get a little more technical

The number of Siacoins created each block is (300,000 - height). This means that a block with a block height of 200,000 created 100,000 Siacoins (300,000 - 200,000). After height 270,000, the block reward won't get lower and all blocks will have a reward of 30,000 Siacoins.

By about July of 2020 when Sia hits the 270,000 block height, there will be about 44.55 billion (((300,000+30,000)/2)x270,000=44.55 billion) Siacoin's available in the market. From there, there will be about 1.57 billion (30,000x144x365=1.5678 billion) Siacoin created from the mining every year, forever.

## The Sia Foundation

In addition, Sia v1.5.4 introduced a network hardfork. The fork introduced the Sia Foundation, a new non-profit entity charged with supporting, developing, and promoting the Sia network. The Foundation changed the supply structure slightly as it is funded by an ongoing block subsidy of 30,000 Siacoins per block, paid out every 4,380 blocks. The hardfork also included an initial subsidy of approximately 1.57 billion Siacoins to help get the Foundation off the ground and fund initial development and activities.

This creates a small single year spike in the inflation schedule of a few percentage points, but that quickly reduces back to nearly pre-fork levels. You can see the entire inflation schedule at the fantastic community site [SiaStats](https://siastats.info/macroeconomics).

## Will the number of coins ever be reduced?

In the future, we'll be implementing a mechanic called Proof of Burn. Using this, sellers of storage on the network will burn coins to prove that they are real and have good intentions towards the network. It also offers another layer of network security. Here's more explanation from Sia lead dev David Vorick on the mechanic:

> Hosts burn coins by sending them to a provably unspendable address. Hosts are expected to burn a portion of their revenue (\~4%) as a demonstration that they are real. Renters will select hosts that have burned coins with a probability that grows in a linear relationship to the total number of coins burned. Therefore, a host that has burned 2x as many coins will be twice as likely to be selected as another host that has all other factors the same. This provides a very important defence against Sybil attacks. An attacker that is trying to manipulate a renter will need to have all of the excess redundancy of a file before being able to commit an attack. For a file with 3x redundancy, that means the attacker will need to get at least 2.1x of that redundancy, which means that the attacker will need to burn enough coins to look like 67% of the network. That entails burning 1.5x as many coins as the rest of the network has burned combined. Especially as the network grows and matures, collecting that many coins is going to be prohibitive. ([Source](https://forum.sia.tech/topic/108/how-sia-works))

## Isn't too many coins a bad thing?

Inflation is built-in with Siacoin to account for the many factors over time that will cause coins to disappear, such as the Proof of Burn mechanic, lost coins, and un-refunded collateral due to bad hosting. This inflation becomes very small over time, but still provides security to the network in the form of block rewards for the miners.

|                          | % Growth in total Siacoins |
| ------------------------ | -------------------------- |
| Year 1                   | 90                         |
| Year 2                   | 39                         |
| Year 3                   | 21                         |
| Year 4                   | 11.6                       |
| Year 5                   | 4.6                        |
| Year 6 (Foundation year) | 9.9                        |
| Year 7                   | 6.3                        |
| Year 8                   | 5.9                        |
| Year 9                   | 5.6                        |
| Year 10                  | 5.3                        |
| Year 20                  | 2.3                        |
