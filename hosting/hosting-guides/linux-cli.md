---
description: This section takes you through setting up a host using Linux CLI
---

# Linux CLI

## The process

### Step 1: Download and install the latest Sia binaries

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



### Step 2: Initialize and setup a new wallet

```
siac wallet init -p 
```

{% hint style="info" %}
_Write down your recovery keys and keep them somewhere safe. If you loose these you will not be able to recover your Siacoin._
{% endhint %}



### Step 3: Unlock your wallet

```
siac wallet unlock
```

{% hint style="info" %}
_You will know this is working by checking your **`siad`** shell. The process should take about 20-30 minutes to complete._
{% endhint %}



### Step 4: Generate wallet and transfer funds

```
siac wallet address
```

{% hint style="info" %}
_It is recommended to have about 1000 Siacoin per TB._
{% endhint %}



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
