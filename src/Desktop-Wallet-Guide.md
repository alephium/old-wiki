# Desktop Wallet Guide

This is the most user-friendly option available for Wallet management. However, some could consider it slightly less privacy-preserving and secure than the node wallet as it requires you to trust the application’s security and is by default connected to a public node. However, you have the possibility to build the wallet directly from our Github repository and to use a local node or even create your wallet completely offline to mitigate some of these risks.

## Step-by-step intructions to install the Desktop Wallet

- Go to the [Release Page on GitHub](https://github.com/alephium/alephium-wallet/releases)
- Download the executable file in line with your set-up (MAC, WINDOWS, Linux). Alternatively, if you wish and are comfortable with coding, you can build the wallet directly from our [Github repository](https://github.com/alephium/alephium-wallet). If you're struggling with this, don't hesitate to contact us on Discord. 
- Double click on the file you've downloaded to install it.
- On Linux and Windows, double click on the application to launch the Desktop wallet. 
- On Mac, you'll need to go to the Application folder, click right on the Alephium app and then click on Open (don't double click, as the application isn't signed yet, it won't work).
- By default, the wallet will be connected to the Alephium public node (please note that your mnemonic or your private key will never be uploaded to the public node). Should you want to use your personal node or generate the wallet offline, you can do so by clicking the setting wheel on the top right of the app and changing the Node Host to your localhost or simply leave it blank to create the wallet offline. 
- Click on Create/Import a wallet, then Click New wallet.
- Choose an account name. You might want to choose a name that allows you to identify your wallet easily. 
- Pick a password to protect your wallet on your computer. This password does not replace your wallet's 24 Secret Words. It is only used to log in and out of the created wallet easily.
- Click Continue.
- You now see your new wallet's information 🎉 
- Your address is a long string of characters. It is what identifies your wallet on the alephium network.
- In the highlighted box, you will see 24 words. These are your wallet's  24 secret words. This is your most precious piece of information, and you must store it wisely, safely, and carefully.
- Copy and store your 24 secret words safely on several offline mediums such as paper and metal and store them in different places. 
- You will now be asked to verify that you got the 24 Secret words right by listing the words in the correct order. Click Ready! And reenter the words with the selection box.
- When all the words are in the correct order, you will be prompted visually to continue.
- Everything is ready! Your wallet is now created (and you've made sure to save your 24 words). 
- To see your public address again, click on “Show address,” copy the string of characters and send it to us by email (Please make sure to use the same email you've listed in your contract). 

## Creating a mining wallet with 4 addresses

A mining wallet is slighlty different in that it needs to have one address per group. Currently Alephium is running 4 groups meaning there is a needed total of 4 addresses. The Desktop wallet can do this for you.

To do this, simply unfold the "Advanced Settings"

## UTXO consolidation

Due to the nature of UTXO, everytime a transaction is made a couple of new Unspet Transaction Outputs are created, each containing various amounts of ALPH. If these UTXOs aren't consolidated every now and then, a UTXO can reach a point where it becomes so called "dust". Meaning that if the amount in a UTXO is smaller than the cost of GAS to send the ALPHs it contains, these ALPHs cannot me moved anymore. To make sure this doesn't happen, the wallet allows you to easily consolidate your UTXOs with the click of a button.