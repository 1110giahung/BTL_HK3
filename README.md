Based on the content from your report, here’s a README file draft that you can use for your GitHub repository:

⸻

Simple Torrent-like Application (STA)

This repository contains the implementation of a Simple Torrent-like Application (STA), designed as a simplified version of BitTorrent using the TCP/IP protocol stack. The application aims to achieve multi-directional data transfer (MDDT) and peer-to-peer (P2P) file sharing, focusing on efficient data dissemination among decentralized peers.

Features
	•	Tracker: A centralized entity managing metadata and facilitating peer discovery.
	•	Peers: Decentralized nodes that both upload and download files from one another.
	•	Multi-Directional Data Transfer (MDDT): A multithreaded approach allowing peers to download multiple file chunks simultaneously from various peers to enhance transfer speed.

System Components
	1.	Tracker: Manages metadata about available files and their chunks across peers.
	2.	Peer: Nodes capable of downloading and uploading files, handling requests, and managing file chunks.
	3.	File & Piece: The system supports chunked file downloading, where each file is broken down into smaller pieces for efficient sharing across peers.

Installation

Requirements
	•	Python 3.x
	•	Required Python packages: socket, threading (for multithreading)

Setup
1.	Clone the repository:

		git clone https://github.com/yourusername/sta.git
		cd sta

2.	Run the tracker

		python tracker.py


3. Run the peer (in a different terminal):

		python peer.py




Use the start command to begin operations and the update command to refresh file availability. To request a file, use the request <filename> command.

System Architecture

The system is composed of the following core components:
	•	Tracker: Centralized metadata server that handles peer registration and manages file availability.
	•	Peer: A decentralized node that communicates with both the tracker and other peers to download/upload files.
	•	File Management: The system divides files into chunks, with each chunk being handled by the File and Piece classes.

Class Diagram

A simple class structure is followed:

- Peer Class: Handles peer-to-peer communication, file download/upload, and registration with the tracker.
- Server Class: Manages communication between peers and updates their file information.
- File Class: Handles file chunks, downloading pieces, and managing the file’s status.

Data Flow
- Registration Phase: Peers register their file metadata with the tracker.
- File Request & Sharing: Peers request files or file pieces from the tracker, which responds with a list of peers holding the desired chunks.
- Chunk Downloading: Peers download file pieces simultaneously from multiple peers (MDDT), optimizing transfer speeds.

Commands
- start: Begins peer operations and establishes communication with the tracker.
- update: Refreshes the list of available files.
- request <filename>: Requests a file from the available peers.

Multi-Threaded Data Transfer (MDDT)

The STA employs a multithreaded approach where peers download file chunks simultaneously from multiple sources, increasing the efficiency of data transfer. Each peer initiates multiple threads to handle concurrent file downloads from different peers.

Conclusion

The Simple Torrent-like Application (STA) demonstrates key concepts of networking, such as socket programming, multithreading, and decentralized file management. It successfully implements a peer-to-peer file-sharing model, showcasing the power of decentralized systems for efficient data distribution.

Authors
	- Huỳnh Gia Hưng – 2252274
	- Mạc Hồ Do Khang – 2252297
 	- Nguyễn Đức Hạnh Nhi – 2252578

License

MIT License

⸻

