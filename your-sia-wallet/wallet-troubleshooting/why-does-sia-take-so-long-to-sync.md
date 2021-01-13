# Why does Sia take so long to sync?

Sia needs to download an entire copy of the blockchain to maintain the integrity of the network’s transactions. This is a critical step and allows the decentralized network to function correctly.

{% hint style="info" %}
As of January 2021, the blockchain is a little over 24 GB, and grows about 1 GB every two months.
{% endhint %}

On newer solid state drives \(SSDs\) this can take several hours. On standard hard disk drives \(HDDs\) this process can take over a day.

This is totally normal, but we are working to decrease this initial sync time in future releases.

Troubleshooting steps can be taken to address this. If the initial sync appears to be frozen:

* Give it time. Often, the sync will resume on its own.
* Quit Sia and restart your computer.

Some sites will allow you to "bootstrap" the blockchain, by giving you a mostly complete version to download and drop in the appropriate folder on your computer. As this requires trusting the party you download it from, we always recommend letting Sia sync itself.

