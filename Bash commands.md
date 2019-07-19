# Bash Commands :

1. **SSH COMMAND** to establish remote connection to a server
   * `ssh -i ~/.ssh/login.pem root@13.126.220.100`
   - **SSH COMMAND LINE OPTIONS :** <br/>
       Some of the most important command-line options for the OpenSSH client are:
     - -1 : Use protocol version 1 only.
     - -2 : Use protocol version 2 only.
     - -4 : Use IPv4 addresses only.
     - -6 : Use IPv6 addresses only.
     - -A : Enable forwarding of the authentication agent connection.
     - -a : Disable forwarding of the authentication agent connection.
     - -C : Use data compression
     - -c : cipher_spec Selects the cipher specification for encrypting the session.
     - -D : [bind_address:]port Dynamic application-level port forwarding. 
            This allocates a socket to listen to port on the local side. 
            When a connection is made to this port, the connection is forwarded over the secure channel,
            and the application protocol is then used to determine where to connect to from the remote machine.
     - -E : log_file Append debug logs to log_file instead of standard error.
     - -F : configfile Specifies a per-user configuration file. 
            The default for the per-user configuration file is ~/.ssh/config.
     - -g : Allows remote hosts to connect to local forwarded ports.
     - -i : identity_file A file from which the identity key (private key) for public key authentication is read.
     - -J : [user@]host[:port] Connect to the target host by first making a ssh connection to the
            pjump host[(/iam/jump-host) and then establishing a TCP forwarding to the ultimate destination from there.
     - -l login_name Specifies the user to log in as on the remote machine.
     - -p port Port to connect to on the remote host.
     - -q Quiet mode.
     - -V Display the version number.
     - -v Verbose mode.
     - -X Enables X11 forwarding.
     
2. **SCP COMMAND** to copy file from One System to Other:
   - From Local system to Remote System
     - ` scp -i login.pem ~/source-file root@13.126.220.100:destination-folder`
   - From Remote to local system
     - ` scp -i login.pem ~root@13.126.220.100:source-file ~/destination-folder`
   - SCP options 
     - -v :  You can use “-v” parameter to print debug information into the screen
     - -p :  An estimated time and the connection speed will appear on the screen
     - -C :  he “-C” parameter will compress your files on the go. The unique thing is the compression 
             is only happen in the network. When the file is arrived to the destination server, it will 
             returning into the original size as before the compression happen.
     - -Cpv : combining multiple options
     - -q : Disable progress meter and warning / diagnostic message
     - -c : select another cipher to encrypt files (default : AES-128 , -c 3des or any other)
       -  ` scp -c 3des ~root@13.126.220.100:source-file  ~/destination-folder`
     - -l : Limiting bandwidth (Kilobits/sec (kbps)) -l 400 ~ 50Kbps
       -  ` scp -l 400   ~/source-file root@13.126.220.100:destination-folder`
     - -P : Specify specific port to use with SCP (default :22)
       -  ` scp -P 5000   ~/source-file root@13.126.220.100:destination-folder`
     - -r : Copy files inside directory recursively
       -  ` scp -r   ~/source-file root@13.126.220.100:destination-folder`
     - -i : Send input file 
       -  ` scp -i login.pem ~/source-file root@13.126.220.100:destination-folder`
     
3. **Linux command**
   - `diff [options] file1 file2`
      -  -i  : make case insensetive
      -  -c : context mode *** file1 --- file2
      -  -u : unified output
