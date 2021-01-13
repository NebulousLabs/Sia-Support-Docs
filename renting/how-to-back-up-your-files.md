# How to back up and restore your files

Back in version 1.4.1 of Sia, we introduced seed-based file recovery. This feature lets you create a metadata snapshot of your current files, which is stored on the Sia network and linked to your seed. As long as your contracts are active, you can then use this backup to restore your files at any future date and from any \(preferably empty\) Sia node.

When your files are on Sia, they're on the most private, secure network in the world. With seed-based file recovery, they're now also recoverable anywhere, anytime.

File backups are meant to be used to restore files in a brand new instance of Sia, but can also be accessed in your current Sia node.

{% hint style="info" %}
Your contracts need to be active, which means Sia isn't totally fire-and-forget just yet. You still need to boot Sia up every few weeks to renew your allowance and contracts.
{% endhint %}

## Back up your files in Sia-UI

### **Create your backup**

After you've [uploaded files to Sia](how-to-rent-storage-on-sia.md), go to the Rent tab and click **More**. You've got two new options, Backup Files and Restore Files. Click **Backup Files**.

![](../.gitbook/assets/backup-1.png)

Name your backup file, and click **Start Backup**.

![](../.gitbook/assets/backup-2.png)

Sia now takes a snapshot of your current files and stores it in the cloud. You'll see a notification pop up in the upper right corner to let you know.

![](../.gitbook/assets/backup-3.png)

### View your backups

Just created your first backup? You can verify that Sia's got it.

Click on **More** and go to **Restore Files** to see your available backups. If any backups are currently being taken, you'll see a green progress bar. It can take a while for a backup to complete, so check back later if it's not done. Completed backups show with the date they were taken, and an option to restore them.

![](../.gitbook/assets/backup-4.png)

### Restore your backup

File backups are typically used to restore your files in a new instance of Sia if the one you were previously using had issues. If you haven't set an allowance or uploaded files in Sia yet, you can choose **Restore Files** as soon as you go to the Rent tab.

![](../.gitbook/assets/backup-5.png)

Otherwise, get to **Restore Files** from More.

Sia needs to scan for your contracts and your backups. Click **Start Recovery Scan**.

![](../.gitbook/assets/backup-6.png)

Sia will scan for your contracts and available backups. You'll see a progress bar indicating how many blocks it has scanned.

![](../.gitbook/assets/backup-7.png)

Wait for the scan to complete. Sia might find your backups right away, but it might need some time. Give Sia up to 10 minutes after the scan completes to locate your backups. They'll appear in the window once they've been found. If after 10 minutes you don't see them, click **Start Recovery Scan** again.

![](../.gitbook/assets/backup-8.png)

Sia has found your backups. Click **Restore** next to the one you want. Feel free to close this window, or reopen it to check back - your files will begin to appear in the file manager in Sia over the next few minutes.

There's one last step - check your allowance to make sure it's set. Sia needs your allowance to be able to spend your Siacoins on contracts and download bandwidth to get your files back. Once that's done, you're good to go!

