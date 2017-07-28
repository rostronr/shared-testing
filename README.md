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

<h2>4. Update the server with most recent code</h2>

Once logged in into the server (i know is forward, but let's face it, sooner or later will happen) navigate to the folder where the code is (for instance, /var/www/vhost/dev.arventurers.org/shared-testing).

<pre>
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