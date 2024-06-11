# Node_fb2kRichPresence

## Result

![image](https://imgur.com/ctPTIpW.png)

`Play on Youtube` → The YouTube URL of the currently playing song  
`View Channel Link` → The channel URL of the currently playing song  

## Installation

### Clone this repository

```bash
git clone https://github.com/shirafukayayoi/Node_fb2kRichPresence
```

### Install the foobar2000 plugin

[Download nowplaying2](https://github.com/foxx1337/foo_nowplaying2/releases/tag/v4.2)  
After downloading, go to `File` → `Preferences` → `Tools` → `Now Playing 2` and set the format as follows:

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

Configure the file settings accordingly.

[Download YoutubeSource](https://fy.3dyd.com/download/)  
After downloading, go to `File` → `Preferences` → `Tools` → `Youtube Source`, and under `Maintenance`, input your YouTube API key.  
For Japanese users, you can refer to my past article [note-foobar2000のすゝめ【フリーソフト/音楽プレイヤー】](https://note.com/shirafuka_yayoi/n/n92af2e5c4673?from=notice) for more details.  
Then, enjoy music by going to `File` → `YoutubeSource`.

[Download Playback Statistics](https://www.foobar2000.org/components/view/foo_playcount)  
This will allow you to display the playback count.

### Install the packages

```bash
npm install
```

### Modify index.js

In the part `const nowPlayingFilePath`, input the directory of the text file set with **Now Playing 2**.

### To display as 'Now Playing', install Vencord

Install [Vencord-foobar](https://github.com/tunip3/Vencord-foobar/tree/main) by running the following in PowerShell:

```text
Invoke-Expression (Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/tunip3/Vencord-foobar/main/Install-RicherCider.ps1' -UseBasicParsing).Content
```

### Execute!

`node index.js`

## Known Issues

- Album art for local files is not displayed on Discord.
![image](https://i.imgur.com/6w6LD8O.png)
- If playback starts from the middle of a song, the progress bar and time will be out of sync.

*This readme converts Japanese using ChatGPT.
