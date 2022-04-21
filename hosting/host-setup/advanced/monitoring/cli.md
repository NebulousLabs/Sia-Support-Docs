# CLI

A detailed itemization of earned coins and expected revenues, together with more parameters and statistics, can be checked with the command `siac host -v` in the Terminal. This is an example of the report:

```go
General Info:
    Connectability Status: Host appears to be working.
    Version:               1.5.7

Host Internal Settings:
    acceptingcontracts:   Yes
    maxdownloadbatchsize: 17.83 MB
    maxduration:          26 Weeks
    maxrevisebatchsize:   17.83 MB
    netaddress:           xx.xxx.xxx.xx:9982 (automatically determined)
    windowsize:           24 Hours

    collateral:       150 SC / TB / Month
    collateralbudget: 100 KS
    maxcollateral:    5 KS Per Contract

    minbaserpcprice:           100 nS
    mincontractprice:          50 mS
    mindownloadbandwidthprice: 25 SC / TB
    minsectoraccessprice:      2 uS
    minstorageprice:           50 SC / TB / Month
    minuploadbandwidthprice:   1 SC / TB

    ephemeralaccountexpiry:     604800s
    maxephemeralaccountbalance: 1 SC
    maxephemeralaccountrisk:    5 SC

    registrysize:       0  B
    customregistrypath: 

Host Financials:
    Contract Count:               1199
    Transaction Fee Compensation: 426 SC
    Potential Fee Compensation:   3.543 KS
    Transaction Fee Expenses:     0 H

    Storage Revenue:           193.2 SC
    Potential Storage Revenue: 441.9 SC

    Locked Collateral: 81.59 KS
    Risked Collateral: 1.385 KS
    Lost Collateral:   0 H

    Download Revenue:           23.58 mS
    Potential Download Revenue: 3.186 SC
    Upload Revenue:             1.708 SC
    Potential Upload Revenue:   12.04 SC

RPC Stats:
    Error Calls:        6125
    Unrecognized Calls: 2222
    Download Calls:     13097
    Renew Calls:        1791
    Revise Calls:       99676
    Settings Calls:     296858
    FormContract Calls: 1503

Storage Folders:
    Used    Capacity      % Used    Path
    72.592 GB    107.374 GB    67.71      /Users/Sia/Storage
```
