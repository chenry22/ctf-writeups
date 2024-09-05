### Index
- [***Back to Main***](/)
- [Scan Surprise](#scan-surprise)
- [Verify](#verify)
- [Secret of the Polygot](#secret-of-the-polygot)
- [CanYouSee](#canyousee)

### Scan Surprise
- We are provided a folder which contains a QR code- reading this QR code gives us our flag!

### Verify
- We are given `ssh` connection to a remote instance with three files: checksum.txt, decrypt.sh, and a files directory containing ~300 ASCII text files
- After verifying our hash, we can use the decrypt.sh script to check each file in the files directory to see if it contains the flag. The decrypt.sh script expects one argument, a filename relative to the home directory, and will attempt to decrypt the file using `openssl enc -d`. There are 300+ files to check, but we can speed up the process by writing a simple shell command looping through all of them.
- ```shell
    for file in files/**;
        do ./decrypt.sh file;
    done
- This simple command will loop through all the files and check them- then it's just a matter of cmd+f to find the flag in the output!

### Secret of the Polygot
- We are given a file that we're told has a conflicting type. If we open it up, we see part of the flag in plaintext on the PDF!
- Using the `cat` command in a terminal to read the raw data of the file, we can see that it is tagged as a PNG file. Using any file explorer, we can manually change the file to a different type. If we convert it to a PNG, we can see the first half of the flag! 

### CanYouSee
- We are provided an image. The first thing you should do with images is always `strings` or `cat`! Since this image is pretty high resolution though, I opted to use `head` instead.
- The top part of a file is usually dedicated to metadata like file type, and this was no exception. We see a bunch of metadata stored, including the word "Exiftool", which is a command line tool that organizes and outputs image metadata for you.
- Running `exiftool` on the image, we see a list of metadata, including something labeled "Attribution URL", which is suspiciously not a URL, but instead a Base64 string (note the trailing "=="). Decrypting this gives us our flag!
