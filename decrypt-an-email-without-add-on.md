# Quickfix: How to decrypt a mail without encryption add-on

Thanks to Thunderbird his last move, encryption through Enigmail add-on suddenly became impossible if you wanted to use well, an add-on to do it.

First, download the email from the mailbox, in Thunderbird base it's an .eml file ([about .EML extension](https://fileinfo.com/extension/eml)) that is downloaded

Then you need to install (hopefully one) and run two tools:

first is [uudeview](http://www.fpx.de/fp/Software/UUDeview/)

	sudo apt install uudeview

View your file content:
	
	uudeview [your_file.eml]
	
	Loaded from example.eml: 'Fwd: Example' (Fwd): encrypted.asc part 1   Base64
                                                                      
    Found 'encrypted.asc' State 16 Base64 Parts 1 OK

    -rw-r--r-- encrypted.asc   is OK   [d] (?=help) 

Press Y to say Yes

	Opened file example.eml
    	File successfully written to /home/x/Desktop/encrypted.asc     
      1 file decoded from 1 input file, 0 failed  

So now you have extracted the **encrypted part** of the message. You have an .asc file ([about .ASC extension](https://fileinfo.com/extension/asc))

Then, you run your [GnuPG](https://gnupg.org/). This line above will give you a preview of the file in your terminal, remember that you'll need to send the stream into file to save it.

	gpg --decrypt [your_file] 
	
**Note**: At the bottom of the output, you have interesting information such as the date and time of the signature, the type of key used, the originated email address, a key fingerprint and so on.


**Tips**: In case your email and it's content is long, you can grab the top of the output by piping a less command:

	gpg --decrypt [your_file] | less 

To save the file:
	
	gpg --decrypt [your_file] > my_file

Now that you hace decrypted your file, you need to take a look in it to see of what it is composed. You'll use Uudeview again:
	
	uudeview [your_decrypted_file]

Press Y as many times as you want to see a file written in the specified format (look at the uudeview output) and you are good to go! 

Files are created in your folder. Now you are free to consult them.

More: [Introduction to decoding](http://www.fpx.de/fp/Software/UUDeview/Introduction.html) by Frank Pilhofer.

special tks to @adulau for cool hacky thoughts
