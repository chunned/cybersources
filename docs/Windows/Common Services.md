---
category: windows
---
# NetBIOS
- Network Basic Input/Output System
	- Port 139
- Provides services related to session layer of OSI model
	- Allows applications on separate devices to talk over the LAN
	- Strictly an API, not a network protocol
- Often used for communication of data for files and printers through the session layer

# SMB
- Server Message Block
	- [Port 139](NetBIOS) and 445
- Network file sharing protocol
- Requires open port on the server
### Common Vulnerabilities
- Unprotected admin shares
`smbclient \\\\{target IP}\\C$ -U Administrator`
- Unprotected users
Remote shell with [[Impacket]]:
`psexec.py Administrator@{target IP}`

# RPC 
- Remote Procedure Call
	- port 135
- Supports communications between Windows applications using RPC protocol
	- Low-level interprocess communication; client process can make requests to server process
- COM and DCOM built on top of RPC
- Service name `RpcSs`; runs inside shared services host process `svchost.exe`