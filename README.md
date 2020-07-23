# Install G-Drive CLI

**To install G-Drive CLI:**

**1.** Login as root<br>
**2.** Copy these Lines and Paste into Terminal
```bash
curl -sSL https://git.io/JJZnz | bash
```

<b>Or,</b>


```bash
wget https://github.com/cachecleanerjeet/install-gdrive-cli/raw/master/install.sh
chmod +x install.sh
bash install.sh
```
------------

**You will get Output Like this:**
```bash
root@tuhin:~$ bash install.sh
--2020-07-12 15:45:19--  https://github.com/cachecleanerjeet/install-gdrive-cli/raw/upload/gdrive
Resolving github.com (github.com)... 13.229.188.59
Connecting to github.com (github.com)|13.229.188.59|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://raw.githubusercontent.com/cachecleanerjeet/install-gdrive-cli/upload/gdrive [following]
--2020-07-12 15:45:20--  https://raw.githubusercontent.com/cachecleanerjeet/install-gdrive-cli/upload/gdrive
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.0.133, 151.101.64.133, 151.101.128.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|151.101.0.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9039026 (8.6M) [application/octet-stream]
Saving to: ‘gdrive’

gdrive    100%  [======================================>]   8.62M  --.-KB/s    in 0.1s

2020-07-12 15:45:20 (90.4 MB/s) - ‘gdrive’ saved [9039026/9039026]

Successfully Installed GDrive CLI
Visit https://tu.hin.life
```


------------

## Examples
#### List files
```
$ gdrive list
Id                             Name                    Type   Size     Created
0B3X9GlR6EmbnZ3gyeGw4d3ozbUk   drive-windows-x64.exe   bin    6.6 MB   2015-07-18 16:43:58
0B3X9GlR6EmbnTXlSc1FqV1dvSTQ   drive-windows-386.exe   bin    5.2 MB   2015-07-18 16:43:53
0B3X9GlR6EmbnVjIzMDRqck1aekE   drive-osx-x64           bin    6.5 MB   2015-07-18 16:43:50
0B3X9GlR6EmbnbEpXdlhza25zT1U   drive-osx-386           bin    5.2 MB   2015-07-18 16:43:41
0B3X9GlR6Embnb095MGxEYmJhY2c   drive-linux-x64         bin    6.5 MB   2015-07-18 16:43:38
```

#### List largest files
```
$ gdrive list --query "name contains 'gdrive'" --order "quotaBytesUsed desc" -m 3
Id                             Name                     Type   Size     Created
0B3X9GlR6EmbnZXpDRG1xblM2LTg   gdrive-linux-mips64      bin    8.5 MB   2016-02-22 21:07:04
0B3X9GlR6EmbnNW5CTV8xdFkxTjg   gdrive-linux-mips64le    bin    8.5 MB   2016-02-22 21:07:07
0B3X9GlR6EmbnZ1NGS25FdEVlWEk   gdrive-osx-x64           bin    8.3 MB   2016-02-21 20:22:13
```

#### Upload file
```
$ gdrive upload gdrive-osx-x64
Uploading gdrive-osx-x64
Uploaded 0B3X9GlR6EmbnZ1NGS25FdEVlWEk at 3.8 MB/s, total 8.3 MB
```

#### Make directory
```
$ gdrive mkdir gdrive-bin
Directory 0B3X9GlR6EmbnY1RLVTk5VUtOVkk created
```

#### Upload file to directory
```
$ gdrive upload --parent 0B3X9GlR6EmbnY1RLVTk5VUtOVkk gdrive-osx-x64
Uploading gdrive-osx-x64
Uploaded 0B3X9GlR6EmbnNTk0SkV0bm5Hd0E at 2.5 MB/s, total 8.3 MB
```

#### Download file
```
$ gdrive download 0B3X9GlR6EmbnZ1NGS25FdEVlWEk
Downloading gdrive-osx-x64 -> gdrive-osx-x64
Downloaded 0B3X9GlR6EmbnZ1NGS25FdEVlWEk at 8.3 MB/s, total 8.3 MB
```

#### Share a file
```
$ gdrive share 0B3X9GlR6EmbnNTk0SkV0bm5Hd0E
Granted reader permission to anyone
```

#### Pipe content directly to google drive
```
$ echo "Hello World" | gdrive upload - hello.txt
Uploading hello.txt
Uploaded 0B3X9GlR6EmbnaXVrOUpIcWlUS0E at 8.0 B/s, total 12.0 B
```

#### Print file to stdout
```
$ gdrive download --stdout 0B3X9GlR6EmbnaXVrOUpIcWlUS0E
Hello World
```

#### Get file info
```
$ gdrive info 0B3X9GlR6EmbnNTk0SkV0bm5Hd0E
Id: 0B3X9GlR6EmbnNTk0SkV0bm5Hd0E
Name: gdrive-osx-x64
Path: gdrive-bin/gdrive-osx-x64
Mime: application/octet-stream
Size: 8.3 MB
Created: 2016-02-21 20:47:04
Modified: 2016-02-21 20:47:04
Md5sum: b607f29231a3b2d16098c4212516470f
Shared: True
Parents: 0B3X9GlR6EmbnY1RLVTk5VUtOVkk
ViewUrl: https://drive.google.com/file/d/0B3X9GlR6EmbnNTk0SkV0bm5Hd0E/view?usp=drivesdk
DownloadUrl: https://docs.google.com/uc?id=0B3X9GlR6EmbnNTk0SkV0bm5Hd0E&export=download
```

------------


This GDrive is configured using my ClientId & ClientSecret. So, you will get a Not Verified App Prompt.<br>

To configure using your own ClientId & ClientSecret, Read the article:<br>
https://www.mynotepaper.com/mount-google-drive-using-gdrive-on-linux-server-with-own-oauth-credentials


