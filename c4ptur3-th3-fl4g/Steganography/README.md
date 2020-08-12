## c4ptur3-th3-fl4g

### Steganography
Steganography is the practice of concealing a file, message, image, or video within another file, message, image, or video.

<img src="stegosteg.jpg">

We are given `stegosteg.jpg`.

I used Steghide to get the flag.

`steghide extract -sf stegosteg.jpg` with an empty passphrase.

I got `steganopayload2248.txt` extracted which had the flag in it.

Flag: `SpaghettiSteg`