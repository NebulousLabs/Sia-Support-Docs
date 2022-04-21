---
description: This section takes you through setting up a host using Linux CLI
---

# Linux CLI

## The process

### Step 1: Install Sia binaries

Download and extract the latest Sia Daemon Linux binaries from [https://sia.tech/get-started](https://sia.tech/get-started).

```
cd ~
wget -q https://sia.tech/releases/Sia-v1.5.7-linux-amd64.zip
unzip Sia-v1.5.7-linux-amd64.zip
```



Next move the extracted Sia binaries to `/usr/local/bin/`.

```
sudo mv -t /usr/local/bin Sia-v1.5.7-linux-amd64/siad Sia-v1.5.7-linux-amd64/siac
```



### Step 2: Locate your storage drive

To locate the storage drive you would like to use for your renters data.

```
sudo fdisk -l
```

This will give you the following printout.

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

{% hint style="info" %}
_For this guide I will be using the external HDD connected via USB listed as_ `/dev/sda`
{% endhint %}



### Step 3: Create a mount point

Create a mount point for your drive.

```
sudo mkdir -p /media/SiaStorage01
```



### Step 4: Configure Services

Now that you have located the path to your storage drive and have created your mount point, you can begin configuring the system services needed to automatically boot your host on startup.



To begin, create a bash script to mount your storage drives.

```
sudo nano /usr/local/bin/sia-auto-mount.sh
```

Once the text editor loads, copy and paste the following. Make sure to change your device and mount point to match your set up.

```
#!/bin/bash

sudo mount /dev/sda1 /media/SiaStorage01
```

{% hint style="info" %}
_If you have any other drives you would like to mount at start up, you can add them to the bash script._
{% endhint %}

Save the file to disk using `ctrl+o`

Exit the text editor using `ctrl+x`



Next create a systemd script to run your bash script at startup.

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

Save the file to disk using `ctrl+o`

Exit the text editor using `ctrl+x`



Now you will need to create a systemd script to run `siad` and login automatically at start up.

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

Save the file to disk using `ctrl+o`

Exit the text editor using `ctrl+x`

&#x20;

To finish, run your new services and enable them to run at start up.

```
sudo systemctl start sia-auto-mount
sudo systemctl enable sia-auto-mount

sudo systemctl start siad
sudo systemctl enable siad
```



### Step 5: Add storage

Now that you have your host set up to run at start up. You'll need to declare your storage locations using `siac`

```
siac host folder add /media/SiaStorage01 5TB
```



### Step 6: Create a wallet

```
siac wallet init -p 
```

{% hint style="info" %}
_Write down your recovery keys and keep them somewhere safe. If you loose these you will not be able to recover your Siacoin._
{% endhint %}



Once created you'll then need to unlock the wallet using the seed phrase you wrote down.

```
siac wallet unlock
```



### Step 7: Fund your wallet

Generate a new wallet

```
siac wallet address
```



Now that you have an address, you can send Siacoin to fund your wallet.

{% hint style="info" %}
_You can fund your wallet before your host has finished syncing to the blockchain. But you will not be able to see your funds until you have fully synced._
{% endhint %}

{% hint style="info" %}
_It is recommended to have about 1000 Siacoin per TB._
{% endhint %}



### Step 8: Configure Pricing

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

```
siac host config maxduration 12w
```

{% hint style="info" %}
_The recommended minimum contract length is 12 weeks._
{% endhint %}



To see more configuration settings use the following

```
siac host config -h
```



### Step 9: Bootstrapping

Before you can begin hosting, you will need to wait for your host to be fully synced with the blockchain. You can use _**`siac`**_ to monitor the progress.

```
siac consensus
```



### Step 10: Announce

Once you have completed syncing to the blockchain The only thing left, is for you to announce your host to the network.

```
siac host announce
```



### Step 11: Retire

{% hint style="info" %}
_Before retiring your host, you will first need to stop accepting contract and allow any current contracts to expire. Once all your remaining contracts have expired, you can then shut down your host without any loss of data or collateral._
{% endhint %}

```
siac host config acceptingcontracts false
```
