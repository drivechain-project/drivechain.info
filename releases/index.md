---
layout: page
title: Releases
---


## Version 30 -- Latest Version (Feb 25, 2020)!!

### What's New?

Mainchain ("DriveNet 0.30.00"): 

 * Fully backwards compatible -- (would sync with Bitcoin Core 0.12.0 [for example], if 0.12 had our genesis block)
 * NODE_DRIVECHAIN signaling / service flag 
 * Overview page now has a "More" frame, and a "sidechain status"
 * * click on a wt^ to go to the WT^ table
 * No "loaded coins" -- fresh blockchain, new genesis block. 

Sidechain ("TestChain 4.00.00"): 

* All BMM checks now enabled by default
 * testchaind handles disconnections the same way as Qt (checks for mainchain connection in a few different places)
* Refactoring of BMM block creation
* Refactoring of sidechain client / refreshbmm RPC

### **Binaries (Linux Only)**

* On [Google Drive](https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT)


### Sha256

    drivechain-0.30.00-x86_64-linux-gnu.tar.gz
    d10c52613d1c4e5d85277244956bdcbd3be040202d022bec207d4dc4a85a5eb4

    testchain-4.00.00-x86_64-linux-gnu.tar.gz
    7cee6f6757f1004776f66d3adec4b8b20b670ff14a1495c4277027d85b8f2a29


### **Source**

* [DriveNet](https://github.com/drivechain-project/mainchain/)
* [TestChain](https://github.com/drivechain-project/sidechains)
* [Integration Script](https://github.com/CryptAxe/DriveChainIntegration) -- will clone, build, and run DriveNet; then activate a sidechain, then deposit to and withdraw from the sidechain. [Video](https://drive.google.com/open?id=1BwSFmXWPLvGyrWP_zo3ZCivqxDvwlZbe).

### Block Explorer

* [Explorer.Drivechain.Info](http://explorer.drivechain.info/)

### How to Run

1. Delete old data directories if you have any (~/.drivenet, ~/.testchain).
2. Download drivechain-0.30.00-x86_64-linux-gnu.tar.gz, verify sha256, extract.
3. Run! (/bin/drivenet-qt)
4. Download testchain-4.00.00-x86_64-linux-gnu.tar.gz, verify sha256, extract.
5. Run! (/bin/testchain-qt)

For more details, see the [**Usage Tour**](http://www.drivechain.info/blog/usage-tour/) and [**Creating a Sidechain**](http://www.drivechain.info/blog/adding-a-sidechain/), and other [**Articles**](http://www.drivechain.info/archive/).


<!--

1. Delete old data directories if you have any (~/.drivenet, ~/.testchain).
2. Download drivechain-0.30.00-x86_64-linux-gnu.tar.gz, verify sha256, extract.
3. Start DriveNet-30. It will create some directories, give an error message about loaded coins, then exit.
4. Download loaded_coins_590000.tar.gz, verify sha256, extract.
5. Move loaded_coins_590000.dat to ~/.drivenet/loaded_coins.dat
6. Start DriveNet-25 again. It will install the UTXO set into your node (~10 minutes).

Feel free to [ask for testcoins](www.t.me/DcInsiders), or start mining to collect coins.

-->

### How to Mine

Please use the updated BMM documentation if you'd like to set up BMM mining once the testchain sidechain has been activated. 
https://github.com/drivechain-project/docs/blob/master/BMM.md



## FAQ

### Why is this on Google Drive?

Because we also host a 4 GB file (of BTC's UTXOs) there, for "importing".

This is new/unstable software -- assume that it is a virus that will set your computer on fire and then steal your BTC. At first, you should only be running it in Qubues / VirtualBox etc.


## Selected Release Notes

### DriveNet30 -- February 25, 2020

Mainchain ("DriveNet 0.30.00"): 

 * Fully backwards compatible -- (would sync with Bitcoin Core 0.12.0 [for example], if 0.12 had our genesis block)
 * NODE_DRIVECHAIN signaling / service flag 
 * Overview page now has a "More" frame, and a "sidechain status"
 * * click on a wt^ to go to the WT^ table
 * No "loaded coins" -- fresh blockchain, new genesis block. 

Sidechain ("TestChain 4.00.00"): 

* All BMM checks now enabled by default
 * testchaind handles disconnections the same way as Qt (checks for mainchain connection in a few different places)
* Refactoring of BMM block creation
* Refactoring of sidechain client / refreshbmm RPC


### DriveNet29 -- November 26, 2019


Here is a pull request of all v28 --> v29 changes: https://github.com/drivechain-project/mainchain/pull/2


* Refactoring and bug fixes for WT^ workscore calculation. 
* Save custom WT^ voting setting to disk so you don't have to set them again after restart
* New RPC commands for showing WT^(s) which have been approved and paid out, as well as interacting with WT^ votes: listspentwtprimes, listwtprimevotes, setwtprimevote, clearwtprimevotes
* Add WT^ vote table model & view to GUI so that you can view and set WT^ votes via GUI
* Move optional and required Drivechain .dat files to "datadir/drivechain" subdirectory for cleaner more organized datadir
* Add spent WT^ cache to SCDB and persist on disk
* Fix WT^ spending bug when blocks are disconnected / reorged.


### DriveNet28 -- October 23, 2019

New version of DriveNet (and the testchain sidechain) are ready for you guys to use!

The newest version of DriveNet is drivenet-0.28.06 (we had 6 revisions of this release during the testing process)

You'll need to delete your data directories for this new release as we are starting with a new genesis block. Save your loaded_coins.dat file if you don't want to re-download it though as we are using the same loaded coins snapshot.


There are a ton of changes in this release. Check out the commit lists:

* Mainchain commits: https://github.com/drivechain-project/mainchain/commits/master
* Sidechain commits: https://github.com/drivechain-project/sidechains/commits/testchain


#### a. Code Has Moved

* All drivechain code is now at https://github.com/drivechain-project.


#### b. Mainchain GUI changes

* Add sidechain fee warning & sidechain deposit confirmation pop up window
* Set default WT^ vote from sidechain page
* Add note about abandoned sidechain deposits to the transactions table
* Require manually setting a fee for sidechain deposits


#### c. Mainchain updates

* Add formatted CTIP amount to listsidechainctip RPC
* Refactor and update ConnectBlock WT^ spending code
* Added some more logging outputs
* Add getscdbhash & gettotalscdb hash RPC commands for debugging and integration testing script purposes
* Automatically abandon expired BMM request from the wallet after they are removed from your mempool
* Automatically abandon failed sidechain deposits after they are removed from your mempool


#### d. Mainchain bug fixes

* Sidechain database (SCDB) block disconnection bug fixes
* Add complete SCDB::Undo function that can handle various edge cases and make sure that SCDB is re-synchronized after a block is disconnected.
* Fix SCDB reindex edge case bugs
* Sidechain proposal miner code fixes & updates
* Fix CTIP updates when a block is disconnected
* Fix deposit ordering bugs when loading from deposit cache
* Loaded coins bug fixes, refactoring, cleanup
* Remove a LOCK that shouldn't have been there (caused miner bugs)
* Don't signal RBF for BMM requests 
* Fix fee & input selection / calculation bugs for sidechain deposit wallet code
* Fix miner WT^ spend bug at the end of a WT^ verification period that would have the miner spend a WT^ after it has expired - resulting in their block being rejected as invalid even by their own node.


#### e. Sidechain GUI changes

* Add a basic version of "train schedule" to the sidechain page which gives an estimate of when the next WT^ will be created if there are pending withdrawals
* If the connection to mainchain fails show an error message. If the user doing BMM on the sidechain then disable networking until the mainchain connection is restored

#### f. Sidechain updates

* Sidechain nodes create WT^(s) in a deterministic way and other sidechain nodes can replicate and verify new WT^(s). The function VerifyWTPrimes() has been added for this purpose.


#### g. Sidechain bug fixes

* Refactoring of WT^ transaction creation
* Fix CTIP payout amount bugs on sidechain
* Refactor / new version of deposit sorting & payout calculation
* Fixes and refactoring of deposit payout transaction code
* Check more frequently on the mainchain connection
* Some RPC function param names corrected
* Fix WT ldb ID uniqueness bug - if a wt duplicated both mainchain destination and amount - leveldb would overwrite the older entry. 



### DriveNet25 -- August 20, 2019

BTC UTXOs shapshot at block #590,000. In many ways, this software acts as if it hard forked from BTC on August 14th. [Ask us](http://www.t.me/DcInsiders) for testnet coins!

* New integration script: https://github.com/CryptAxe/DriveChainIntegration
* * Just run ./drivechainintegration.sh , and the script will clone, build, and then run DriveNet, activate a sidechain, deposit to and withdraw from the sidechain. It's just a basic test for now, and the script could use some refactoring already but if you're feeling adventurous you can give it a try. You'll need all of the bitcoin dependencies as this will actually compile the software. I have them listed here: https://github.com/CryptAxe/Setup/blob/master/setup.sh
* Major improvements to sidechain template. To make it easier for other people to create new sidechains.
* Superior automation -- nearly everything is exposed to the RPC / CLI interfaces now. Previously, most drivechain specific functions were all only accessible via GUI.
* BMM code has been refactored
* Mainchain WT^ voting is accessible to GUI and RPC, which should be available in a next release on this same chain.
 * Refactored code that was caching WT^(s) on the sidechain and turned it into a more general purpose BMM cache. Now it caches the results of BMM proof validation, and eventually should also cache the results of deposit validation. This saves a ton of local RPC requests depending on your nodes BMM validation settings it could save thousands of requests during a reindex and startup.
* Made BMM validation easily configurable. Previously you would have to actually set values in validation.cpp and re-compile if you wanted to specify the level of BMM validation your node will perform. Now this can be done with these startup params: 
 (-verifybmmcheckblock, -verifybmmreadblock, verifybmmacceptheader)
* * So, for example to run with maximum BMM validation: ./src/qt/testchain-qt —verifybmmcheckblock —verifybmmreadblock —verifybmmacceptheader
* * The same options will be made available for deposit validation soon.
* Fixed a bug with the size of sidechain git commit hashes. Should have been stored / read as uint160 not uint256. (This bug caused the commit hash to actually be wrong if you list active sidechains)


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