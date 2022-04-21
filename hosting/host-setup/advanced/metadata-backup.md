# Metadata Backup

Sia keeps data pertaining to your hosting operation in two places:

* The storage folders you're renting out, where uploaded renter data is stored
* Internal host metadata files that keep track of your contracts with renters and what's where in your storage folders

The first type of data, uploaded renter data, isn't very practical to back up unless you have additional hard drives lying around with a capacity equivalent to what you're selling on Sia. In that case, you'd be better off setting up a mirrored volume with multiple disks to prevent data loss if a drive fails.

The second type of data, internal host metadata, is equally important. Sia installations have been known to corrupt this data if a host does not shut down gracefully (i.e. a power outage or crash), and in rare cases, Sia itself can corrupt this data at no fault of the user. Without this metadata, your host cannot operate, and it is equivalent to losing all of your renter's data on all storage folders. This would result in the loss of all your risked collateral for your host. For this reason, you can see why it might be important to back the metadata up regularly. Even if you restore a copy of the metadata which is a few days old, you only stand to lose collateral for data uploaded to your host over those few days.

Host metadata is located in the `/host` folder in Sia's internal data files, which can be found in the Sia-UI by clicking the **About (i) icon > Open Data Folder** or in these locations:

* **Linux:** `$HOME/.config/Sia-UI/sia/`
* **Mac:** `$HOME/Library/Application Support/Sia-UI/sia/`
* **Windows:** `%APPDATA%\roaming\Sia-UI\sia\`

It is recommended to set up a backup schedule to regularly back up your `/host` folder so that you do not risk losing your hosting operation entirely in the event that your computer or Sia crashes or the data is randomly corrupted. You can do this by writing a simple backup script, by using built-in backup tools in [Windows](https://support.microsoft.com/en-us/help/17127/windows-back-up-restore) and [macOS](https://support.apple.com/mac-backup), or by using third-party tools in [Linux](https://www.tecmint.com/linux-system-backup-tools/).
