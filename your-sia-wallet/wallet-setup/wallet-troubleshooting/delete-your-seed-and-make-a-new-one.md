# Delete your seed and make a new one

[Your seed is incredibly important](../the-importance-of-your-seed.md), but there might be a time where you want to initialize your wallet with a new seed. Maybe you lost your old one, or maybe you're making a new wallet for a new purpose. Either way, we've got you covered.

## Things you'll need

* Sia installed on your computer
* A Sia wallet set up
* Siacoins, the cryptocurrency used to buy and sell storage

{% hint style="warning" %}
This process generates a new wallet with a new Sia seed. This is not recommended if you currently have Siacoins in your wallet, unless you've already forgotten your Sia seed. Any Siacoins in your current wallet will no longer be accessible unless you have your previous seed and restore from it.
{% endhint %}

## Deleting your wallet and starting over

1. Go to the Terminal tab
2. Type: `wallet init --force`

{% hint style="warning" %}
There are two dashes before the word `force`.
{% endhint %}

This will immediately erase your old wallet and create a new one. You will also see your new seed instantly in the Terminal window. [Make sure you safely store your new seed](../the-importance-of-your-seed.md).

Go back to the Wallet tab, and use the new seed to unlock your wallet. Since this is a brand new wallet, your Siacoin balance will be 0 SC. Enjoy your new wallet!

