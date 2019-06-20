---
layout: page
title: Releases
---

## Latest Version

Includes: 

* DriveNet-24
* loaded-coins file
* (No sidechain-template release for this version, yet)


Link here: [https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT](https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT)

## FAQ

### Why is this on Google Drive?

Because we also host a 4 GB file (of BTC's UTXOs) there, for "importing". And we haven't switched back yet.

The GitHub links are here: 

* [DriveNet](https://github.com/DriveNetTESTDRIVE/)
* [TestChain](https://github.com/drivechain-project/bitcoin/tree/sidechainBMM)

This is new/unstable software assume that it is a virus that will set your computer on fire then steal your BTC. At first, you should only be running it in Qubues / VirtualBox etc.

## Selected Release Notes

### DriveNet24 -- June 12, 2019

"Beta Release"

Important:

You will need to move loaded_coins_drivenet_0_24_00.dat into your data directory and rename it loaded_coins.dat

example: cp loaded_coins_drivenet_0_24_00.dat ~/.drivenet/loaded_coins.dat

Updates include:

  * The re-activation of loaded coins for testing. Only the first few releases imported a UTXO set (in those cases the entire bitcoin core UTXO set) before we turned it off due to some bugs and the large  setup / import time.

In this version we have a loaded coins UTXO set with a few outputs for beta testers to use. There are no UTXOs from bitcoin core for the beta. If you would like one of the limited testing outputs (1,000 testnet coins) just ask.

* Loaded coins bug fixes:
* * Correctly handle spent status of loaded coins when a block is disconnected for a reorg etc. This is different than a normal UTXO as the transaction which created the UTXO doesn't actually exist in any of the blocks we rewind.
* * Fix pointer bug that would cause errors during shutdown after importing a private key that owns a loaded coin UTXO.
* Fix sidechain database synchronization issues during startup sometimes caused by VerifyDB()
* Fix sidechain database and sidechain activation bugs during reindexing
* Fix bugs in IsBMMRequest
* Fix SCDB sync bugs during init
* Refactoring, comments updated, more debug logging added, add a ton of unit tests
* If you do run into an issue, you should be able to fix anything now simply by reindexing (./drivenet-qt —reindex)


### DriveNet-23 -- April 25, 2019

New Stuff:

* "beta" version of **GUI themes**. Settings->Options->Display : Theme (dropdown selection box)
* No need to delete any of your existing data.


### DriveNet-22 -- April 15, 2019

DriveNet-22 and testchain-3. 

We are resetting / starting with a new blockchain. You need to clear out both your DriveNet (~/.drivenet) and testchain (~/.testchain) data directories to use the new version. No sidechains will be active when you first start up DriveNet-qt.

* Sidechain activation period lowered to 256 blocks with a maximum failure count of 64; for faster / more testing.

Bug fixes and improvements to BMM including:

* Add 4 bytes of the previous sidechain block hash to BMM request. In addition to the sidechain number and some identifying bytes, BMM requests now include 4 bytes of the previous sidechain block hash.
* Add optional signalling of WT^ hash in sidechain block headers. Added a WT^ hash field to sidechain block headers, for signalling the current WT^ that the mainchain should be voting on.
* Fixed issue where BMM / critical data transaction fee outputs were not being collected by the miner. If you mine a block that includes these transactions, you will receive the fees at the same address as the coinbase payout.
* Fixed issue with depositing to a sidechain after a WT^ payout has happened on that sidechain. Fix WT^ spend tracking, update CTIP properly. 


### DriveNet-21 -- April 8, 2019

Bugfixes and Cleanup

### DriveNet-20 -- Mar 23, 2019

Bugfixes

### DriveNet-19 -- Mar 22, 2019

* The testchain sidechain has activated -- its binary (testchain-1.01.00) is on the google drive.
* Please make sure you update to the new version of DriveNet and testchain before trying to deposit to the new sidechain. 
* You do not need to delete any of your drivenet data, but you should delete your ~/.testchain folder if you have one.

Thank you to everyone who mined and provided data / logs during the process! 

### DriveNet-18 -- March 14, 2019

Whats new:
* GUI: Add comma separation to amount fields
* GUI: Reorganize sidechain page
* Other small gui fixes

### DriveNet-17 -- Mar 11, 2019

Hey everyone! We have a new version of DriveNet with a lot
of upgrades ready. There's also a new version of the 
sidechain template which has been renamed from "sidechain one"
to "testchain". We're starting with a new blockchain so you'll need
to clear out all of your old data. 

The sidechain management page (where you can propose a 
new sidechain or ACK / NACK current sidechain proposals) 
has been overhauled so it should be less confusing to create
a new sidechain or activate one that someone else has
proposed.

There's more to come but this release has a ton of bug fixes,
refactoring and improvements to test out. There are more
bugs to fix but overall this version brings us very close to a
final result (whatever that means for software that is never
finished). We have more (mostly GUI) improvements to
add but I think we can release something "finished" really soon.

At some point we should cooperate in the telegram to
activate the testchain sidechain. If many of us are mining
and ACK/NACKing the sidechain it should be an interesting test. 

What's new:
* Improvements to sidechain control page (create new sidechains, ACK new)
* No longer depend on the wallet code to watch sidechain addresses.
* Simplified receive page
* Add comma separators to amount fields on testchain sidechain
* Other GUI improvements

Bug fixes:
* Fix reindex bug that some people had when enabling txindex 
* Fix BMM change maturity bug
* Copy bug fix a8b5d20f4f171828b2bd70ab2405c42b1e452e5b from upstream
* Fix WT^ creation bug
* Fix SCDB WT^ tracking bugs
* Fix sidechain activation bugs



### DriveNet-15 -- Jan 9, 2019

This update includes:
Sidechain miner dialog (sidechain
activation & other settings) GUI 
improvements. 

Sidechain activation bug fixes

You don't need to clear out your
data directory or anything else, 
just start using the new binary.

### DriveNet-14 -- Jan 3, 2019

This version has added basic GUI control of sidechain activation
& voting. On the sidechain tab you will now see a "manage" 
button. Clicking "manage" will show a new window where 
miners can propose new sidechains, decide which  sidechains
to signal activation for, and generate configuration files for the
mainchain and any sidechains.

You don't need to clear out your data directory, just start running
the new version.