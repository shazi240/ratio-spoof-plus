# ratio-spoof
Ratio-spoof is a cross-platform, free and open source tool to spoof the download/upload amount on private bittorrent trackers.

![](./assets/demo.gif)

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
ratiospoofplus -t <TORRENT_PATH> -d <INITIAL_DOWNLOADED> -ds <DOWNLOAD_SPEED> -u <INITIAL_UPLOADED> -us <UPLOAD_SPEED> 

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
[CLIENT_CODE] options: as above
```

* Will start "downloading" with the initial value of 2gb downloaded  if possible at 500kbps speed until it reaches 100% mark.
* Will start "uploading" with the initial value of 1gb uplodead at 1024kbps (aka 1mb/s) indefinitely.

## Will I get caught using it ?
Depends on whether you use it carefully, It's a hard task to catch cheaters, but if you start uploading crazy amounts out of nowhere or seeding something with no active leecher on the swarm you may be in risk.

## Resources
http://www.bittorrent.org/beps/bep_0003.html

https://wiki.theory.org/BitTorrentSpecification

