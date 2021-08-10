NOTE: Please keep in mind we are currently running on our testnet, as a result, we regularly update our testnet and potentially wipe out existing history.

Block explorer: [https://testnet.alephium.org](https://testnet.alephium.org)

# Download JAR

1. Ensure that Java is installed on your computer: [https://java.com/fr/](https://java.com/fr/).

2. Download the executable file [alephium-0.8.9.jar](https://github.com/alephium/alephium/releases/download/v0.8.9/alephium-0.8.9.jar) (once it is downloaded, do not double click on it, it can not be launched this way).
If you’re on Mac, you might need to allow apps from unidentified devs, you can find how-to online.

3. In your home folder (or any folder of your choice), create a folder called **.alephium** and move the **alephium-0.8.9.jar** file in the **.alephium** folder.

# Configure your node

1. In the .alephium folder create a new text file named user.conf and in the file copy and save the following text: 

alephium.network.network-type = "testnet"

alephium.discovery.bootstrap = ["3.68.2.201:9973", "34.236.121.90:9973", "54.252.31.241:9973"]


2. Make sure to change the format of the text to plain text (Format -> Make plain text).
When you save the file, make sure the extension of the file is .conf (and not .conf.txt). 
It might only be possible to save the file with the extension.conf.txt. If it is the case, rename the file directly from the folder as user.conf and when asked, choose to save with the .conf extension only.

NOTE: If you are upgrading from a previous release, please ensure the folder .alephium is clean of any `db-*` folders

# Start your node

1. Open the search and type in _Terminal_ (for Mac) or _Command_ (for  Windows).

2. Open the Terminal/Command Line program and navigate to the **.alephium** folder. 

* Type ls and press Enter to list the folders on your computer. 

* Navigate to the **.alephium** folder by typing `cd FolderName` to enter the folder in which the **.alephium** folder is saved. Please note that the **.alephium** folder is hidden so you won’t see it in the directory.

* Type `cd .alephium` to enter the folder.

3. Type the command `java -jar -Xmx500m alephium-0.8.9.jar` in the terminal and press _Enter_. 

_**Tada your node is running**_

If you close the terminal the node will be turned off.

NOTE: On Windows, it might make sense to download and use Windows terminal instead of Command Line in order to display the logs in a more readable manner.
