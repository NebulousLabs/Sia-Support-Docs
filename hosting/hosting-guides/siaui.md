# SiaUI

This section takes you setting up a host using the **SiaUI**.

## The process

### Step 1: Download and Install the SiaUI

Download and install the [**SiaUI**](https://sia.tech/get-started) for your system.

### Step 2: Create your wallet

Once installed create a new wallet and allow it to sync to the blockchain. If you already have a existing wallet that you would like to use, you may do so by typing in your seed phrase.

_**Note:** On a SSD syncing to the blockchain can take a day or more. Therefore it is not recommended to install Sia on a HDD as syncing will take much longer._

### Step 3: Configure your host

Once you have the SiaUI installed, open Sia and click on the **Host** tab on the left. This is where you can configure your host settings. The first thing you do is tell Sia where your storage folder is. This is a location on the storage device you want to use for hosting.

Click **Add a folder**, then select a location. You can choose a drive (like D:\\) to use an entire empty drive or partition, or you can pick a specific folder on a drive. Sia will create one large file in the location you select that allocates the amount of storage you choose.

Tell Sia how much space you want to allocate to hosting, in megabytes. Entering a value lower than 32 GB will provide a warning since as a host you're graded on having a lot of available storage. Set at least 4 TB if you can. You can type in a value if you want to set a value higher than what the slider allows.

Here are some quick values you can use to get started:

* 10240 is 10 GB
* 51200 is 50 GB
* 102400 is 100 GB
* 1024000 is 1 TB
* 4096000 is 4 TB
* 10240000 is 10 TB
* 102400000 is 100 TB

## Host Settings

{% tabs %}
{% tab title="Max Duration" %}
Measured in weeks, Max Duration determines the longest contract you'll accept. The default length during contract creation for renters is 13 weeks, so don't go lower than that or you risk not forming many contracts.
{% endtab %}

{% tab title="Collateral Per TB/Month" %}
Collateral is the amount of Siacoins you're willing to lose if you end up not fulfilling your end of the contract, which is to store the renter's data for the contract length while being online.

Putting up more collateral improves trust by showing you're willing to lose more money than another host. Setting this amount at 2-3 times your storage price is a good idea to maximize your host score while not losing too much money if your host does indeed go down.
{% endtab %}

{% tab title="Storage Per TB/Month" %}
The biggest factor in your host score, this number is how many Siacoins you are charging for 1 TB each month. The less you charge, the more positively it affects your host score. The more you charge, the more money you make. Find your balance between profitability and competitive pricing.
{% endtab %}

{% tab title="Download Per TB" %}
This is how much you charge renters for downloading data from your host.

Users who frequently download data might use a lot of bandwidth, and you can charge accordingly.
{% endtab %}

{% tab title="Upload Per TB" %}
This is how much you charge renters for uploading data to your host.

This is similar to download bandwidth. You pay for your bandwidth from your ISP, so you can pass that cost on to your renters.
{% endtab %}

{% tab title="Contract Fee" %}
This is the cost of creating a contract with your host.

This can only be changed in siac, or using the Terminal in Sia-UI with the command `host config mincontractprice <value>SC,` or;

`host config mincontractprice 0.3SC`
{% endtab %}
{% endtabs %}

## Announce your host

Click the slider at the top of the Host window next to the Announce Host button so it appears green. This will turn on your host for accepting new storage contracts from renters. Then, unless you used DDNS in a previous step, click **Announce Host** to the Sia network so that renters can find you.

### If you signed up for a DDNS service

You need to announce your host using your DDNS hostname in order for it to work. You can also announce a specific IP address. Click on the **Terminal** `>` icon at the top of the Sia-UI window, and type:

`host announce [ddns hostname or ip]:9982`

substituting \[_ddns hostname or ip_] with your unique DDNS hostname that you received from your DDNS service or the IP you want to announce. Make sure to include `:9982` afterward and without a space, as this specifies which port renters can contact you through and is the default for Sia.

{% hint style="info" %}
Announcing your host is a transaction that will appear in your Transaction list in your wallet.
{% endhint %}

Read on for some additional important things to take care of to get the most out of your host.

## Port Forwarding (Required)

The number one reason that users have issues getting their host running is port forwarding. By default, the host is on port `:9982`, but you should forward all ports from `:9981` to `:9984`. You can see if your host has forwarded its port from this website: [http://canyouseeme.org/](http://canyouseeme.org)

{% hint style="warning" %}
Be sure to not forward port 9980, as this can represent a security threat. You'll need to access your router's manual to learn how to set up port forwarding on your device.
{% endhint %}

### What each port does

* :9981 (consensus p2p network)
* :9982 (renter-host-protocol-v2)
* :9983 (rhp-v3)
* :9984 (rhp-v3-websocket)

If your port is not forwarded, it's probably because your router does not support UPnP. Unfortunately, that means you need to go into the configuration yourself and do it manually. There are some great guides to help you here: [https://portforward.com/](https://portforward.com)

Renters know to contact your host from the network address in the host announcement. If your IP address has changed since your announcement, you will need to announce again. If you have a firewall or some networking setup that may be blocking inbound connections from the internet, you need to make sure that it allows traffic to reach the host.

Finally, if you have a dynamic IP address, you should strongly consider setting up something like DynDNS, which allows you to announce a hostname and then manages the dynamic IP address issue for you.

## Set up Dynamic DNS (DDNS) (Optional)

Most residential Internet services assign subscribers a dynamic public IP address which may change at a set duration, or when rebooting your Internet modem. This can be a problem because when running a service like a Sia host, renters find you by your public IP address. The host tracks your current IP address and automatically re-announces every time that the IP address changes. If you have manually set the host's net address (which can be IPv4, IPv6, or a full hostname like `myhost.sia.tech`), then the host will stop tracking your IP address and instead just use the one you have set manually.

You can go a step further and mitigate this issue by signing up for a Dynamic DNS (DDNS) service. If you have a static public IP address, you don't need to worry about this step. If you're not sure whether or not you have a static IP address, it won't hurt to set up DDNS anyway.

DDNS services work by assigning you a subdomain or URL, and having you run a small program or script on a device on your network - your Sia host computer will work fine. Some routers also have built-in DDNS support for certain DDNS services. When your public IP address changes, the DDNS client detects the change and updates your DDNS subdomain or URL with your new IP address. You can use your DDNS address to announce your Sia host, and renters will always be able to find you as long as you have DDNS set up and the IP update software running.

There are several free DDNS services available, such as [NoIP.com](https://www.noip.com/remote-access), [Afraid.org](https://freedns.afraid.org), or [Dynu.com](https://www.dynu.com/DynamicDNS). Visit any of these, or search for your own free DDNS service, and follow the instructions to set up your DDNS hostname and install IP update software. Note that some free services may require you to confirm you're still using your DDNS account with them by requiring you to do something like click a link in an email once a month or so - make sure you watch for this, as you could lose your DDNS hostname and make your Sia host unconnectable if you don't. When you're done, you should have a DDNS URL such as `mysiahost.noip.com` which you can use in the next step to announce your host with.

## Auto-unlock your Sia wallet (Optional)

What happens if your computer shuts down and you're not there to turn it back on? Setting your computer to automatically reboot, start Sia, and unlock your wallet can get you back up and running to minimize downtime.

Read this page to set it up.

## Check host configuration (Optional)

Once you are set up, you can be proactive about making sure everything is set up correctly. Use the [SiaCentral Host Troubleshooter](https://troubleshoot.siacentral.com) to check your host configuration and make sure it can form contracts. Change your host address if necessary to your host's actual public IP or DDNS address.

If SiaCentral discovers issues when connecting to your host, wait an hour or two and try again - the announcement can take a little while to reach the Sia network.

## Set up host metadata backups (Recommended)

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
