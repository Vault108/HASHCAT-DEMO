First we need to unpack rockyou.txt.tar.gz
To do this we run
    gunzip rockyou.txt.tar.gz
No more  BS lets get right into it! 
To crack the md5 hashes we run

    hashcat -m 0 hashes/md5.txt dict/passwords.txt -o cracked/md5.txt --force
Now doing this may return "exhausted" meaning hashcat cracked all the passwords it could
with the given dict file and placed them in /cracked/md5.txt 

Lets try it with a different dict file now run 

    hashcat -m 0 hashes/md5.txt dict/rockyou.txt -o cracked/md5rockyou.txt --force

It should give you a messages saying "removed x hashes found in potfile" this means it
already has cracked those hashes, and moved on to the other ones. 



To crack the sha1 hashes we run

    hashcat -m 100 hashes/sha1.txt dict/passwords.txt -o cracked/sha1.txt --force
