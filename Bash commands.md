# Bash Commands :

1. **ssh command** to establish remote connection to a server
   * `ssh -i ~/.ssh/login.pem root@13.126.220.100`

2. **scp command** to copy file from One System to Other:
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
