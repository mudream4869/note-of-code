title:: Code Snippets/Ansible

- ## Ansible deploy to docker
	- ```
	  [host_group_name]
	  <container_name> ansible_connection=docker
	  ```
- ## Debug
	- ```yml
	  - name: IPs
	    ansible.builtin.debug:
	      var: <var_name>
	  ```
- ## Multicast Command
	- ```bash
	  ansible -i hosts 'LIMIT' \
	      --user=<user> \
	      --private-key=<key> \
	      -f 10 -m shell -a \
	  	'echo 1'
	  ```
- ##  IPs
	- All
		- ```yml
		  - name: IPs
		    ansible.builtin.debug:
		      var: ansible_all_ipv4_addresses
		  ```
	- Specific network interface
		- ```
		  ansible_eth0.ipv4.address
		  ```
-