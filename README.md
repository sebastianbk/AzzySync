AzzySync (v1.01)
========

Command line tool to sync local folders with Azure blob storage. Right now this just does a one-way sync from a local folder into an Azure blob storage container.

Update (June 17, 2014)
========

After constantly getting the *No valid combination of account information found* error, I forked to this to update the way of connecting to Azure blob storage. This also means that this client will always run over HTTPS.

Example
========

This example works in a PowerShell console:

 1. Sync *C:\Misc\Screenshot\* to Azure blob storage: 
    
    ```PowerShell
    .\AzzySync.exe s /containerName:screenshots /localPath:"C:\Misc\Screenshot\" /accountname:"YOUR_STORAGE_ACCOUNT_NAME" /accountkey:"YOUR_STORAGE_ACCOUNT_KEY"
    ```

Get command line help
========
```PowerShell
.\AzzySync.exe /?
```

Output: 
```
   sync|s: Performs a one way sync of files from a local folder to an Azure blob storage container.
        /accountkey    : Account key for the Azure blob storage account. (String)
        /accountname   : Account name for the Azure blob storage account. (String)
        /containername : Name of the blob storage container. (String)
        /forcereupload : Forces re-upload all files from local dir to blob storage. This bypasses the hash calculation/check to see if a file has changed. (Default = False)
        /localpath     : Path of local folder to sync to blob storage. (String)

   Global Parameters:
        /debug     :
        /debugmode :
        /help|h|?  : Help
```