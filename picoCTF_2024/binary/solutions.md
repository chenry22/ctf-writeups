### Index
- [***Back to Main***](/)
- [format string 0](#format-string-0)
- [heap 0](#heap-0)

### format string 0
- We are given the source code to a program being run on a remote server which we can connect to using the `nc` command in our terminal
- Inspecting this source code, we see that the user must choose two sandwich "recommendations" for two customers at a burger shop. Some of the items on the menu have format specifiers within their string makeup, which we can take advantage of to read memory from the program we shouldn't have access to. Specifically we see that there is an option to choose the "Cla%sic_Che%s%steak" for the second customer, which contains three `%s` format specifiers. Our chosen options are printed out after selection without any extra input, so each of these will fill with a character stirng read from the processes memory.
- Connecting to the program run on the remote server and choosing this option as your second selection forces the program to read the stored flag string from memory and print it out!

### heap 0
- We are given the source code of a program which is meant to manage heap data securely. In it, two variables are stored on the heap next to each other. Through the program we can access their addresses and see the data stored there. We can also write to one of the variables through a function defined by the program. Our goal is to overwrite the 'safe' variable which we do not have access to. If the program finds that this variable does not hold its original value, it will give us the flag!
- Looking at the source code, we see the `write_buffer()` function simply uses `scanf` to overwrite the data at the address we have access to, without doing any bounds/overflow checking! We can take advantage of this by overflowing past the original bounds of the string (providing a long string to write to the buffer). Doing this we can corrupt the safe data, after which the program will give us the flag!