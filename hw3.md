## b) make offline storage for git

Before starting I had micro, bash-completion and ufw installed

First I needed to update package lists

	$ sudo apt-get update

And install git

	$ sudo apt-get -y install git

I made a new directory for git

	$ git init cat
	$ cd cat

I needed to define name and email for git

	$ git config --global user.name "Tatu"
	$ git config --global user.email "tatu@palvelintenhallinta.com"
	$ git config --global --list
	user.name=Tatu
	user.email=tatu@palvelintenhallinta.com

Next I made a new file to the repository

	$ micro README.md
	$ cat README.md
	Hello World!

And did a commit

	$ git add .
	$ git commit
	$ git log --patch
	commit 51e983012f3297014dcda694bbc229e6dc17540d (HEAD -> master)
	Author: Tatu <tatu@palvelintenhallinta.com>
	Date:   Tue Nov 15 19:26:12 2022 +0000
	
	    Add purpose to README.md
	
	diff --git a/README.md b/README.md
	new file mode 100644
	index 0000000..980a0d5
	--- /dev/null
	+++ b/README.md
	@@ -0,0 +1 @@
	+Hello World!


### c) make a stupid change to git and undo it with git reset

First I needed to make a mistake in git

	$ micro README.md
	$ cat README.md
	This is Hello World! wrong!!

And fix the mistake

	$ git reset --hard
	HEAD is now at 51e9830 Add purpose to README.md
	$ cat README.md
	Hello World!


### d) and e) Make a new repository to github and clone it and make commits with ssh

At the start I made a new repository to github.com, made a new ssh key

	$ cd
	$ ssh-keygen

Copied the key and added it to github

	$ cat .ssh/id_rsa.pub
	ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDRbYSps9aoEzOD0DPzOvq7qdWEmtkZ+Qc3PDJeI3Ofu39VlYjdBAyayCiETb8OuxuKlC2n8W9QA2nGHVVxpirFXaDDp55KPflxbg0wl7jxrUPbbxu84ZL5r5pun9kEU6G/21IryMILGHIlFyt1oaKG89U6UXWmfvRHcrHdaXm/JR18IQ6lNIzc1AXCgUCDHqT4NzDaTSIR4BynYVTiJKPiEougXIY1DsY9S0R4Fr4sKkjClINhcBVqy/0MjJDOEPi+0uxijuTTVi2H4UID6f76nScxWkaFJxrZNz73zz5AwR5ZBqK2rPpM35Lzm/VUbfrEO19BIoBh3ZBhrBRp/RUKyL+OYezsX8f0BA2dUEM9h5xv+V7jpoBY/gJie5D8mWNenyL9/KoTPacQoYvJXk7KZEIsI8aPDQAM30RfczSwNXaHPD8DxQXHJU9spYSOShoRNYHArQt7SIc1owwleiZTdaJayiBmvPShLvapdxmAfm2617JtqJscDm5y9ft+tiE= tatu@table

After that I cloned the repository to my pc

	$ git clone git@github.com:aavetatu/imaginarycar.git
	$ cd imaginarycar/

I edited README.md

	$ micro README.md
	$ cat README.md
	# imaginarycar
	
	Hello world!

And made a commit

	$ git add .
	$ git commit
	$ git pull
	$ git push

I wanted to do a commit of the report I had been writing during completing this homework

I went to the directory I had done the report in and copied it to the repository I had cloned in this excercise

	$ cp hw3.md /home/tatu/imaginarycar/

And made the commit 

	$ git add .
	$ git commit
	$ git pull
	$ git push

I went to check from github.com if my commit was succesfully updated to github website


	
