Files that I sign will include a base64 encoding of the signature. The easiest way to verify the signature is to run a command like:

openssl base64 -d -in "signature" -out /tmp/sign.sha256

Where "signature" is the provided signature of the file.

From there you can verify the file with a command like:

openssl dgst -sha256 -verify "pub-key" -signature /tmp/sign.sha256 "file"

Where "pub-key" is my public key and "file" is the signed file to be checked
