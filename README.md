# Marmot Tunnel

Welcome in the home of to the Marmot Tunnel application. This application is designed for our students to be able to connect to our Labs for their course practical exercises, challenges, or final projects. Best of luck in your learning!

## Before you begin

The application comes with some basic prerequisites in order perform the connection to our lab. These are: the dotnet runtime version 9.0, and the azcli utility.

To make it easy for you, grab it all with the following PowerShell script:

```PowerShell
# Install dotnet runtime
Start-BitsTransfer -Source "https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/9.0.12/windowsdesktop-runtime-9.0.12-win-x64.exe" -Destination "$HOME/dotnet-runtime-9.0.12-win-x64.exe"
cd $HOME
.\dotnet-runtime-9.0.12-win-x64.exe

# Install azcli utility
Invoke-WebRequest -Uri https://aka.ms/installazurecliwindowsx64 -OutFile .\AzureCLI.msi
.\AzureCLI.msi
```

## Get Marmot Tunnel locally

```PowerShell
# In case of any errors, retry running the commands
# Download the repo contents to C:\azrez and expand the archive
Start-BitsTransfer -Source "https://github.com/lesformidables/marmot-tunnel/archive/refs/heads/main.zip" -Destination "C:\marmot.zip"
Expand-Archive -Path "C:\marmot.zip" -DestinationPath "C:\" -Force
# Edit the path name and remove the initial compressed file
# Add to environment variables for the current PS session only
$env:Path += ";C:\marmot\"
```

## Limitations

The application only supports Windows OS in the current release. There are plans in our roadmap to extend it for Linux / MacOS as well.
