####Ansible:

##### SSH CONNECTION
Ansible uses SSH connection to connect to remote hosts.

##### How SSH connection will work ?

SSH connection uses two connection algorithms symetric and asymetric.

 ##### symetric algorithm
 same private key is used on both hosts, to encrypt
and decrypt.

Pros: while sharing key somebody will get access private key.
so they can encode and decode text easily.

##### asymetric key algorithm:

In this algorithm we will have  public and private keys, which are used for encryption and decryption.

    a. private key not shared to any one.
    b. public key is shared to any body.
    clients will encode sending data with public key and server will use 
    private key to decode data.
    
Combination of both used in SSH connection
1. asymetric algorithm is used to share encryption key to clients.
2. data can be encrypted by symetric algorithm because, it is fast 
compare to asymetric algorithm.
symetric algorithm used to encode large data and asymetric will
be used to encrypt small data.

##### Remote connection setup ansible

import points while setup ssh connection, on client host we cant setup ssh connection
using root user, we need to create a new user and need to add to sudoers.

##### Ansible priviliged methods:

    # remote_user: the use who is logging through ssh. ex: ssh abc@127.0.0.0.1, here abc is remote user
    # become: once connection is establish, user will become to root user
    # become_user: by default ansible will become user as root, we can change this using
      become_user
    # become_method: it will be like sudo or su etc.
    # sudo: yes, while installing anything we need to use sudo in ubuntu for this purpose 
    we will use sudo
    # we can pass password from command line like --extra-vars "ansible_sudo_pass=***" 
    
      
   

