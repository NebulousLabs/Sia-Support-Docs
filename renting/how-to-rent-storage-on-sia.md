# How to rent storage on Sia

When you upload files on the Sia network, you become a **renter**. You upload files to other users who have made their space available, called **hosts**. Learn more [about renting](about-renting.md) and [managing your files](managing-your-files.md) before you start.

But the only thing that you need to set when you start uploading is your **Allowance**, or how much money you're willing to spend on storage. Having an allowance makes sure that your storage costs are predictable, and won't exceed an amount you're comfortable with.

## Things you'll need

* Sia installed on your computer
* A Sia wallet set up
* Siacoins, the cryptocurrency used to buy and sell storage

## The process

{% hint style="info" %}
These instructions walk you through how to upload files in Sia-UI.
{% endhint %}

Go to the Files tab in Sia-UI. Click **Setup Allowance**.

![](../.gitbook/assets/rent-tab.png)

Enter in the amount of Siacoin you'd like to spend for storage. You'll only ever pay for what tyou use, but entering an allowance that's close to what you'll actually use is a good idea. If you're not sure what to enter, use the default values.

In this example, we say that we want to spend 500 SC per TB. As today's prices, that's about $2. We also expect to store about 3 TB of data. Because the default is to store data for three months, the equation becomes:

**500** SC per TB x **3** TB x **3** months, or **500** x **3** x **3**. This gets you an allowance of 4,500 SC.

Click **OK.**

![](../.gitbook/assets/allowance-tab.png)

Now you might have to wait a minute. Sia is busy - it's forming contracts with hosts to get ready for all your data.

This process usually takes about 10-15 minutes. When it's done, you'll see Sia-UI's file manager ready to go. After you can start uploading, that Contracts Active number will slowly tick up to about 50. That might take a couple hours to finish.

![](../.gitbook/assets/renter-creating-contracts.png)

Once Sia is ready to go, you'll see some icons towards the right.

![](../.gitbook/assets/rent-icons.png)

In this example, we use the file upload option to start moving a .zip to Sia.

![](../.gitbook/assets/renter-uploading.png)

Over time, you'll see Contracts Active increase to about 50, and Health increase to 100%. Upload speed will vary based on your internet connection, your hosts' internet connection, and advancements to the Sia protocol as new versions are released. Keep in mind that uploading several TB of data can take several days or weeks.

That's it! Your files are on Sia - the most secure, affordable decentralized cloud network in the world.

