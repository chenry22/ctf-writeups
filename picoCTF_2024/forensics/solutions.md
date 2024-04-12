### Index
- [***Back to Main***](/)
- [Scan Surprise](#scan-surprise)
- [Verify](#verify)

### Scan Surprise
- We are provided a folder which contains a QR code- reading this QR code gives us our flag!

### Verify
- We are given `ssh` connection to a remote instance with three files: checksum.txt, decrypt.sh, and a files directory containing ~300 ASCII text files
- After verifying our hash, we can use the decrypt.sh script to check each file in the files directory to see if it contains the flag. The decrypt.sh script expects one argument, a filename relative to the home directory, and will attempt to decrypt the file using `openssl enc -d`. There are 300+ files to check, but we can speed up the process by writing a simple shell command looping through all of them.
- ```shell
    for file in files/**;
        do ./decrypt.sh file;
    done```
- This simple command will loop through all the files and check them- then it's just a matter of cmd+f to find the flag in the output!