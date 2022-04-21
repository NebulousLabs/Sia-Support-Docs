# What are these deductions in my wallet?

Unexpected deductions of Siacoin from your Sia-UI wallet are not an immediate cause for concern. There are a few completely normal causes.

## **You are renting storage space, and the coins are paying for the storage space, as specified in your renter allowance.**

If you don't store any files, your coins will be returned to your wallet after the contract expires in three months.

## **You are hosting, and your coins are paying for collateral.**

If you are a good host \(preserve uptime and preserve any files you are storing\), your coins will be returned to your wallet after the contract expires in three months.

## **You may be running the same wallet \(same seed\) on multiple computers.**

This is not supported and can cause problems. You should delete both wallets and start over with fresh seeds. You can do this by clicking on the "Terminal" tab and typing \`wallet init --force\`. Then use the Recover Seed feature to restore your old seed to only one of the computers.

## **Something else may have gone wrong.**

If none of the above points describe your situation, you can delete your current wallet by clicking on the Terminal tab and typing:

`wallet init --force`

Then use the Recover Seed feature to restore your old seed to your new wallet. This should fix the problem.

## **Someone has access to your seed.**

This is the bad one. If someone has access to your 29-word seed, they can easily steal your Siacoin by loading it into another instance of Sia-UI. Keep your seed safe.

