# Wallet overview

Sia-UI and `siac` are the best places to store your Siacoins. They're also the only official apps made by the developers of the Sia network.

[Download Sia.](http://sia.tech/get-started)

Sia-UI allows you to store Siacoins in a secure wallet, or rent or sell storage space on the Sia network. `siac` is a command-line client for Sia, and is only recommended for advanced users.

[Download Sia.](http://sia.tech/get-started)

Your wallet gives you access to see your balance and transaction history, and the ability to send or receive Siacoin to any other Sia user.

Here's what a typical Sia-UI wallet looks like.

![](../.gitbook/assets/send-1.png)

Your **balance** is at the top. This is the current amount of Siacoins in your wallet, and can fluctuate quite a bit depending on how you use Sia. If you own any Siafunds, they show up next to this.

## The Transactions tab

Every transaction is broken into a few categories - the Amount, Transaction ID, Time, TX Type, and Status.

![In this example, you can see three transactions.](../.gitbook/assets/wallet-1.png)

{% tabs %}
{% tab title="Amount" %}
The amount of Siacoins entering or leaving your wallet.
{% endtab %}

{% tab title="Transaction ID" %}
Use these to look up your transaction in a Sia blockchain explorer. The transaction IDs are shortened, but you can hover over them to see the full ID. You can also copy and paste while you do this.
{% endtab %}

{% tab title="Time" %}
The date and time the transaction was made.
{% endtab %}

{% tab title="TX Type" %}
The type of transaction that took place. Possible values are Siacoin, Siafund, Contract, Proof, Revision, Block, Defrag, and Setup.
{% endtab %}

{% tab title="Status" %}
While your transaction is confirming, you'll see 0/6, then 1/6, and so on. Once you reach six confirmations, you'll see the green checkmark like above and your transaction is considered confirmed.
{% endtab %}
{% endtabs %}

Near the upper right corner, you'll see a button that says `More`. Click on this to get some additional wallet options.

![](../.gitbook/assets/wallet-2%20%282%29%20%283%29%20%281%29.png)

**View Seed** shows you your seed in case you need to see it again.

**Change Password** lets you set a custom password for your wallet, instead of using your Sia seed. [Learn about the pros and cons of a custom password.](how-do-i-change-my-sia-wallet-password.md)

## Be careful

There are plenty of scams in the cryptocurrency space. Make sure the only software wallet you use to store your Siacoin is the official app downloaded from that link above or [our GitLab page.](https://gitlab.com/NebulousLabs/Sia-UI/tags) There are some other great recommendations you can get from [our community](https://discord.gg/sia), but we can't guarantee that any other software wallet will safely store your Siacoins.

