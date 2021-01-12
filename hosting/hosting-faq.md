# Hosting FAQ

## How do I see advanced host stats?

Type `host -v` to see complete stats. If you are in Sia-UI, open the Terminal with `>` at the top of the app.

## Can I run my host on two different computers at the same time?

It is not recommended to keep the same wallet and installation running in two different computers while hosting, as it could lead to data loss and loss of Siacoins.

## What happens if my Sia wallet locks?

Your host will appear as offline. Reference [this article](../your-sia-wallet/for-advanced-users/how-to-automatically-restart-and-unlock-sia.md) to keep it automatically unlocked.

## What happens if my host computer shuts off?

Your host will appear as offline. Reference [this article](../your-sia-wallet/for-advanced-users/how-to-automatically-restart-and-unlock-sia.md) to reboot it automatically.

## Can I change the folder that Sia uses for storage?

The easiest way to do so is to add the new storage folder in the Host tab, wait for it to show as part of the "Total Storage", and then remove the old storage folder. Sia should move any stored data from the old folder to the new ones once you remove the old, but this process might take a while depending on the size of the old folder and Sia will be unresponsive during the move. 

It may be easier to resize your old storage folders down incrementally after adding the new folder, which will cause Sia to move data from the old folder to the new folder with each resize. If you do this repeatedly in small pieces \(e.g. 50 or 100 GB at at time\), Sia is less likely to lock up or crash in the process.

## Can I move my Sia host to a new computer?

{% hint style="warning" %}
Moving your host isn't recommended. It's a tough process and doesn't have a 100% success rate. Doing so might break your host completely.
{% endhint %}

Both the installation folder and the Sia-UI folders are required to be transferred, on top of preserving the recovery seed. 

### Installation locations

| Operating System | Data Directory |
| :--- | :--- |
| Linux | `$HOME/.config/Sia-UI` |
| Windows | `Users\\appdata\roaming\Sia-UI\` |
| macOS | `$HOME/Library/Application Support/Sia-UI/` |



1. Install Sia on the new system, and start it once to generate the internal data files. Then close Sia completely \(right click the icon in the system tray and select **Quit**\) - you don't need to wait for it to synchronize or set up your wallet. 
2. Open Sia's internal data files \(**About \(i\) icon &gt; Open Data Folder**\) on the old host, then close Sia completely. 
3. Move the host storage folders and their contents from the old host to the new host. Obviously, this must be done such that the new storage locations are equal to or larger in size than the old storage locations in order to fit the data. Additionally, the hosting folders need to be accessible in the new machine in the exact same path. For instance, if the host was hosting files in a folder located on D:/Misc/Sia, the new computer will need to have a drive called “D:” and the hosting files placed exactly in /Misc/Sia. **This last requirement makes impossible to transfer a host from the OS of one family to another OS of a different family** \(for example, from Linux to Windows\), as the drive routes are different.
4. Move all of Sia's internal data files from the old host to the new host at the locations found above.
5. In the internal data files on the new host, edit the `host\contractmanager\contractmanager.json` and `host\contractmanager\contractmanager.wal` files using a text editor, look for your old storage folder paths, and change them to your corresponding new storage folder paths. 
6. Start Sia on the new host.

Sia may take a while to start while it tries to figure out the changes. It may display a message while it does, or it may just sit. Your wallet and host data should be transferred over, though, and hopefully everything will be in order once Sia finishes loading and you unlock your wallet.

## How do I shut my Sia host down?

You can stop accepting new contracts by turning off the green slider next to "Announce Host" in the Host tab. However, this only stops new contracts - you still need to finish out current contracts. Default host settings use a ~26 week contract length and renters use a default ~3 month length, so you should switch new contracts off at least 6 months prior to when you'd like to shut down your host. Otherwise, you may still have contracts active which you could lose collateral for if you take your host offline before they complete. 

Once you've switched off new contracts, you can track the progress of any current contracts by typing `host` into the Terminal `>` at the top of Sia-UI every week or so. Once all collateral is freed \(no collateral shows as locked or risked\), you can safely take your host offline. You can also use a tool like the [SiaStats Host Monitor](https://siastats.info/hosts) by searching for your host's IP address or domain name. While this service doesn't show contract details, once your host's used storage drops to zero all contracts should be completed.

## Should I backup my Sia host metadata?

The Sia client maintains additional information on your contracts as a host and your renters' files in an internal location. This information is known as host metadata, and is required in order to provide your renters with access to their data on the Sia cloud storage network. Without it, it's like losing renter data - you'd have no way to know which data belongs to who in your host storage folders.

See more about backing up in [How to host on Sia](how-to-host-on-sia.md#set-up-host-metadata-backups).

## **My public IP address is dynamic, and my Sia host goes Offline when it changes.**

You can use a free Dynamic DNS \(DDNS\) service. DDNS involves registering for and receiving your own address, like "mysiahost.ddns.net", in combination with running a small program or script on your computer. Some routers also have built-in DDNS support for certain providers. When your public IP address changes, the DDNS program detects the change and configures your DDNS address with the new IP. This way, you can announce your Sia host using your DDNS address, and it should stay Online even with public IP changes. 

There are a number of free DDNS providers which can be found by searching for DDNS using your favorite search engine. One popular free option is [NoIP.com](https://www.noip.com/). 

## My Sia host is becoming unresponsive for several minutes to several hours at a time.

Your host can become unresponsive if you add or change storage directories - especially on Windows, as Windows preallocates files so adding a drive with several terabytes of space will take as long as it takes to write to the entire drive, which is usually about 2-3 hours per TB. Your host can also become unresponsive during initial startup if it has to process or rebuild certain internal data files, or if it is syncing because it hasn't been online for a while or because the consensus data was removed or bootstrapped. 

In Sia v1.4.x and v1.5.0, there is a known issue regarding hosts becoming unresponsive, causing [SiaStats Host Monitor](https://siastats.info/hosts) benchmark failures and other issues. The SiaStats benchmark failures usually mention an I/O timeout, and several failures may occur in a row. There's not much you can do about this issue currently, but the Sia team is aware of the issue and has attempted a fix for v1.5.1. As this version has just been released in November 2020, it may take a few months to see if the resolution is effective.

## Why are there multiple small deductions taken from my wallet?

If you don't use DDNS, you probably have a dynamic IP from your ISP that changes from time to time. When this happens, your Sia host re-announces itself and this becomes a transaction in your wallet.

You also might see multiple transactions form as collateral gets tied up in contracts. This is totally normal.

