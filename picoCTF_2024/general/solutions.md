### Index
- [Super SSH](#super-ssh)
- [Commitment Issues](#commitment-issues)
- [Time Machine](#time-machine)

### Super SSH
 - Simply run an ssh command connecting to the server provided
- These commands are in the form of `ssh <user>@<remote_instance> -p <port>`, and you may be asked for a password on connection

### Commitment Issues
- We are provided a folder with text file (simply containing the text "TOP SECRET") and a `.git` directory- using `git log` we can see that two commits editing this text file are stored
- We want to get one commit back, and since these are locally stored, we can do this using `git reset --hard HEAD~`, which will destroy the most recent commit to go back to the commit where the text file was originally commited
- After this, we can simply read the text file normally, which contians the flag

### Time Machine
- We are provided a folder with a text file and a `.git` directory. Using `git log` in the folder, we can find our flag as the commit message of the most recent commit

