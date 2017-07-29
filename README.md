<h1>YO DWAG! READ THIS INSTRUCTIONS</h1>
<h5>So we use the same procedures!</h5>

<h2>1. Initiate repository</h2>

On your machine create a folder called arventurer (or whatever really). inside of it create another one called "shared-testing" (or whathever the repository you're working on is called). <br>
From that folder do these following commands:

<pre>
	git init .
	git remote add origin URL_TO_REPOSITORY
	git fetch origin
	git checkout master
</pre>

<b>IMPORTANT INFO:</b> Make sure you are on master before pulling, do a "git branch" to see what branch you are in.

<h2>2. Work on an already initiated repository</h2>

Once the repository is initiated (and from that point on, everytime you'll work on that same repository) follow this commands:

<pre>
	git checkout master
	git pull
	git checkout BRANCH_NAME
</pre>

<b>IMPORTANT INFO:</b> if you are working on a non existing branch just do a "git checkout -b BRANCH_NAME", but make sure master is checked out before you do so.

<h2>3. What happens after you change code/files?</h2>

While you work on your files, everything should be happening on the branch you're on (e.g. st1 that i've created just as a proof of concept).
Once you're happy with your changes you need to merge it into dev, so it will show up on the server that we will set up (give me a bit of time and it will be set up too)

<pre>
	git add FILENAME (or you can do "git add ." to add everything, but make sure there's no stuff we don't need in the folder)
	git commit -m "MESSAGE FOR THE COMMIT"
	git push
	git checkout dev
	git pull (this will prevent conflicts getting the latest code from dev before merging)
	git merge BRANCH_NAME (the branch you were working before switching into dev)
	git push
	git checkout BRANCH_NAME (again, the branch you were working before switching into dev)
</pre>

<b>IMPORTANT INFO:</b> Make sure to be on a branch that is not dev while you change your code, or dev will end up full of conflicts!!

<h2>4. Connect into the server</h2>

Once generated an ssh key (if don't know how i'll walk you through it), just ssh into the server with the command

<pre>ssh root@104.131.44.170</pre>

This will ask you for a password if you set one up during the ssh key generation, otherwise will log you in automatically.

<b>IMPORTANT INFO:</b> tutorial for ssh key auto generation: https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html . Once generate, send me an email with the public key generated at comm.campione@gmail.com .

<h2>5. Update the server with most recent code</h2>

Once in the server, navigate to /var/www/http/

<pre>cd /var/www/http/</pre>

check all the folders in there with "ls -la". Choose the folder you want to work on (will most likely be called as the repository) and navigate into it "cd FOLDERNAME".
Once in the folder do this:

<pre>
	git branch (to make sure the folder is set on dev)
	git pull
</pre>

<b>IMPORTANT INFO:</b> At this stage the code should be updated, be sure that you are on dev before pulling (again, run a "git branch" command to check what branch is the server in, even tho i will make sure it will have only dev on the development, and master on live).

<h2>BASIC GIT COMMANDS</h2>

<pre>
	git init - creates the .git folder where all the logic is stored
	git pull - gets the latest version of the code from the repository
	git checkout BRANCH - switches between branches
	git checkout -b BRANCH - creates a new branch based on the branch you are currently on
	git status - shows a list of files edited and deleted (green are ready to be committed, red are deleted and if there are problems will be shown in the list with details)
	git branch - shows the branch you are working on
	git merge BRANCH - merges the specified branch inside the branch you are currently switched on
</pre>

<b>IMPORTANT INFO:</b> actually there are none, but i wanted to keep the structure. Hope you guys like this, if there are any problem slack is your friend. Byez.

<h2>USEFUL LINKS</h2>
three.js documentation: https://jeromeetienne.github.io/AR.js/three.js/<br>
a-frame documentation: https://aframe.io/docs/0.5.0/primitives/a-obj-model.html <br>
useful issue: https://github.com/jeromeetienne/AR.js/issues/61 <br>
FULL TUTORIAL!!!: http://www.creativebloq.com/how-to/how-to-code-an-augmented-reality-marker <br>