# Challenge:
Brian tries to send some crucial information from the spacestation about an impending disaster through a super secure line to his friend through a picture.
Help his friend uncover the truth ..

Author: Rakhul

FLAG FORMAT:
dsc{[a-zA-Z0-9_]+}
# Solution:
The challenge gave me a file named `super_secret.jpg`, using `zsteg`, `steghide`, `exiftool`, etc. I got a weird line on the comment:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/0734dd9e-1f75-4bb9-85d0-6fe6edba07c8)

Using `binwalk`, I extracted a picture from it:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/b3c353ea-9e59-41cb-8914-a5c62cb45cc1)

Using `binwalk` again after try above tools and I found a `.wav` file:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/8e975f52-e88e-46f3-addc-131226dde423)

Remember the weird line? I googled it and had the result is `sstv`:
![image](https://github.com/Katsumi1012/CTF/assets/108376735/8346f3af-f2ca-499a-80de-a67f2f108e93)

Using a sstv decoder to decode the `.wav` file, I got a picture with QR code in it:
![Screenshot 2023-08-06 095411](https://github.com/Katsumi1012/CTF/assets/108376735/d69c6e9a-21a9-4cc5-8870-77d02b1ad387)
![image](https://github.com/Katsumi1012/CTF/assets/108376735/a2810f2b-a1fc-44fc-87dc-e4e503552424)


Upload the picture to a QR reader and get the flag:
![Screenshot 2023-08-06 095321](https://github.com/Katsumi1012/CTF/assets/108376735/a65401b6-187a-4463-ac43-25009a957525)

# ENJOY 🤡
