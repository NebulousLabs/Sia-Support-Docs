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



Next move the extracted Sia binaries to _`/usr/local/bin/`_.

```
sudo mv -t /usr/local/bin Sia-v1.5.7-linux-amd64/siad Sia-v1.5.7-linux-amd64/siac
```

###

### Step 11: Automatic boot

To begin, create a systemd script to start up your sia host and login automatically.

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



To finish, start and enable the service you just created.

```
$ sudo systemctl start siad
$ sudo systemctl enable siad
```

### &#x20;Step 2: Create a wallet

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



### Step 4: Fund your wallet

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



### Step 5: Bootstrapping

Before you can begin hosting, you will need to wait for your host to be fully synced with the blockchain. You can use _**`siac`**_ to monitor the progress.

```
siac consensus
```



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
