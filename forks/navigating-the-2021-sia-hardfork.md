# Navigating the 2021 Sia hardfork

The Sia network is hardforking to implement the Sia Foundation: a new non-profit entity that builds and supports distributed cloud storage infrastructure, with a specific focus on the Sia storage platform. 

{% hint style="info" %}
The hardfork requires v1.5.4 of Sia.
{% endhint %}

{% hint style="warning" %}
1.5.4 is necessary to spend coins, receive coins, rent, or host after the fork. If you don't upgrade in time, you will brick your consensus.db file. This is the file that syncs the blockchain to your computer, and you will have to completely re-sync it.
{% endhint %}

This guide is strictly practical. If you'd like to learn more about the Foundation's proposal and discussion that led to its acceptance, check these links.

[The Sia Foundation proposal](https://www.reddit.com/r/siacoin/comments/iox6ly/proposal_the_sia_foundation/)

[The Sia forums](https://forum.sia.tech)

And you can also reference our [Sia API docs](https://sia.tech/docs/) for technical documentation on Sia and updating via CLI.

## Timeline

Sia v1.5.4 will be released by the second week of January. The fork will be implemented at a block height of 298,000, which is expected to be on February 3rd. **Be updated by this date.**

## If you rent or host on Sia

Renters and hosts need to upgrade to v1.5.4 by February 3rd.

Doing so ensures that renters will continue to upload data to hosts also on the new fork. Hosts who fail to upgrade in time will no longer form contracts with renters who upgrade. Long story short, you need to be on the same version as everyone else or you aren't part of the same network.

## If you mine Siacoin

Nothing will change. You can check in with your mining pool to make sure they've updated, but we've received confirmation from the following pools that they will update: Luxor, SiaMining, f2pool, Dxpool.

## If you're an exchange that trades Siacoin

Exchanges need to upgrade to v1.5.4 by February 1st at the latest. Due to the volume of users you serve, you should leave time for a proper upgrade. Once you do, your exchange will be able to support the fork once it takes effect.

{% hint style="warning" %}
Transactions created before the fork block but not confirmed yet will not be valid anymore after the fork block. We recommend that you pause withdrawals for the 6 hours leading up to the fork, and the 2 hours following the fork. This will prevent you from having your transactions become invalid.
{% endhint %}

Reference our [Sia API docs](https://sia.tech/docs/) if necessary. Updating your Sia wallet can be as simple as running `siac update`, or using the following API command, but only you know your Sia wallet setup.

```text
curl -A "Sia-Agent" -u "":<apipassword> "localhost:9980/daemon/update"
```

## Info for Siacoin holders

### For users that store in our official wallet

Siacoin holders need to upgrade to v1.5.4 by February 3rd. There are two versions of Sia: Sia-UI for most users, and siac for advanced users. When you store them here, you control the private keys. When the hardfork hits at block 298,000, your updated 1.5.4 version of Sia will instantly give you access to the new chain, and all of your Siacoins will be available to you.

{% hint style="warning" %}
Transactions created before the fork block but not confirmed yet will not be valid anymore after the fork block. We recommend that you don't send any transactions for the 6 hours leading up to the fork, and the 2 hours following the fork. This will prevent you from having your transactions become invalid.
{% endhint %}

[Learn how to download and install Sia-UI](https://support.sia.tech/article/lsk44kqzx2-sia-ui-how-to-download-and-install)

[Learn how to create a new wallet in Sia-UI](https://support.sia.tech/article/1ydsw46thr-sia-ui-creating-a-new-wallet)

[Download siac from our site \(for advanced users\)](http://sia.tech/get-started)

{% hint style="warning" %}
1.5.4 is necessary to spend coins, receive coins, rent, or host after the fork. If you don't upgrade in time, you will brick your consensus.db file. This is the file that syncs the blockchain to your computer, and you will have to completely re-sync it.
{% endhint %}

### For users that store Siacoins on an exchange

When an exchange updates their wallet, you'll now have the same amount of coins on the new Sia chain. These coins are usable to trade with exchanges once they upgrade, and to buy storage from hosts who also use the new chain.

## Exchange Support

Here's a list of all the exchanges that have had Siacoin volume over the past couple of months, according to CoinMarketCap. Please keep in mind that while we've confirmed with these exchanges that they are supporting the 1.5.4 Sia fork, final implementation is up to their teams. You should reach out to your exchanges to confirm.

The second column will have three values:

* Informed, meaning we have passed the fork information along to the exchange
* Confirmed, meaning the exchange has agreed to update
* Complete, meaning the exchange has already updated

| Exchange | Updating to 1.5.4 |
| :--- | :--- |
| Binance | Confirmed |
| BiOne | Informed |
| Bittrex | Confirmed |
| Digifinex | Informed |
| HitBTC | Informed |
| Huobi Global | Confirmed |
| Kraken | Confirmed |
| Lbank | Informed |
| OKex | Confirmed |
| Poloniex | Informed |
| Upbit | Confirmed |
| VCC | Informed |

## More questions?

Let us know! [Send us an email](mailto:hello@sia.tech), or [reach out to the community on Discord](https://discord.gg/sia).

