---
description: >-
  There's some specific info you should know before you get your first file on
  Sia.
---

# Managing your files

{% hint style="info" %}
As with any file storage or backup solution, Sia should not be your sole location for critical files.
{% endhint %}

## Uploading

Uploading happens in Sia-UI or your preferred command-line interface. Sia-UI has your standard file browser or drag-and-drop options, just like any other file storage application. There are special commands that you'll want to become familiar with when using the CLI version of Sia, which is called `siac`.

When you upload a file, it gets split into 10 pieces. Each of those 10 pieces is then duplicated three times. Each piece is then encrypted and sent to 30 different hosts. Because a host only has a single encrypted piece of your file, they can never see what you upload.

Visualized differently:

* 1 file gets
* split into 10 pieces
* which are each duplicated three times.
* Those 30 pieces are then encrypted
* and sent to 30 different hosts.

You don't have to do anything, or even see that this process happens.

## Limits on uploading\*

\*These numbers will change over time.

**Maximum total storage:** Sia can currently handle 35 TB of data in a single node, or installation of Sia.

**File size:** The minimum file size on Sia is currently 40 MB. Uploading smaller files isn't a problem, but Sia will pad each of them out to 40 MB. Your 80 MB short video stays 80 MB. But your 8 MB photo and your 100 KB document each become 40 MB when uploaded.

This means that, if you're uploading many small files, you'll save a lot of money by zipping them up together before uploading. This minimum file size will be _significantly_ reduced in a future update.

## Health and Redundancy

In Sia, you'll see the health of your files represented as a percentage. This refers to how many pieces of this file are available. You always want this to be 100%, which means that all 30 pieces of your file are stored on hosts. Sia is smart though – if a host goes offline, it will re-duplicate that piece on a new host the next time it checks.

Sia can only check when it's active though, so be sure to open Sia periodically to refresh the health of your files.

## Downloading

Downloading files happens right through the app as well. There's a small download icon next to each file in your list. Downloading requires Siacoins since you pay for the bandwidth you use.

### Maintaining Data _\*\*_

In order to make sure that your data is always available, there's a couple of important tasks you should periodically perform.

* **Refreshing your allowance** - About six weeks after your contracts are created, your allowance attempts to refill itself. Sia will never spend more than your allowance, so it needs to be refilled to facilitate contract renewals and downloads through the rest of the contract period. _**!** The allowance will refill automatically when you open Sia._
* **Renewing your contracts** - Your storage contracts will renew automatically at the end of the contract period. By default, Sia will attempt to renew your contract within about 1 month of the contract expiration date. If you started renting at the beginning of January, your 3-month contracts would expire around the end of March. Sia would attempt to renew them around the beginning of March. _**!** Your contracts renew automatically when you open Sia._
* **Boosting file health** - File health and redundancy are also boosted if needed, as described above. 

**Sia needs to be running with your wallet unlocked for these things to occur**, so as a renter, it's a good idea to open Sia **at least once a month** and let it run overnight to take care of miscellaneous housekeeping tasks such as these. If you simply upload files and then never open Sia again, your allowance and your contracts will eventually expire and your files will be immediately deleted once your contracts are no longer valid.

