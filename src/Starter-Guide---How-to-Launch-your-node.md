Block explorer: [https://explorer.alephium.org](https://explorer.alephium.org)

# Requirements

1. Ensure that Java is installed on your computer: [https://java.com/](https://java.com/).
2. (Windows only) Install [Windows Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701)
3. In your home folder[^1]:
   1. Create a folder called **.alephium**
   2. Make sure to show the hidden folders:
      - [on Windows](https://support.microsoft.com/en-us/windows/view-hidden-files-and-folders-in-windows-97fbc472-c603-9d90-91d0-1166d1d9f4b5)
      - [on MacOS](https://www.pcmag.com/how-to/how-to-access-your-macs-hidden-files)
4. (Windows only): You will need to add one `Environment variables`
   - To do this you can follow the `Windows` section of [this guide](https://java.com/en/download/help/path.html).
   - Add the following two values in your user's variables:
     - Click `New`
     - In the variable name, type: `HOME`
     - In the variable value, enter: `C:\Users\<your-user-name>`

# Download JAR
Download the executable file [alephium-1.1.0.jar](https://github.com/alephium/alephium/releases/download/v1.1.0/alephium-1.1.0.jar) (once it is downloaded, do not double click on it, it can not be launched this way).
Move the **alephium-1.1.0.jar** file in the **.alephium** folder.
If you’re on Mac, you might need to allow apps from unidentified devs, you can find how-to online.

# Start your node

1. Open the search and type in `Terminal` (for Mac) or `Windows Terminal` (for Windows).
2. Open the Terminal/Command Line program and navigate to the **.alephium** folder:
   1. Type `ls` and press Enter to list the folders on your computer.
   2. Navigate to the **.alephium** folder by typing `cd FolderName` to enter the folder in which the **.alephium** folder is saved. Please note that the **.alephium** folder is hidden so you won’t see it in the directory if you didn't executed step 3 of the requirements.
   3. Type `cd .alephium` to enter the folder.
3. Type the following command in the terminal and press Enter:
   ```
   java -jar -Xmx500m alephium-1.1.0.jar
   ```

🎉 _**Tada, your node is running**_

- Your node will start to sync with the network, it might take long the first time.
- Open [http://127.0.0.1:12973/docs](http://127.0.0.1:12973/docs) to see all interactions you can have with the node.
- If you close the terminal the node will be turned off.

[^1]: The home folder depends on your system: `C:\Users\<your-username>` in Windows, `/Users/<your-username>` in macOS, `/home/<your-username>` in Linux.
