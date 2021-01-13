# Renter troubleshooting

There are some common issues that you might encounter when uploading files to Sia, mostly related to stuck or stalling uploads. There are some easy solutions for these issues, as long as you have the right info. We’ll detail what to look for and possible solutions in this document.

`siac`, the command-line for Sia, is a great way to get information that can help identify your problem. Commands can be run in your preferred CLI, or in Sia-UI by accessing the built-in Terminal from the top menu bar.

## Gather general Sia info

Use the command `siac`. This will print basic info about Sia’s status, focusing on your blockchain sync status, your wallet status, and some info about your renter.

```go
Consensus:
  Synced: Yes
  Height: 216307

Wallet:
  Status:          unlocked
  Siacoin Balance: 415.95 KS

Renter:
  Files:           257
  Total Stored:    2.93 TB
  Min Redundancy:  0
  Contracts:       52
```

You can use this info to make sure that your wallet is unlocked, that you have enough Siacoins, and check important renter info like your number of files, amount of data stored, and minimum redundancy.

If your wallet is locked, you can’t spend Siacoins. This means you can’t form contracts or renew your allowance. This alone can grind your Sia renting to a standstill.

If you don’t have enough contracts, Sia won’t be able to maintain your data on the network. Contracts should usually be right around 50. If you have too few, your allowance settings might be too strict. Try raising the amount you’re willing to spend on storage and confirm the number of hosts in your allowance settings as this controls the number of contracts.

### Get renter-specific info

Use the command `siac renter`. This will print some info that you saw earlier, but also important allowance info.

Quick tip: Your allowance is the maximum amount of Siacions you’re willing to spend on storage. By setting this number, you’re making sure that you don’t end up spending way more over your contract period that you intended. If your allowance runs out, you can’t make new contracts and your data will eventually be removed from Sia.

```go
Allowance:       12 KS
  Spent Funds:     254.4 SC
  Unspent Funds:   11.75 KS

Data Storage:
  Files:           257
  Total Stored:    2.93 TB
  Min Redundancy:  0
  Contracts:       52
```

You can also run `siac renter allowance` to get even more detailed allowance info.

```go
Allowance:
 Amount:               75 KS
 Period:               12096 blocks
 Renew Window:         4032 blocks
 Hosts:                50

Expectations for period:
 Expected Storage:     23.0000 TB
 Expected Upload:      560.000 GB
 Expected Download:    280.000 GB
 Expected Redundancy:  3

Spending:
  Current Period Spending:
    Spent Funds:      18.07 KS
      Storage:        12.72 KS
      Upload:         732.2 SC
      Download:       3.093 SC
      Fees:           4.617 KS
    Unspent Funds:    56.93 KS
      Allocated:      29.03 KS
      Unallocated:    27.9 KS
  Previous Spending:  34.32 KS
    Withheld Funds:   0 H
    Release Block:    0
```

You can use this to see if your allowance is large enough to accommodate the amount of storage you’re trying to rent. This might clue you in that you need to raise your allowance, or add more Siacoins to your wallet if you don’t have enough to set a proper allowance.

Specifically, look at your Unspent Unallocated amount. If this is reporting very low amounts of Siacoins then the allowance needs to be increased because all the other funds have been locked up.

Use the command `siac renter contracts`. This will print a long list of your contracts, but importantly will allow you to see your number of active contracts and the total amount of data stored.

### The log files

There’s also another important file - the renter.log. This can be found in the /sia/renter/ folder in your Sia data folder. You can use this to search for errors classified as `worker` or `uploadheap`.

Worker logs to search for:

```go
2019/07/29 18:16:05.728694 worker.go:199: Refreshed Worker Pool has 167 total workers and 0 are on cooldown
```

This log will tell you how many of your workers are on cool down. Search for \`Refreshed Worker Pool\`. If too many of your workers are on cooldown then uploads and downloads will be impacted. To find out why and which workers are on cooldown see the log messages directly above this line. There will be a line for each worker.

Uploadheap logs to search for:

```go
2019/07/29 18:16:12.598899 uploadheap.go:1122: [DEBUG] Executing an upload and repair cycle, uploadHeap has 250 chunks in it
```

Search for `Executing`. Check to see if this line appears and if so, how often. This will tell you how fast your renter is working through the uploadHeap for repairs. Also it should always have 250 chunks in it so if that number is not 250 then let the core team know so they can investigate. One edge case is if you are on the last cycle and have less than 250 chunks remaining, or there are just less than 250 chunks that need repair in general.

```go
2019/07/29 18:16:12.598899 uploadheap.go:348: WARN: no chunk indicies gathered, can’t add chunks to heap
```

If this is coming up a lot, this could be an issue. Reach out to a core team member.

Check your root `.siadir` file:

```go
cat siad/renter/siafiles/.siadir 

{"aggregatehealth":0.75,"aggregatelasthealthchecktime":"2019-08-
05T18:10:19.088309123+02:00","aggregateminredundancy":1.5,"aggregatemodtime":"2019-08-
05T20:13:52.972312906+02:00","aggregatenumfiles":63062,"aggregatenumstuckchunks":0,"aggregatenumsubdirs":0,"aggregatesize"
:23044664385536,"aggregatestuckhealth":0,"health":0,"lasthealthchecktime":"2019-08-
05T20:40:08.755212828+02:00","minredundancy":0,"modtime":"2019-08-
05T20:40:08.755948025+02:00","numfiles":0,"numstuckchunks":0,"numsubdirs":10,"size":0,"stuckhealth":0}
```

If you have python installed on your machine:

```python
cat siad/renter/siafiles/.siadir | python -m json.tool

{
    "aggregatehealth": 0.75,
    "aggregatelasthealthchecktime": "2019-08-05T18:10:19.088309123+02:00",
    "aggregateminredundancy": 1.5,
    "aggregatemodtime": "2019-08-05T20:13:52.972312906+02:00",
    "aggregatenumfiles": 63062,
    "aggregatenumstuckchunks": 0,
    "aggregatenumsubdirs": 0,
    "aggregatesize": 23044664385536,
    "aggregatestuckhealth": 0,
    "health": 0,
    "lasthealthchecktime": "2019-08-05T20:40:08.755212828+02:00",
    "minredundancy": 0,
    "modtime": "2019-08-05T20:40:08.755948025+02:00",
    "numfiles": 0,
    "numstuckchunks": 0,
    "numsubdirs": 10,
    "size": 0,
    "stuckhealth": 0
}
```

Here is the aggregate metadata of your filesystem that the repair loop is going to use. If `aggregatehealth` is &lt;= 0.25 then your system is healthy, if it is &gt; 0.25 then it should be repairing.

If there is a large number of `aggregatenumstuckchunks` then slow uploads could be because all the work is relying on the stuck loop. In this case you can try `siac renter unstuckall` to try and unmark those stuck chunks and allow for the repair loop to pick them up again.

Big things that you want to check for:

* Is your wallet unlocked?
* Does your allowance have Siacoins in it?
* Is your allowance large enough?
* Do you have enough active contracts?
* Do you have enough total contracts?

Reference the [renter README](https://gitlab.com/NebulousLabs/Sia/blob/master/modules/renter/README.md) to get an understanding of how the upload should be happening to then understand if the logs in renter.log make sense or indicate an error.

