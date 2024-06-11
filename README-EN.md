# Node_fb2kRichPresence

[English README](README-EN.md)

## Execution Result

![image](https://imgur.com/ctPTIpW.png)

`Play on Youtube` → The Youtube URL of the music you are listening to  
`View Channel Link` → The Channel URL of the music you are listening to  

## Installation

### Clone this repository

```bash
git clone https://github.com/shirafukayayoi/Node_fb2kRichPresence
```

### Install the foobar2000 plugin

[Download nowplaying2](https://github.com/foxx1337/foo_nowplaying2/releases/tag/v4.2)  
After downloading, go to `file` → `Preferences` → `Tools` → `Now Playing 2` settings, and set the Format to:

```text
%title%$char(10)
%artist%$char(10)
%length%$char(10)
%fy_url%$char(10)
%fy_channel_url%$char(10)
%fy_thumbnail_url%$char(10)
%album%$char(10)
%play_count%$char(10)
%albumarturl%
```

Then, set the File path.

[Download YoutubeSource](https://fy.3dyd.com/download/)  
After downloading, go to `file` → `Preferences` → `Tools` → `Youtube Source` settings, and enter the Youtube API in `Maintenance`.  
Japanese users can refer to the article [note-foobar2000のすゝめ【フリーソフト/音楽プレイヤー】](https://note.com/shirafuka_yayoi/n/n92af2e5c4673?from=notice) written by the author.  
After that, enjoy music from `File` → `YoutubeSource`.

[Download Playback Statistics](https://www.foobar2000.org/components/view/foo_playcount)  
By installing this, you can display the play count.

### Install the packages

```bash
npm install
```

### Modify index.js

Set the directory of the text file configured in **Now Playing 2** in `const nowPlayingFilePath`.

### If you want to create an executable file

You can use nexe to create an executable file.  

```bash
nexe -i index.js -o Node_fb2kRichPresence.exe -t windows-x64-14.15.3
```

### If you want to display while playing, download Vencord

Install [Vencord-foobar](https://github.com/tunip3/Vencord-foobar/tree/main).

```bash
Invoke-Expression (Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/tunip3/Vencord-foobar/main/Install-RicherCider.ps1' -UseBasicParsing).Content
```

Run this in PowerShell.

### Execute!

```bash
node index.js
```

## Known Issues

- Album art is not displayed on Discord for local files.
![image](https://i.imgur.com/6w6LD8O.png)
- If you start playing from the middle, the playback bar and time will be misaligned.

*This readme converts Japanese using ChatGPT.
