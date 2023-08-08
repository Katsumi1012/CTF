# Challenge:
NASA receive a weird transmission yesterday but they were't able to decode it. I mean, it's just a bunch of gibberish. The only thing they have cracked was one word "goodbye"
They have no clue what that means though. Can you help them?

FLAG FORMAT:
dsc{[a-zA-Z0-9_]+}
# Solution:
The challenge gave me a `.txt` file, open it, and it might be a dead end just by looking at it:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/ffc95a25-8bb9-499b-a378-88a10724da12)

Go to the end of the file and I found the sign of Base64 encode:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/86ed7355-8a81-44e0-a19c-88712a6497dd)

Decoding the file, the description had the hint "goodbye" so I find it and it right before the flag:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/1d097438-51c7-4c40-8457-419e585b934b)

And we get the flag 🚩
# ENJOY 🤡
