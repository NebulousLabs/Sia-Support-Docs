# How do I uninstall Sia-UI?

## Sorry to see you go!

If you're done with Sia-UI, you can uninstall easily.

There are two things you need to remove — the application, and the associated data folders.

{% hint style="info" %}
Deleting your data folders means Sia is gone - blockchain and everything. You can always [restore your wallet](how-to-restore-a-wallet-from-a-seed-in-sia-ui.md), though.
{% endhint %}

## Windows

Sia-UI on Windows has a built-in uninstaller that will do it for you. It can be found in the default install location - `user/AppData/Local/Programs/Sia-UI`

Using this will delete Sia and all the associated data folders.

You can also use Add or Remove Programs app from the System Settings. Uninstalling from here will leave the data folders intact.

## Mac and Linux

On Mac and Linux, you can just delete the app from your Applications folder. You'll then need to delete the data folders.

In Sia-UI version 1.4.0 and later, there's an easy way to find this. Click on the **Info** button at the top of Sia-UI.

![](../../.gitbook/assets/uninstall-1.png)

Then click on **Show Sia Data** or **Open Data Folder** \(version dependent\)**.**

![](../../.gitbook/assets/fork-2%20%281%29%20%282%29.png)

You'll be taken to your computer's `/sia` folder. Delete the parent folder to this, `/Sia-UI`.

## Data folder locations

If you're having trouble and can't get to your Sia data from Sia, they can also be found in the following locations:

**Windows:** `%UserProfile%\AppData\Roaming\Sia-UI\`

**Mac:** `~/Library/Application Support/Sia-UI/`

**Linux:** `~/.config/Sia-UI/`

