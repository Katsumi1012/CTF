# Challenge:
Jason todd went missing and all alfred was able to recover from his pc was this file
Help Alfred find Jason

Author: Rakhul

FLAG FORMAT:
dsc{[a-zA-Z0-9_]+}
# Solution:
The challenge gave me a file with password named `jason.zip`, using `john` to unzip it, there are 2 folder:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/a56308d1-c2db-494f-a0b7-6bed9bd81c8d)

![image](https://github.com/Katsumi1012/CTF/assets/108376735/c212621b-e1b7-48a2-93a2-49273da048e5)

In the first folder, we have a `README.md` file:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/9b3c6e38-93b4-4b89-a959-160fcedeb079)

I assume that this file is a kind of a html file, so I used a html editor online to see the clean version of it:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/a2644527-237b-4d87-9749-983a263ab82c)

Nothing more, so I open the second folder, there are 3 `.txt` files and a folder that stands out, `.git`:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/e15aa201-dce4-474d-9706-8e59c96f1847)

Open 3 files: `empty.txt`, `encode.txt`, `secret.txt` and I was rick rolled at `secret.txt`🤡:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/8d3a2be5-a115-44f4-8a5f-4048c2910974)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/b82e1650-b9cf-4ea8-8934-547d0d8ef987)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/d56e434c-0e2a-4957-a591-5112e281b5d0)

Decode the line in `encode.txt`, this is a dead end:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/44eb1fcf-79c0-4227-b783-022de53cb9b1)

The information in `empty.txt` leads me to the `.git' folder, so I can say the given folder is the repository of the person we're looking for
I easily found the github of Jason:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/800aa587-85c1-47a3-94bb-29929ce25e11)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/097aaadf-0f07-4d10-b90b-eea6062e3883)

Checking `nothing_here_to_look_at`'s commit, I found the 4th file:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/d4cc0964-9813-41cd-8be0-9f6ec7bc67dd)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/bc1bfa0f-4d25-432d-b915-f7786c672fac)

Decoding the line using Base64 leads us to an Instagram profile:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/ab89f451-41a5-463a-9cd2-27052d5652ec)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/065203ef-3221-4c2c-a439-997efa57a5c2)

The first picture gave us half of the flag and the second picture told us to find his Twitter:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/9feae332-2122-42c6-a5f1-ab9be00c972d)

I found him using his Instagram username to search, and there are 2 posts with two encoded lines:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/944f75c0-e84c-4a73-ab21-5b39695184ac)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/4fe25d7e-29d3-414f-b1b6-aa5b788d7e28)

Decode with the line in older post with base32, I found the second half of the flag:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/21518e7b-5042-4e22-9f0d-6699be5446a8)

And we get the flag 🚩
# ENJOY 🤡
