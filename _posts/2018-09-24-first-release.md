---
title: Drivechain Release Announcement
show_author: true
comments: true
date: 2018-09-24 4:00:00
---

## Announcement

I am happy to announce **the first Drivechain release!!**

The release is in two parts:

1. Bitcoin Core 16.99, [modified to support drivechain technology](https://github.com/drivechain-project/diff).
2. Bitcoin Core 16.99, modified to be a vanilla, minimalist, 'blank' sidechain. It is a very boring sidechain, whose capabilities are the same as Bitcoin Core's.


## Getting the Files

Source code here: https://github.com/DriveNetTESTDRIVE/DriveNet

The binary files (for less-technical users) are hosted on Google Drive: **[https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT](https://drive.google.com/drive/folders/1o83i1N4yPbbKT5hVv_IspNVwHV2jUUoT)**

![image](/media/post1/dl-1.png)

![image](/media/post1/dl-2.png)

After getting the files, **[check out the usage tour](/blog/usage-tour/)** to take the software for a spin and see what it can do!

## Other Features

This release has some additional characteristics: 

1. New PoW algorithm (with reset difficulty).
2. UTXO loader -- this is much faster than doing an initial chain-sync. And it also lets us very easily release other versions (BCH, BTG, etc). Finally, it lets us easily mint our own testnet coins.
3. One-way replay protection -- the best of both worlds, this setup grants permanent replay protection to UTXOs once they *as they are used*, but not before. It is user-based, not 'time of fork'-based.


## Work in Progress

TESTDRIVE is our first drivenet TEST release. It certainly isn't perfect. We are still working on it.

Nonetheless, it's good to be able to show people what exactly Drivechain does: it allows Bitcoin to travel among different pieces of software.

## Implications

If this "multi-network coin" idea is found to be viable, it has profound implications for the crypto's most salient problems. **Bitcoin would be able to copy, without controversy, any technology**, including: larger blocks, Turing-completeness, and ring signatures.

As a result:

* There would be no need to fight about which features Bitcoin "should" have (or over which features "define" Bitcoin).
* Technologists would be free to build interesting blockchain technology and add it to Bitcoin, without going through the arduous/political review process.
* The "base layer" would be free to quickly ossify and stabilize, adding security.

Thank you!
