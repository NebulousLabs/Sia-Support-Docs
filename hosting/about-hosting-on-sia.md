---
description: >-
  Learn about the concepts and terms you'll need to be familiar with to host on
  the Sia network.
---

# About hosting on Sia

**Hosting** means you are contributing your excess storage space to the Sia network. You're helping to keep data where it belongs – safely in the hands of those who uploaded it, the **renters**.

You also earn Siacoins, the cryptocurrency that powers the Sia network. Siacoins can be used to purchase your own storage space, or converted to other cryptocurrency or fiat on crypto exchanges.

Hosts are a critical part of the ecosystem. You are contributing to the decentralized network that is the heart of Sia. Hosting is also more technical a process than renting, and while anyone can fairly easily set it up, there's a lot you'll want to know to maximize your setup.

## Things you'll need

Not meeting these requirements can have a range of effects: you may be unable to host, you may not receive any storage contracts from renters, or you may even risk losing your own Siacoins as a penalty. Hosting is a serious commitment. If you're going to do it, do it right.

* **A reliable and stable setup:** You need a computer, internet connection, and electricity that you can trust. Hosts are required to be online nearly 100% of the time or face financial penalties.
* **Sia Prerequisites:** Make sure your computer meets the Sia requirements
  * CPU: Sia does not require special CPU considerations
  * RAM: 8 GB recommended
  * SSD: 40 GB recommended (keep an eye on your consensus size!)
  * Create a Sia wallet
  * [Get Siacoins](../get-started-with-sia/how-to-buy-siacoins.md)
* **Storage space:** Spare hard drive space to rent out, ideally greater than 4 TB.

## Pricing

As a host, you set your own prices. There's a lot of specific price points you can control:

* **Storage Price:** The base price for your storage, per TB/month.
* **Contract Fees:** A small, one-time fee per contract to cover network transaction costs.
* **Upload/Download Bandwidth Price:** Your price for upload or download bandwidth to and from your host, per TB.
* **Collateral:** How many Siacoins you're willing to lose if you don't fulfill the rental contract, per TB.

## **About Contracts**

Storage contracts are one of the most important features of the Sia network. They are what allow the entire Sia ecosystem to work in a trustless way – they form blockchain-enforced contracts between you and the people who rent your storage space that are automatically fulfilled.

## Earn Siacoins

As a host, you're part of a marketplace where you compete with other hosts for renter contracts. Competition should drive prices down, and demand should drive prices up. The goal is a market where people can upload their data with maximum security, minimum cost, and at fair rates that provide revenue to the hosts.

## Fees

As a host, you earn Siacoin for the storage space that you sell. But in order to create additional incentive for hosts to be good hosts and sustain a reliable network, you also put up collateral.

* **Collateral** – An amount of Siacoins that you're willing to lose if you aren't a good host.

Having collateral incentivizes hosts to be online and to keep their renter data intact. Hosts that go offline or lose data lose their collateral, and hosts that stay online and keep data safe get their collateral back.

## Host Scoring

One of the most important factors that determine how you'll fair as a host is your host score. This is based on a number of metrics – some that you can directly affect, some that improve or diminish over time based on your performance.

Sia is a decentralized network - the code to evaluate these scoring metrics is contained within each renter's Sia instance. For that reason, each Sia renter you encounter builds their own host score for your host, so your host may be scored differently among different renters. Your host does not have one single overall score across the Sia network, but instead many scores with many renters based on the metrics described below. Any website or service showing your Sia host rank is showing that particular source's view of your host, which may be different from what a renter comes up with.

### Specific Metrics

{% tabs %}
{% tab title="Host Uptime" %}
Host uptime is an incredibly important metric. You need to be online when people try to get their data, and since that might be anytime, you should be online all the time. You're allowed a small amount of downtime in order to address minor maintenance issues like restarting for updates, which amounts to approximately 14 hours per month.

In general, you should plan for your hosting computer to be turned on and online 24/7. If you can't commit to this, you shouldn't try to host on the Sia network.

{% hint style="danger" %}
Warning: If you go offline for too long (less than 95% uptime) or lose renter data (by deleting it or experiencing a hardware failure), you can lose money by losing your collateral for active contracts. You can also become responsible for SiaFund fees for each contract.
{% endhint %}

Below are the exact amounts that your score will change based on your uptime percentage. Greater than 98% uptime results in no penalty, which is the 14 hours a month explained above (2% of 720 hours in a month = 14 hours).

| Uptime | Score Multiplier | % Reduction in Score |
| ------ | ---------------- | -------------------- |
| 100%   | 1.0              | None                 |
| 98%    | 1.0              | None                 |
| 95%    | .91              | -10%                 |
| 90%    | .51              | -50%                 |
| 85%    | .16              | -85%                 |
| 80%    | .03              | -97%                 |

There are more values we could include in this table, but there's not much point. If you can't maintain a minimum of 95% uptime, don't host.
{% endtab %}

{% tab title="Storage Pricing" %}
The price you set for your storage as a host is one of the biggest ways you can affect your host score. You want to set a price that's competitive, but that will still result in a reasonable amount of income for the space you offer. In general, the higher you price your storage, the lower your host score will be. Your host score will increase by a factor of 16 every time you cut your storage price in half. Decreasing your storage cost by even a small amount will have an impact on your score.

There are a number of other pricing factors you have to take into consideration as a host:

* A **Contract Fee** is a one-time fee a renter pays in order to initiate a storage contract with you. It's intended to cover transaction fees on the Sia network related to the creation of the contract and receiving payments as a host. This is normally set for you automatically, but it can be changed via the Terminal/command line. If you change it, you generally don't want to set this more than about 5 SC, as these costs are very low.
* **Bandwidth Price** can be set on a basis of SC per Terabyte transferred to/from your host. One price can be set for both upload and download bandwidth via the Sia-UI, or different upload/download prices can be set individually via the Terminal/command line. It's suggested that you price your upload and download bandwidth in relation to your internet connection capabilities. If you have a fast connection such as gigabit fiber, you can price these items very low because a user transferring several Terabytes doesn't impact you very much. If you have a slow connection or data caps, you may want to consider a higher bandwidth price, though this may deter renters.
* Fees related to **Sector Access** and **RPC** are protections against malicious renters which may be trying to abuse hosts by accessing host resources without paying for uploading or downloading. These fees are capped at 1% of the cost to download a file, but some services which use Sia for storage may ignore your host if you set these fees to anything.
{% endtab %}

{% tab title="Collateral" %}
This is how many Siacoins you're willing to lose if you don't fulfill the rental contract, per TB. It's a guarantee to your renters that you will be online through the storage contract, and that you'll have their data intact at the end of the contract. As a host, this is why you need Siacoins to start hosting. If you go offline for too long or lose renter data, you risk losing your collateral.

You should normally set your collateral to around **2-3x your base storage price** as a starting point in order to maximize your host score in this area. For example, if you've priced your storage at 50 SC/TB, you should set your collateral at 100-150 SC/TB.

* If you set your collateral **too low**, your host score will be reduced, because renters will have no reason to trust you as a host if you have little or nothing to lose by going offline.
* If you set your collateral **too high**, this can also decrease your host score. Renters pay a fee based on a percentage of your collateral that goes towards [Siafunds](../siafunds/what-are-siafunds.md) - if your collateral is set very high, the fee a renter pays as a result will be very high, which can decrease your host score.

**Monitoring Your Collateral**

You can get information on your collateral by typing `host -v` into the Terminal. This will show you a few things:

* All of your current host settings, as well as details on contracts and expected revenue
* **Locked Collateral** - this is the total collateral that's been reserved for contracts that have been created with your host. This amount has been removed from your wallet and is inaccessible to you.
* **Risked Collateral** - this is collateral for data that has actually been uploaded to your host, so you stand to lose it if your host goes offline or loses the data. This amount is a subset of Locked Collateral.
* **Lost Collateral** - this is collateral you've lost because you weren't online when a storage proof was due to be submitted, or because you lost a renter's data.

With this information, you can determine how much collateral has been tied up in the process of hosting, and make adjustments to your collateral settings accordingly if necessary.
{% endtab %}

{% tab title="Storage Remaining" %}
The more free space you have, the more attractive you are to people who want to store things. It makes your host less likely to run out of space later. The host scoring system takes this into account.

Again, each renter determines their score for your host. The more available space you have when a host forms contracts with you, the more reliable you look, and the higher this piece of the scoring will be.
{% endtab %}

{% tab title="Host Age" %}
History matters. The longer you've been around, the more reliable you look to host scoring. There's a penalty applied to new hosts. How to beat that penalty you ask? Keep your host online.

Once you've been online for about twelve weeks, about half of the default contract length, your penalty disappears!

| Host Age (Blocks) | Host Age (Days) | Score Multiplier | % Reduction in Score |
| ----------------- | --------------- | ---------------- | -------------------- |
| 12,001            | 83.5            | 1.0              | 0%                   |
| 12,000            | 83              | .66667           | -33.33%              |
| 6,000             | 41              | .33333           | -66.67%              |
| 4,000             | 28              | .16667           | -83.33%              |
| 2,000             | 14              | .08333           | -91.667%             |
| 1,000             | 7               | .02778           | -97.222%             |
| 576               | 4               | .009259          | -99.0741%            |
| 288               | 2               | .0030864         | -99.69136%           |
| 144               | 1               | .0010288         | -99.89712%           |
{% endtab %}

{% tab title="Interaction Weight" %}
Interaction weight is a metric measured between your host and each renter on the Sia network. For example, if a renter tries to contact your host and you're frequently offline or don't have your wallet unlocked (a pre-requisite to your host being online), your interaction score will decrease with that renter. Again, this score is unique for each renter you encounter - it will be different for each individual renter on the Sia network.

Keeping your host online and your wallet unlocked while hosting will keep this score as high as possible.
{% endtab %}

{% tab title="Version Adjustment" %}
Stay updated. Your host score drops if you're not running the latest version of the Sia client. Sia is constantly under development, and bug fixes and new features are pushed out on a somewhat regular basis. If you're running an older version of the client, your renters may not be able to take advantage of all the latest features of Sia until you upgrade.
{% endtab %}
{% endtabs %}

## Third-Party Host Scoring

We have an incredible community building on Sia. Third-party sites can develop their own methods for scoring hosts based on various metrics. For example, SiaStats has developed a [Host Monitor](https://siastats.info/hosts) which evaluates hosts on pricing relative to other hosts, and even evaluates host performance regularly by forming contracts with every host it can in order to test bandwidth and latency. SiaStats even has great visualization for each host to make judging their metrics easier.

These benchmarks are different from the core Sia protocol, but are still useful, and may be used to help monitor and improve your own host over time.

Once you've started hosting, you'll probably want to keep an eye on your host score and see how you might be able to improve your host ranking.

## Units and Conversions

*   **Currency units:**

    * 1 MS = 1,000,000 SC
    * 1 KS = 1,000 SC
    * 1 mS = 0.001 SC
    * 1 uS = 0.000,001
    * 1 nS = 0.000,000,001 SC
    * 1 H = 1e-24 SC _(The smallest currency unit of Siacoin)_

    __
* **Duration Units:**
  * 1 block (b) = \~10 minutes
  * 1 hour (h) = \~6 blocks
  * 1 day (d) = 144 blocks
  * 1 week (w) = 1008 blocks
