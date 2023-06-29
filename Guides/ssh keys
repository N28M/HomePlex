SSH public-private keypair can be used to connect from one server to another using a key instead of a password

Here we are using Ubuntu server on windows WSL2 to connect to Ubuntu Server on the optiplex.

Generate a 4096 bit key using the command 
	ssh-keygen -b 4096

The program will ask for a name and path for the key
	/home/ansible/.ssh/ansible_key_rsa

The keygen program will ask for a passphrase, but we will keep this blank for now (Adding a passphrase requires us to enter the passphrase even while connecting using the ssh keys)

Next, we need to copy the public key to the optiplex server
	ssh-copy-id -i /home/ansible/.ssh/ansible_key_rsa <user>@<hostname>

This will ask for a password for the user (<user>) for the optiplex

Since we are using a custom key, we need to create a config file in the .ssh folder if that does not exist

In the config file, add the below for connecting to optiplex

	#optiplex
	Host <hostname>
	        User <user>
	        IdentityFile /home/ansible/.ssh/ansible_key_rsa
	
Now connect to optiplex using ssh <user>@<hostname>