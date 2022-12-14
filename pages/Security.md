icon:: 🛡️

- ## Normal
	- Upgrade some daemon to latest version in order to prevent 0day attacking.
		- [Nginx](logseq://graph/note-of-code?block-id=634e68bd-d960-4be4-a489-1babe761f48d)
		- ssh
- ## Emergency
	- ### Source: [Linux应急笔记](https://github.com/422926799/note/tree/master/%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95/Linux%E5%BA%94%E6%80%A5%E7%AC%94%E8%AE%B0)
		- Check Status
			- Check processes that CPU usages > 50%
			- Check weird command
			- `htop` process tree
			- Ex: miner process: `xmrig`
		- Check Communicating IP/Host
		- Remove Virus
			- Crond Job
			- `dpkg -S` to check if the executable is from package or not
			- [Scan file](((63155aa2-1e4d-4f5c-888c-3929814d549d))) to check the binary file
		- Periodic Scanning:
			- TODO Maybe we can write a tool to record (git diff??)
			- `service --status-all`
			- `crontab -l`
			- `cat /etc/anacrontab`
			- `find /usr/bin/ /usr/sbin/ /bin/ /usr/local/bin/ -type f -mtime -7 | xargs ls -la`
			- `lsmod`
	- ### Note
		- Check what program listen what port
			- ```bash
			  sudo lsof -PiTCP -sTCP:LISTEN
			  ```
		- Check ip incoming
			- `tcpdump` will get the flow before iptable
				- Wire -> NIC -> tcpdump -> iptables
				- iptables -> tcpdump -> NIC -> Wire
			- ```bash
			  sudo tcpdump -i eth0 'tcp and port 8763'
			  ```
- ## Scan file
  id:: 63155aa2-1e4d-4f5c-888c-3929814d549d
	- VirusTotal scan the binary file
		- https://github.com/VirusTotal
		- https://www.virustotal.com/gui/home/upload
	- chkrootkit check if there is a rootkit sign
		- http://www.chkrootkit.org/
- ## Privacy
	- ### VPN
		- [WireGuard]([[Security/WireGuard]])
	- ### Anonymous
		- [Tor]([[Security/Tor]])
		- [Tails]([[Security/Tails]])
	- ### Data
		- [Proton Mail](https://proton.me/)
		- [Filebrowser](https://github.com/filebrowser/filebrowser)