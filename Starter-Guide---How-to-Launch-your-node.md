Block explorer: [https://explorer.alephium.org](https://explorer.alephium.org)

# Requirement

1. Ensure that Java is installed on your computer: [https://java.com/](https://java.com/).
2. (Windows only) Install [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701)
3. In your home folder:
   - Windows: `C:\Users\<your-username`
   - MacOS: `/Users/<your-username`
   - Linux: /home/<your-username>
 Create a folder called **.alephium** and
 Make sure to show the hidden folders:
 - [on Windows](https://support.microsoft.com/en-us/windows/view-hidden-files-and-folders-in-windows-97fbc472-c603-9d90-91d0-1166d1d9f4b5)
 - [on MacOS](https://www.pcmag.com/how-to/how-to-access-your-macs-hidden-files)
4. (Windows only): You will need to add one `Environment variables`
  * For this you can follow: [This guide](https://java.com/en/download/help/path.html) and follow the `Windows` section
  * You can add the two following variables in your user's variables:
      - Click `New`
      - In the variable name type `HOME`
      - In the variable value: `C:\Users\<your-user-name>`

# Download JAR
Download the executable file [alephium-1.0.0.jar](https://github.com/alephium/alephium/releases/download/v1.0.0/alephium-1.0.0.jar) (once it is downloaded, do not double click on it, it can not be launched this way).
Move the **alephium-1.0.0.jar** file in the **.alephium** folder.
If you’re on Mac, you might need to allow apps from unidentified devs, you can find how-to online.

# Start your node

1. Open the search and type in `Terminal` (for Mac) or `Windows Terminal` (for  Windows).

2. Open the Terminal/Command Line program and navigate to the **.alephium** folder.

* Type `ls` and press Enter to list the folders on your computer.

* Navigate to the **.alephium** folder by typing `cd FolderName` to enter the folder in which the **.alephium** folder is saved. Please note that the **.alephium** folder is hidden so you won’t see it in the directory if you didn't executed step 3 of the requirements.

* Type `cd .alephium` to enter the folder.

3. Type the command `java -jar -Xmx500m alephium-1.0.0.jar` in the terminal and press Enter.

_**Tada your node is running**_

* Your node will start to sync with the network, it might be long the first time.
* Open [http://127.0.0.1:12973/docs](http://127.0.0.1:12973/docs) to see all interactions you can have with the node.
* If you close the terminal the node will be turned off.

# Future

Stay tuned for future release, you might need to download a new jar, to update your `bootstrap` addresses in your `user.conf` and delete the `db` folder in your `.alephium` folder.
