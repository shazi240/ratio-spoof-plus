# ratio-spoof
Ratio-spoof is a cross-platform, free and open source tool to spoof the download/upload amount on private bittorrent trackers.

![](./assets/demo.gif)

## Motivation
Here in Brazil, not everybody has a great upload speed, and most private trackers require a ratio greater than or equal to 1. For example, if you downloaded 1GB, you must also upload 1GB in order to survive. Additionally, I have always been fascinated by the BitTorrent protocol. In fact, [I even made a BitTorrent web client to learn more about it](https://github.com/ap-pauloafonso/rwTorrent). So, if you have a bad internet connection, feel free to use this tool. Otherwise, please consider seeding the files with a real torrent client.

## How does it work?
![Diagram](./assets/how-it-works.png)
Bittorrent protocol works in such a way that there is no way that a tracker knows how much certain peer have downloaded or uploaded, so the tracker depends on the peer itself telling the amounts.

Ratio-spoof acts like a normal bittorrent client but without downloading or uploading anything, in fact it just tricks the tracker pretending that.

## Usage
```
Create a folder in "C Drive" with name "tr"
Copy and Paste "ratiospoofplus.exe" tool file in this folder, also copy paste torrent file in the folder and rename it to "d.torrent"
In start menu, search with "cmd", then Righ Click and Run with Admin.
In Command Prompt (cmd), Copy and Paste location of folder, where you pasted files before, by using "cd" command
like this:

cd C:\tr
and then press enter from keyboard

Now use this, with or without aleteration

ratiospoofplus -d 100% -ds 0kbps -u 0% -us 1500kbps -c utorrent-2.2.1 -t C:\tr\d.torrent

d 100%  = Already Downloaded by You.
100% means, file already downloaded, you are only seeding/uploading

ds 0kbps = 0 Download Speed, as files are already downloaded, you now only seeding/uploading

-u 0%  = 0% File Uploaded, as you are now Uploading
-us 1500kbps = Your upload speed is 1500kbps

-c utorrent-2.2.1 = Torrent Client you are using

you can use any of these clients, these are available in the tool:

deluge-1.3.15
deluge-2.2.0

qbittorrent-4.0.3
qbittorrent-4.2.3
qbittorrent-4.3.3
qbittorrent-4.5.2
qbittorrent-4.6.3
qbittorrent-5.1.3

utorrent-2.2.1
utorrent-3.5.5
utorrent-3.6.0

========================================================================================================================

usage: 
	./ratio-spoof -t <TORRENT_PATH> -d <INITIAL_DOWNLOADED> -ds <DOWNLOAD_SPEED> -u <INITIAL_UPLOADED> -us <UPLOAD_SPEED> 

optional arguments:
	-h           		show this help message and exit
	-p [PORT]    		change the port number, default: 8999
	-c [CLIENT_CODE]	change the client emulation, default: qbit-4.0.3
	  
required arguments:
	-t  <TORRENT_PATH>     
	-d  <INITIAL_DOWNLOADED> 
	-ds <DOWNLOAD_SPEED>						  
	-u  <INITIAL_UPLOADED> 
	-us <UPLOAD_SPEED> 						  
	  
<INITIAL_DOWNLOADED> and <INITIAL_UPLOADED> must be in %, b, kb, mb, gb, tb
<DOWNLOAD_SPEED> and <UPLOAD_SPEED> must be in kbps, mbps
[CLIENT_CODE] options: qbit-4.0.3, qbit-4.3.3
```

```
./ratio-spoof -d 90% -ds 100kbps -u 0% -us 1024kbps -t (torrentfile_path) 
```
* Will start "downloading" with the initial value of 90% of the torrent total size at 100 kbps speed until it reaches 100% mark.
* Will start "uploading" with the initial value of 0% of the torrent total size at 1024kbps (aka 1mb/s) indefinitely.

```
./ratio-spoof -d 2gb -ds 500kbps -u 1gb -us 1024kbps -t (torrentfile_path) 
```
* Will start "downloading" with the initial value of 2gb downloaded  if possible at 500kbps speed until it reaches 100% mark.
* Will start "uploading" with the initial value of 1gb uplodead at 1024kbps (aka 1mb/s) indefinitely.

## Will I get caught using it ?
Depends on whether you use it carefully, It's a hard task to catch cheaters, but if you start uploading crazy amounts out of nowhere or seeding something with no active leecher on the swarm you may be in risk.

## Bittorrent client supported 
The default client emulation is qbittorrent v4.0.3, however you can change it by using the -c argument

## Resources
http://www.bittorrent.org/beps/bep_0003.html

https://wiki.theory.org/BitTorrentSpecification

