# Using the Sia Ledger app with Sia Central

## What is a Ledger Nano?

The Ledger Nano X and Ledger Nano S are hardware wallets created by Ledger. A hardware wallet stores the private keys to cryptocurrency on a separate device, making it much harder for malicious parties to steal them. In fact, the private keys never leave the hardware wallet, so they will remain secure even if the device is connected to a compromised computer. As long as you follow best practices when using your hardware wallet, it is virtually impossible for an attacker to steal your funds.

Hardware wallets are an important part of the crypto ecosystem, and they're one of the best ways to personally secure your coins. We're happy to be working with Ledger to offer our official Sia app for use on both the Ledger Nano X and Ledger Nano S.

To send and receive Siacoin on a Ledger device we will be using Sia Central's web wallet through the latest version of Google Chrome desktop. Sia Central's web wallet only supports Siacoin, sending and claiming Siafund dividends are not yet supported. The web wallet should always be accessed from [https://wallet.siacentral.com](https://wallet.siacentral.com). This article will be using a Ledger Nano X with bluetooth, but the steps are similar for USB or the Ledger Nano S.

## Things you'll need

Using Sia on a Ledger device requires a few things. You will need:

* Your Ledger device
* The Sia app installed on your device
* A desktop browser to access Sia Central's web wallet

### Supported browsers

The web wallet only supports Ledger wallets on some desktop browsers:

|                | USB Suppport  | Bluetooth Support (Ledger Nano X only) |
| -------------- | ------------- | -------------------------------------- |
| Chrome         | 89+           | 89+ (macOS and Windows only)           |
| Microsoft Edge | 89+           | Not available                          |
| Opera          | 76+           | Not available                          |
| Brave          | 1.29.77+      | Not available                          |
| Safari         | Not available | Not available                          |
| Firefox        | Not available | Not available                          |
| Android        | Not available | Not available                          |
| iOS            | Not available | Not available                          |

## Set up your device

_Let's make sure your hardware wallet is ready to use._

### Ledger Nano X

1. [Initialize](https://support.ledger.com/hc/en-us/articles/360018784134-Set-up-your-Ledger-Nano-X) your Ledger Nano X. This gets the hardware wallet set up and ready to use.
2. Download [Ledger Live Desktop](https://support.ledger.com/hc/en-us/articles/4404389606417-Download-and-install-Ledger-Live) onto your computer. Ledger Live is the app you use to manage your Ledger device.
3. [Install the latest firmware](https://support.ledger.com/hc/en-us/articles/360013349800-Update-Ledger-Nano-X-firmware) on your Nano X. This ensures compatibility with the Sia app.

### Ledger Nano S

1. [Initialize](https://support.ledgerwallet.com/hc/en-us/articles/360000613793) your Ledger Nano S. This gets the hardware wallet set up and ready to use.
2. Download [Ledger Live](https://support.ledgerwallet.com/hc/en-us/articles/360006395553/) onto your computer. Ledger Live is the app you use to manage your Ledger device.
3. [Install the latest firmware](https://support.ledgerwallet.com/hc/en-us/articles/360002731113) on your Nano S. This ensures compatibility with the Sia app.

At this point, you're ready to install apps on your Ledger device. Remember to store your 24-word recovery phrase in a safe place, because you'll need it to recover your funds if your device is lost or damaged.

### Install the Sia Ledger app <a href="#install_the_sia_ledger_app" id="install_the_sia_ledger_app"></a>

_Now we'll install the Sia app onto your Ledger hardware wallet._

1. Open the **Manager** in Ledger Live.

![](../.gitbook/assets/nanox-manager.png)

1. Connect and unlock your Ledger device via USB. You will be prompted on the device to allow the manager.
2. Search for Sia in the app catalog.

![](../.gitbook/assets/nanox-sia.png)

1. Click the **Install** button. Your device will display **Processing...**
2. When the main menu reappears, the Sia app has been successfully installed.

## Wallet Setup

Sia Central's web wallet is a lite, non-custodial wallet that allows you to send and receive Siacoin without downloading the blockchain. After the Ledger wallet is imported, your balance can be viewed almost immediately.

1. Access the wallet at [https://wallet.siacentral.com](https://wallet.siacentral.com)
2. If you have never used the wallet before you will be prompted to set a password. This password is used to encrypt your data and is required to unlock your wallets in the future.

![](../.gitbook/assets/lite-wallet-set-password.png)

1. Create a new wallet

![](../.gitbook/assets/lite-wallet-create-ledger.png)

1. Click **Ledger Wallet** to add a new Ledger wallet.

You will now need to connect your device and import an address to send Siacoins to. When connecting you can choose either USB or Bluetooth depending on your browser's support. ![](../.gitbook/assets/lite-wallet-import-connect.png)

1. Connect and unlock your device, then open the Sia app.
2. Click the green **Connect** button in the wallet. The status should change to "Connected".

{% hint style="info" %}
If you have never connected your device to this computer before, you may need to confirm the pairing on the device.
{% endhint %}

![](../.gitbook/assets/lite-wallet-import-pair.png)

1. Click the **Add Address** button. Confirm that you want to generate the address on your device by pressing the right button once, the screen should now read "Approve"; then press both buttons together to confirm.

![](../.gitbook/assets/nanox-generate-address.png)

1. The address is now imported, verify that the address in the box matches the address displayed on the device. If you have used this device before your balance will update.
2. Optionally, you can add additional addresses by clicking the **Add Address** button again and confirming on the device.
3. After you have imported your addresses click the **Done** button at the bottom. You will now have a new wallet in your dashboard.

![](../.gitbook/assets/lite-wallet-balance-ledger.png)

## Receiving Siacoin <a href="#receiving_siacoin" id="receiving_siacoin"></a>

After the initial setup is complete you can send Siacoin to your wallet. Select your wallet from the list on the right, then click the _Receive_ button right under the balance.

![](../.gitbook/assets/lite-wallet-ledger-receive.png)

Before sending Siacoin to an address it is important to manually verify that it belongs to your wallet.

1. Connect your Ledger Nano, unlock it, and open the Sia app.
2. Click the green _Connect_ button above the QR code.
3. Click the green _Verify_ button next to your address.
4. Confirm that you want to generate the address on your device.
5. Manually check that the address displayed on the device matches the address in the text box.

After verifying the address you can send Siacoin to this address. If this is the first time you have sent Siacoin to a hardware wallet, try with a small amount first to make sure everything is setup correctly. When you receive Siacoin it will be marked as an unconfirmed transaction for 10 minutes to an hour. You will have to wait for at least one confirmation before you can spend your Siacoin.

![](../.gitbook/assets/lite-wallet-ledger-receive-unconfirmed.png)

## Checking balance <a href="#checking_balance" id="checking_balance"></a>

Your balance and your last 500 transactions can be displayed at any time by selecting the wallet from the list on the left of the dashboard. You do not need your Ledger to view your balance. Just to verify addresses or send transactions.

![](../.gitbook/assets/lite-wallet-ledger-confirmed-balance.png)

## Sending Siacoin <a href="#sending_siacoin" id="sending_siacoin"></a>

To send a transaction you will need your device. Select your wallet from the list on the left; then click **Send**. A dialog will pop up allowing you to input the recipient's address and the amount of Siacoin to send them. You can enter the amount in your display currency, or Siacoin.

![](../.gitbook/assets/lite-wallet-ledger-send-setup.png)

Once you have entered the address and amount, click the **Send** button. You will now need to verify the transaction and sign it with your device.

![](../.gitbook/assets/lite-wallet-ledger-send-sign.png)

1. Connect your Ledger device, unlock it, and open the Sia app.
2. Press the green **Connect** button; the **Sign** button should enable.

![](../.gitbook/assets/lite-wallet-ledger-send-pair.png)

1. Click the green **Sign** button.
2. You will now need to confirm the transaction details on your device.

![](../.gitbook/assets/nanox-send-confirm.png)

1. Verify that the "SC Output #1", displayed on your device, matches your intended recipient. To confirm on the device: scroll to page 2 by pressing the right button, then press both buttons at the same time.
2. Next the send amount will be displayed; verify it matches the amount you wish to send. Then confirm by pressing both buttons at the same time.
3. Verify that "Miner Fee #1" matches the amount displayed on the screen. Confirm by pressing both buttons at the same time.
4. After confirming the transaction details are correct, sign the transaction. Press the right button once; the device should now say "Approve". Press both buttons at the same time to confirm the signature.
5. In the lite wallet, the **Send** button should appear. To broadcast your transaction and send your Siacoin, press **Send**. The amount will be deducted from your balance and sent to your recipient.

![](../.gitbook/assets/lite-wallet-ledger-send-confirm.png)

If the transaction broadcast successfully, you should now have a new unconfirmed transaction in your transaction list deducting the amount + the transaction fee. Your recipient will have to wait between 10 minutes to an hour for the transaction to be confirmed. Depending on how many UTXOs are in your wallet; you may have to wait for at least one confirmation before being able to send another transaction.

![](../.gitbook/assets/lite-wallet-ledger-unconfirmed-send.png)

## Additional help

If you're having trouble, we're here to help. [Email our official support](mailto:hello@sia.tech), or [join our Discord server](https://discord.gg/sia) and post in the #core-dev or #app-dev channels.
