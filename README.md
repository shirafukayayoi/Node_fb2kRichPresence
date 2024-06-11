# Node_fb2kRichPresence

[English README](README-EN.md)

## 実行結果

![image](https://imgur.com/ctPTIpW.png)

`Play on Youtube` → 聞いている音楽のYoutubeURL  
`View Channel Link` →今聞いている音楽のChannelURL  

## インストール方法

### このリポジトリをcloneします  

```git clone https://github.com/shirafukayayoi/Node_fb2kRichPresence```

### foobar2000のプラグインを入れる

[nowplaying2のダウンロード](https://github.com/foxx1337/foo_nowplaying2/releases/tag/v4.2)  
ダウンロード後、`file`→`Preferences`→`Tools`→`Now Playing 2`の設定まで行き、Formatに  

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

と入れ、Fileの設定を行う。  

[YoutubeSourceのダウンロード](https://fy.3dyd.com/download/)  
ダウンロード後、`file`→`Preferences`→`Tools`→`Youtube Source`の設定に行き、`Maintenance`にYoutubeのapiを入れる。  
日本人の方は自分が過去に書いた[note-foobar2000のすゝめ【フリーソフト/音楽プレイヤー】](https://note.com/shirafuka_yayoi/n/n92af2e5c4673?from=notice)を読んでみてほしい。  
その後、`File`→`YoutubeSource`から音楽を楽しむ。

[Playback Statisticsのダウンロード](https://www.foobar2000.org/components/view/foo_playcount)  
これを導入することで、再生回数の表示が可能になる。

### パッケージのインストール

```npm install```

### index.jsの変更

`const nowPlayingFilePath`の部分に、**Now Playing2**で設定したテキストファイルのディレクトリを入れる。

### exe化したい場合

nexeを使ってexe化することができます。  

`nexe -i index.js -o Node_fb2kRichPresence.exe -t windows-x64-14.15.3`

### 再生中の表示にしたい場合、Vencardのダウンロード

[Vencord-foobar](https://github.com/tunip3/Vencord-foobar/tree/main)を入れる。  

```text
Invoke-Expression (Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/tunip3/Vencord-foobar/main/Install-RicherCider.ps1' -UseBasicParsing).Content
```

をPowerShellで実行。

### 実行!

`node index.js`

## 既知の問題

- ローカルファイルだとアルバムアートがDiscordに表示されない。
![image](https://i.imgur.com/6w6LD8O.png)
- 途中から再生してしまうと再生バーと時間がずれてしまう。
