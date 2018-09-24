---
title: First Drivechain Release
show_author: true
comments: true
date: 2018-09-24
---

## 1. Announcement

I am happy to announce **the first Drivechain release!!**

The release is in two parts:

1. Bitcoin Core 16.99, [modified to support drivechain technology](https://github.com/drivechain-project/diff).
2. Bitcoin Core 16.99, modified to be a vanilla, minimalist, 'blank' sidechain. It is a sidechain whose capabilities are the same as Bitcoin Core's.



## 2. Getting the Files

Source code here: https://github.com/DriveNetTESTDRIVE/DriveNet

The binary files (for less-technical users) are hosted on Google Drive: **[https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT](https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT)**

![image](/media/post1/dl-1.png)

![image](/media/post1/dl-2.png)


### SHA-256 Hashes

Make sure you've downloaded the files correctly!

    x64
    ------------------
    DriveNet-4-0.21.00-x86_64-linux-gnu.tar.gz
    8AC8B0262F0BAFFF1AD7C30164BAB0D115AF1A483003FA3E12515F0522BE2C30
     
    sidechain-5-0.16.99-x86_64-linux-gnu.tar.gz
    5E6533F59DDB79323BF5FCFABF9232B0CE2363EEA6F1C8A03A9E01D40F9F63F5
     
    x32
    ------------------
    DriveNet-4-0.21.00-i686-pc-linux-gnu.tar.gz
    8E322F855A493275CB404CDE965379671558DE49E592F9857203549AEEBC1A63
     
    sidechain-5-0.16.99-i686-pc-linux-gnu.tar.gz
    5D1E458318FA4C799B81CE92313E7F3E162367AB1F45A77B673A73781711E24E

### Drivenet-BTC vs Drivenet-Blank

If you want to join the same network as CryptAxe and I, you'll need to download our UTXO set (2.0 GiB).

    UTXO torrent file
    ----------------------
    DriveNetLoadedCoinsV1.tar.gz.torrent
    7B633ACE5C5FDD50EA3BB3C0F35ED2FCBD527E2553E41B5133D0DA3A7BF614A1
     
    loaded_coins.dat
    0a5ddf44ec2620d7103111da3b7412cbe3f3385edd1a9c9f0eb9292f01e4840f

It's the July 30th UTXO set from the BTC network at [block 534,444](https://www.blockchain.com/btc/block/00000000000000000012ff6b14f186d7b7c41d8e585a40d79f1164dcd92f8b36). Uncompressed, it is 4.8 GB.

Alternatively, you can just join the Blank Network. It doesn't load any UTXOs, so it is is more like a testnet or fresh new altcoin.

In the near future, we plan to release a "Drivenet-BCH" that has the Bitcoin Cash UTXO set.


## 3. Step-by-Step Tour

Up to date as of 24 Sept 2018.

Here I present a visual guide. It assumes only very basic computer knowledge. 

We will: 

* Send BTC from the mainchain to a sidechain.
* Use the sidechain (send BTC from ourselves to ourselves).
* Send the sidechain-BTC back to the mainchain.

Follow along, and expand each image if you get lost. Or [download all the images](/media/dc-release-images.zip) at once and scroll through them as an album.

### A. Setting Up

First, extract the files:

![image](/media/post1/3.png)

I have put the contents on the Desktop for convenience:

![image](/media/post1/4.png)

![image](/media/post1/5.png)

### B. Importing the UTXOs

First, try to run the Mainchain by entering the Drivenet /bin/ folder:

![image](/media/post1/6.png)

Open a terminal:

![image](/media/post1/7.png)

Start the software by running "./drivenet-qt":

![image](/media/post1/8.png)

Drivenet will create a bunch of files and directories.

But you will get this error message:

![image](/media/post1/9.png)

Time to use the loaded_coins.dat file. Navigate to your newly-created /.drivenet/ folder:

![image](/media/post1/10.png)

Move the loaded_coins.dat file to this directory:

![image](/media/post1/11.png)

Now, rerun by using "./drivenet-qt" in the terminal again:

![image](/media/post1/12.png)

This will load the UTXOs. The very first time, it takes an average computer about 10 minutes. Afterwards it will be instant.

While we are waiting for that, we can at least start up the sidechain.

### C. Starting up 'Sidechain One'

To start up 'Sidechain One', go into the sidechain folder ("/bitcoin-0.16.99/"). And enter the /bin/ directory.

![image](/media/post1/13.png)

Open the terminal again:

![image](/media/post1/14.png)

Run './sidechain-qt':

![image](/media/post1/15.png)

It's online!

![image](/media/post1/16.png)

### D. Sending BTC Main-to-Side

Below, I have arranged the mainchain on the left (in blue) and the sidechain "Sidechain One" on the right (in red):

![image](/media/post1/17.png)

#### i. Getting drivenet-BTC

First, in order to send some BTC, you'll need some BTC to send!

You can get some by:

* Mining some ( Help > Debug window > Console > "setgenerate true"). 
* Asking me for some [in our new telegram group](https://t.me/joinchat/C-POgRCPpB_-ki-csUGE9g).
* NOT RECOMMENDED importing your private key ( Help > Debug window > Console > "import <KEY>") NOT RECOMMENDED

The last method is not recommended, because *you should never type your private key into software, unless you've checked that software very carefully*. Which, at this point, you have not. Furthermore, if you misunderstand how we have implemented replay protection, you may destroy your regular (non-drivenet) BTC funds. 

Don't worry about asking me for BTC. For testing purposes, CryptAxe and I modded the UTXO set to give ourselves 100,000 each. We're loaded! Plus these are useless testnet coins.

Mining should be easy, at first. Although if you do mine, you will probably be unwilling or unable able [to set up blind merged mining](https://github.com/drivechain-project/testing) and so your presence may be somewhat chaotic. But that's what testing is for, I suppose.

Here I assume you just ask for some, but using the "Receive" tab > "Request Payment" > "Copy Address".

![image](/media/post1/18.png)

![image](/media/post1/19.png)

And then I assume you've received 21 BTC.

![image](/media/post1/20.png)

#### ii. Depositing to a Sidechain

On the mainchain (the "DriveNet" window), click the "Sidechains" tab:

![image](/media/post1/21.png)

On the sidechain (the "Sidechain One" window), click the "Parent Chain" tab:

![image](/media/post1/22.png)

Under the "Parent Chain" tab, you'll see a bunch of stuff. You need to get a Deposit address under Transfer > Deposit to Sidechain > Copy.

![image](/media/post1/23.png)

Copy it into the Mainchain's "Sidechain address" field.

![image](/media/post1/24.png)

Enter an amount, and click Deposit:

![image](/media/post1/25.png)

![image](/media/post1/26.png)

Go back to the sidechain "Overview" tab, to wait for your money to arrive.

![image](/media/post1/27.png)

It should show up, as "Immature". Since the coins were created out of nothing, the software classifies these BTC as "mined". We are going to change that to something drivechain-specific soon.


![image](/media/post1/28.png)

![image](/media/post1/29.png)

![image](/media/post1/30.png)

### E. Using the Sidechain

We've now got 15.9999,0880 BTC on "Sidechain One".

![image](/media/post1/31.png)

Let's send it to ourselves, to simulate the act of paying a merchant for a good or service.

![image](/media/post1/32.png)

Get a new address:

![image](/media/post1/33.png)

Send 11 BTC (of our 15.9999,0880) to it:

![image](/media/post1/34.png)

Click "Send", our balance decreases very slightly, to 15.9998,6380, as we paid a transaction fee. See the bottom right corner:

![image](/media/post1/35.png)

Using the "Coin Control" > "Inputs" button, we can see the new 11 BTC UTXO that we paid to the "merchant" (aka ourselves).

![image](/media/post1/36.png)


### F. Sending BTC Side-to-Main

Now, let us imagine that our hypothetical merchant wants to move his BTC from the sidechain back to the mainchain.

On the sidechain, click on the "Parent Chain" tab...

![image](/media/post1/37.png)

...and "Withdraw from Sidechain":

![image](/media/post1/38.png)

On the mainchain, use "Receive" > "Request Payment" > "Copy Address":

![image](/media/post1/39.png)

Paste that withdrawal address into the sidechain's "Withdraw Address" field. 

![image](/media/post1/40.png)

And pick an amount to withdraw, I picked 10.

Then click send:

![image](/media/post1/41.png)

### G. The Slow Return

A key feature of Drivechain is its "slow return" (as it's often phrased):

![image](/media/post1/slow-return.png)

Normally this process would take 3-6 months, but for testing purposes we have dramatically sped it up.

See also: [FAQ Question "I have heard that it will take 3-6 months to transfer money from the sidechain to the mainchain. Won't that be too slow to be useful?""](http://www.drivechain.info/faq/#liquidity)

Nonetheless, this part involves a little bit of waiting.

Back on the mainchain, click the "Sidechains" tab:

![image](/media/post1/43.png)

Cick the "Sidechains WT^(s)" table:

![image](/media/post1/44.png)

After 6 blocks or so, the withdrawal should show up. It will be inside of a "WT^" container.

![image](/media/post1/45.png)

This container will accumulate "ACKs" until it either [a] expires, or else [b] successfully reaches the target value (of 141 in this case).

You can see it has moved from 2 up to 7 here.

![image](/media/post1/46.png)

Now you'll need to waste some serious time. So hit up Reddit and see if there's anything good (or whatever). 

![image](/media/post1/47.png)

![image](/media/post1/48.png)

Looks like I've been reading bitcoin-dev long enough, we now have 143 ACKs. The "Approved" field has switched to "true". This WT^ container transaction can now be included in a mainchain block.

![image](/media/post1/49.png)

My mainchain balance has increased by about 10. It rose from ~5 to about ~15.

![image](/media/post1/49.png)

Let's investigate more carefully using the "Coin Control" > "Inputs" window:

![image](/media/post1/3.png)

We have two UTXOs:

* 5 BTC -- Change from when we sent 16 of our 21 starting BTC to the sidechain.
* 9.98996640 BTC -- the 10 BTC side-to-main transfer, minus various sidechain and mainchain fees.


## Conclusion

TESTDRIVE is our first drivenet TEST release. It certainly isn't perfect. We are still working on it.

Nonetheless, it's good to be able to show people what exactly Drivechain does: it allows Bitcoin to travel among different pieces of software.

If this "multi-network coin" idea is found to be viable, it has profound implications for the crypto's most salient problems. Bitcoin would be able to copy any technology, including: larger blocks, Turing-completeness, and ring signatures.

As a result, there would be no need to fight about which features Bitcoin "should" have (or over which features "define" Bitcoin). Technologists would be free to build interesting blockchain technology and add it to Bitcoin, without going through the conservative review process. And furthermore, the base mainchain "layer-1" would be free to quickly ossify and stabilize.

