---
description: ...and now you have to resync your Sia wallet.
---

# So, you didn't update in time for the fork

![](../.gitbook/assets/cap.jpg)

On February 3rd, 2021 at block 298,000, the Sia network hardforked to implement the Sia Foundation: a new non-profit entity that builds and supports distributed cloud storage infrastructure, with a specific focus on the Sia storage platform.

It's a great thing! But here you are, and you didn't update in time. Maybe you never even updated from the 2018 fork! You can't rent storage space, host, or send SC to friends or exchanges. For most people who updated ahead of time, it was a simple matter of [downloading the latest version and installing it](../your-sia-wallet/sia-ui-faqs/how-to-download-and-install-sia-ui.md).

Not you though, something went \(or is going\) wrong. It might be that:

* Sia is not syncing
* Sia is not forming contracts
* Your transactions are not broadcasting
* Your transactions are broadcasting, but are not being received at your destination
* Sia says you are not up to date
* Sia says you are up to date, but you know you're not \(sometimes happens with very old versions when checking via the siac `update` command\)

Many of these issues can manifest when you're [on the wrong chain](using-the-wrong-chain-after-a-fork.md).

## How to resync

You're on the wrong Sia chain if you're not on 1.5.4. Type `./siac version` in your CLI, or use the ⓘ in the top nav bar of Sia-UI to check.

The most effective way to resync is to perform a clean install. The process requires:

* your Sia seed
* deleting the Sia data folders
* deleting and re-downloading Sia
* setting Sia up again

It's a bit of a long process, mostly because Sia will re-download the consensus blockchain file. But resyncing is something you'll need to do anyway, and a clean install works 100% of the time. Use [this guide](../your-sia-wallet/sia-ui-faqs/how-to-perform-a-clean-install-in-sia-ui.md) for a detailed walkthrough of these steps.

