# Bash Commands :

1. **ssh command** to establish remote connection to a server
   * `ssh -i ~/.ssh/login.pem root@13.126.220.100`

2. **scp command** to copy file from One System to Other:
   * From Local system to Remote System
     ` scp -i login.pem   ~/path/to/fileOnLocalSystem/myfile    root@13.126.220.100:/path/toSavefile/onRemote`
   * From Remote to local system
     ` scp -i login.pem   ~root@13.126.220.100:/fileOnRemoteSystem/myfile    ~/path/toSavefile/onLocal`
3. **Linux command**
   * `diff [options] file1 file2`
      **  -i make case insensetive
      **  -c context mode *** file1 --- file2
      **  -u unified output
