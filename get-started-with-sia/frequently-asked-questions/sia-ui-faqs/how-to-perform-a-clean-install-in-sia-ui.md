# How to perform a clean install in Sia-UI

Sia-UI is great for storing Siacoins, uploading data to the Sia network, or lending hard drive space for others to use.

It’s possible that you might have to perform a **clean install** of Sia-UI if you run into a problem that can’t be solved by other means.

During a clean install, two primary things are deleted:

* The Sia data folders
* The Sia-UI application, in certain circumstances

But don’t worry, restoring your balance of Siacoins is easy as long as you have your original wallet seed.

{% hint style="warning" %}
Performing a clean install will remove all your renting and hosting info as well. So if you've uploaded data to Sia or are hosting other's files, this will eliminate those contracts and should be used as a last resort. If you're not comfortable doing this, [contact support](mailto:hello@sia.tech) or [visit our Discord](https://discord.gg/sia) and we might be able to guide you through a specific fix.
{% endhint %}

## Your Sia wallet seed

When you first generated your wallet, you were given [a 29-word seed](../../../your-sia-wallet/wallet-setup/the-importance-of-your-seed.md). This seed is the master key for your Sia wallet and your Siacoin balance. Your Siacoins are always safe as long as you, and only you, have your seed.

The seed is required for this process, so make sure you have it handy. We’ll use it towards the end of the document.

If you don’t have your seed, do not proceed with these steps.

## Deleting the Sia data folders

Sia stores its data in specific folders. This includes things like the entire blockchain and your wallet info. We need to delete these, but first we need to find them. There are two easy ways to locate the folders.

{% hint style="warning" %}
**Note:** Quit Sia before deleting the data folders.
{% endhint %}

**Navigate directly to the location below, depending on your OS.**

Windows: `%UserProfile%\AppData\Roaming\Sia-UI\sia`

Linux: `~/.config/Sia-UI/sia/`

Mac: `~/Library/Application Support/Sia-UI/sia/`

**or…**

**Use Sia-UI**

If you've updated to v1.3.1 or later, you can easily find these folders by clicking **Show Sia Data** in the About tab.

If you're on 1.4.0 or later, use the Info button at the top of Sia.

![](<../../../.gitbook/assets/fork-2 (1) (3) (3) (1).png>)

Then click **Show Sia Data.**

Once you find the `/sia` folder:

![](<../../../.gitbook/assets/fork-3 (1) (2) (2).png>)

Delete it.

Reboot your computer after deleting this folder.

## Deleting and re-downloading Sia-UI

{% hint style="warning" %}
While not required, deleting and re-downloading the application files will ensure you are on the latest version. If you're sure you're already [on the latest version](https://sia.tech/get-started), you can skip this step.
{% endhint %}

### **Prior to 1.4.0**

Sia-UI installed where it was downloaded, unless moved. For Windows and Linux, you’ll see a folder that is named something like:

`Sia-UI-v1.3.2-win32-x64`

On macOS, you’ll simply see the Sia-UI icon.

Drag the folder containing the Sia-UI app into the trash if you wish to.

### **1.4.0 and later**

On macOS, Sia-UI can be found in the Applications folder. Trash it.

On Windows and Linux, you can run the uninstaller found with the Program file - `user/AppData/Local/Programs/Sia-UI/` on Windows.

[Learn how to download and install Sia-UI\*\*.\*\*](how-to-download-and-install-sia-ui.md)\*\*\*\*

## Setting Sia-UI up again

At this point, you’ve deleted the Sia data folders and made sure you’re updated to the latest version of Sia-UI. Now you’ll need to restore your seed to make sure your Siacoin balance is restored.

When you open Sia-UI, choose **Restore from seed**. [Learn how to do that here](how-to-restore-a-wallet-from-a-seed-in-sia-ui.md) if you need help.

{% hint style="info" %}
After restoring Sia from your seed and resyncing, it might take your balance up to an hour to re-appear in the wallet as Sia performs more actions in the background.
{% endhint %}

Sia-UI will then scan the blockchain for any Siacoin associated with your seed. This may take a while, but once it’s done your Wallet will show your previous Siacoin balance.

## Questions?

If you have any issues with this process, let us know! Send an email to [hello@sia.tech](mailto:hello@sia.tech) and we’ll get back to you as soon as we can.
