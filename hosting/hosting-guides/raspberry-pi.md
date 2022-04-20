---
description: This section takes you through setting up a host on a Raspbery Pi 4.
---

# Raspberry Pi

## The process

### Step 1: Download and install Raspberry PI Imager

Download and install the latest version of Raspberry PI Imager from [**raspberrypi.org/software/**](https://www.raspberrypi.org/software/)**.**

### Step 2: Download and install Ubuntu

Using the Raspberry PI Imager software download and install Ubuntu 20.04 LTS onto your Raspberry PI SD card.

**Choose OS >> Other general purpose OS >> Ubuntu >> Ubuntu 20.04 LTS**

### Step 3: First boot

Once Ubuntu has been installed on your MicroSD card insert it into your Raspberry Pi and turn it on. By default ssh is open, so once your Rasberry Pi has finished booting you can open a terminal on another device and ssh into your host.

{% hint style="info" %}
_By default Ubuntu is installed with the user account **`ubuntu`** already created with the default password **`ubuntu`**. Use this to login through ssh._
{% endhint %}

```
ssh ubuntu@hostname
```

{% hint style="info" %}
_If you would like to use a different user account make sure to create it now._
{% endhint %}



### Step 4: Install _`unzip`_

To install _`unzip`_ use the _`apt`_ package manager.

```
sudo apt update && sudo apt upgrade -y && sudo apt install unzip -y
```



### Step 5: Download and install the Sia binaries

Download and extract the latest Raspberry Pi binaries from [https://sia.tech/get-started](https://sia.tech/get-started).

```
cd ~
wget -q https://sia.tech/releases/Sia-v1.5.7-linux-arm64.zip
unzip Sia-v1.5.7-linux-arm64.zip
```



Next move the extracted Sia binaries to _`/usr/local/bin/`_.

```
sudo mv -t /usr/local/bin Sia-v1.5.7-linux-arm64/siad Sia-v1.5.7-linux-arm64/siac
```



### Step 6: Initialize and setup a new wallet

```
siac wallet init -p
```

{% hint style="info" %}
_Write down your recovery keys and keep them somewhere safe. If you loose these you will not be able to recover your Siacoin._
{% endhint %}



### Step 7: Unlock your wallet

```
siac wallet unlock
```

{% hint style="info" %}
_You will know this is working by checking your **`siad`** shell. The process should take about 20-30 minutes to complete._
{% endhint %}



### Step 8: Generate wallet and transfer funds

```
siac wallet address
```

{% hint style="info" %}
_It is recommended to have about 1000 Siacoin per TB._
{% endhint %}



### Step 9: Create a mount point

```
sudo mkdir /media/SiaStorage
```



### Step 10: Locate your storage drive

To locate the storage drive you would like to use for your renters data.

```
sudo fdisk -l
```

This will give  you the following printout.

```
Device         Boot  Start       End   Sectors   Size Id Type 
/dev/mmcblk0p1 *      2048    526335    524288   256M  c W95 FAT32 (LBA) 
/dev/mmcblk0p2      526336 250347486 249821151 119.1G 83 Linux 


Disk /dev/sda: 5.47 TiB, 6001175125504 bytes, 11721045167 sectors 
Disk model: Expansion Desk   
Units: sectors of 1 * 512 = 512 bytes 
Sector size (logical/physical): 512 bytes / 4096 bytes 
I/O size (minimum/optimal): 4096 bytes / 4096 bytes 
Disklabel type: gpt 
Disk identifier: 95C65D62-CA73-934A-9C4B-030C5FF0321F 


Device     Start         End     Sectors  Size Type 
/dev/sda1   2048 11721045133 11721043086  5.5T Linux filesystem

```



### Step 11: Automatically mount storage on boot

To begin create a new bash script to mount the external drives that will be storing your renter data.

{% hint style="info" %}
_In this example we will be using the 5.5TiB storage drive listed as **`/dev/sda`**_
{% endhint %}

```
sudo nano /etc/systemd/system/sia-auto-mount.service
```

Once the text editor loads, copy and paste the following.

```
#!/bin/bash

sudo mount /dev/sda1 /media/SiaHostStorage
```

Save the file to disk using _**`ctrl+o`**_

Exit the text editor using _**`ctrl+x`**_



Next create a systemd script to mount your storage drives automatically on boot.

```
sudo nano /etc/systemd/system/sia-auto-mount.service
```

Once the text editor loads, copy and paste the following.

```
[Unit]
Description=Mount Sia renter data storage drives
After=systemd-user-sessions.service network-online.target

[Service]
User=root
Type=forking
ExecStart=/usr/local/bin/sia-auto-mount.sh
Restart=always
RestartSec=15

[Install]
WantedBy=multi-user.target
```

Save the file to disk using _**`ctrl+o`**_

Exit the text editor using _**`ctrl+x`**_



Next create a systemd script to start up your sia host and login automatically.

```
sudo nano /etc/systemd/system/siad.service
```

Once the text editor loads, copy and paste the following.

```
[Unit]
Description=siad
After=network.target sia-storage-mount.service

[Service]
Type=simple
ExecStart=/usr/local/bin/siad -M gctwh -d /home/ubuntu/siad
ExecStop=/usr/local/bin/siac stop
Restart=always
RestartSec=15
User=ubuntu
Environment=”SIA_WALLET_PASSWORD=walletseedphrase”
LimitNOFILE=900000

[Install]
WantedBy=multi-user.target
Alias=siad.service
```

Save the file to disk using _**`ctrl+o`**_

Exit the text editor using _**`ctrl+x`**_

&#x20;

### Step 12: Add your storage folder

```
siac host folder add /media/SiaStorage 5TB
```



### Step 13: Configure your pricing

Set your minimum storage price.

{% hint style="info" %}
_Filebase will only make contracts with hosts that have a storage price of 150SC or higher. Also Skynet Labs will not make contracts with hosts that have a storage price of 300SC or higher._
{% endhint %}

```
siac host config minstorageprice 150SC
```



Set your collateral.

{% hint style="info" %}
_Your collateral should be two times your storage price. So if your storage price is set to 150SC, your collateral should be set to 300SC_
{% endhint %}

```
siac host config collateral 300SC
```



Set your bandwidth fees.

```
siac host config mindownloadbandwidthprice 250SC
siac host config minuploadbandwidthprice 50SC
```



Set your max contract length.

{% hint style="info" %}
_The recommended minimum contract length is 12 weeks._
{% endhint %}

```
siac host config maxduration 12w
```



To see more configuration settings use the following

```
siac host config -h
```



### Step 14: Announce your host!

Now all that is left, is for you to announce your host to the network and you're done!

```
siac host announce
```



### Step 15: Retire your host

{% hint style="info" %}
_Before retiring your host, you will first need to stop accepting contract and allow any current contracts to expire. Once all your remaining contracts have expired, you can then shut down your host without any loss of data or collateral._
{% endhint %}

```
siac host config acceptingcontracts false
```
