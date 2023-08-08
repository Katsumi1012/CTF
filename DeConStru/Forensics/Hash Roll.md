# Challenge:
Augustine's friend took a important file of augustine and stashed it.
He was able to grab all the files from his friend's machine but he is worried that the files are encrypted.
Help him get the file back

Author: Rakhul

FLAG FORMAT:
dsc{[a-zA-Z0-9_]+}
# Solution:
The challenge gave me 2 files: `encrypted1.zip` with password and `nothing.pdf`. The later just rick rolled us:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/6ae14896-9759-4300-8baa-363b0992e0d1)

Using `john` to crack password of `encrypted1.zip`:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/733b5fb0-61e3-434c-9d66-fa1a511b619f)

Open the `flag.jpg` after unzip the above file and get the flag:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/d57ff363-a753-4ead-86e3-205de3eeff8e)

# ENJOY 🤡
