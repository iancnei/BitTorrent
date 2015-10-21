# BitTorrent

## What is BitTorrent?

BitTorrent is a method of performing peer to peer file sharing over the internet.

## What do those words mean?

### What is "file sharing"?

File sharing is the distribution of digital media (ie: music, movies, computer games, etc).  Forms include Direct Download from file hosting services (Mediafire, Dropbox, etc) and Torrents utilizing P2P services (Vuze, Transmission, etc).

### What is "peer to peer"?

![client-server](https://upload.wikimedia.org/wikipedia/commons/f/fb/Server-based-network.svg)

The client-server model is where a user or "client" communicates to a central server requesting services or files from the server.  (ie: You go to the Mediafire site and download a file from their server.)

![peer-peer](https://upload.wikimedia.org/wikipedia/commons/3/3f/P2P-network.svg)

In contrast to the client-server model, in peer to peer, users or "peers" communicate directly with other users or "peers" for those services or files.  (ie: Twitter uses BitTorrent to distribute patches to its many servers.)

### How do the client-server and peer-to-peer models compare?

![animation of client-server vs peer-to-peer](https://upload.wikimedia.org/wikipedia/en/5/55/Torrentcomp_lite.gif)

* The client-server model is very secure, the server does authentication whereas with peer-to-peer there is little to no authentication making it very insecure.
* Peer-to-peer can be very inexpensive and fast to setup whereas client-server tends to be more expensive due to maintenance and scalability costs.
* The stability of a peer-to-peer network depends on its peers which can be quite unstable if the file is unpopular (lack of peers who own the file), peers go down, or peers lose the file.  On the other hand the stability of a client-server network is very stable since the server is very unlikely to go down unless it is hacked or someone trips over the power cable and thereby unplugs it.  Servers also usually have scheduled backups which make the permanent loss of a file very hard.

## How does BitTorrent work?

### Differences with the peer-to-peer model

* Rather than sharing the complete file with other peers, a user will instead download pieces of the file from other users which their BitTorrent client will then compile into the original file after all the pieces are downloaded.
* Each piece has a hash assigned to it that is created when the original uploader of the file creates the torrent file.  This makes the sharing of the file safer than normal peer-to-peer since any tampering of an individual piece will lead to a conflicting hash in which case the client will usually download the conflicting piece from a different user until it is found to no longer be conflicting.

### Sharing a File as the Initial Seeder

The initial seeder first creates a torrent file that contains the name of the tracker that the file will be distributed from, the filenames of the files being downloaded, a list of all the pieces, and the uniform size of each piece.  That file is then distributed to leechers via a website or some other means.

### Downloading the File as a Leecher

Once a leecher has obtained the torrent file, their client will connect to the tracker who will direct them to the swarm of other leechers.  The leecher then begins downloading pieces from other leechers and uploading the pieces they've downloaded to other leechers.  This occurs until the file is completely downloaded.

### Uploading the File as a Seeder

Once a leecher has completely downloaded the file, they then become a seeder and begin purely uploading said file.  The more seeds or complete copies of the file there are as well as the more active seeders there are, the healthier a torrent is said to be.

## Upsides of BitTorrent

* It is an efficient way of distributing large amounts of files to many places.
* It can serve many downloaders without a huge increase in internet traffic for a specific user.
* It works really well with extremely popular files.

## Downsides of BitTorrent

* For unpopular files it can be almost impossible to completely download a file if the initial seeder is not present.  The less people there are, the more work the initial seeder has to put in since with less people, there will be less seeders besides the inital seeder.
* Users are not anonymous and their IP addresses are exposed to any other leecher or seeder of a torrent that the user is participating in.  This could lead to problems if the user has an unsecure system.

## BitTorrent Clients

### Recommended

[qBittorrent](http://www.qbittorrent.org/)

It's an open source client made specifically as an alternative to uTorrent. It's easy to use.

[Transmission](http://www.transmissionbt.com/)

It's also open source and simple to use.

### Unrecommended

[uTorrent](http://www.utorrent.com/)

While uTorrent was once a good choice, it has since become ad filled and at one point forced users to install a program that mined bitcoins without their knowledge and gave them to the owners of uTorrent.

# Cheat Sheet

## Definitions

### BitTorrent Client

A program that implements the BitTorrent protocol.

### Seeder

Any user who has a complete copy of the file being distributed and is still uploading.

### Leecher

Any user who has an incomplete copy of the file being distributed and is still downloading.

### Seeding

When a seeder is uploading.

### Leeching

When a leecher is downloading.

### Tracker

The computer or server that coordinates the file distribution

### Torrent File

The file that is created by the initial seeder which holds all the info necessary to download the file being distributed.  Contains info such as which tracker to use, the hashes of each piece, how big each piece is, etc.

### Swarm

The collection of all Seeders and Leechers for a particular bitTorrent file.

# Sources
* http://www.bittorrent.org/beps/bep_0003.html
* https://en.wikipedia.org/wiki/BitTorrent
* http://www.techrepublic.com/article/understanding-the-differences-between-client-server-and-peer-to-peer-networks/
