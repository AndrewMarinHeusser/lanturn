## Git and GitHub Guide

For the purpose of this guide I am going to assume you have no experiance with git or GitHub.
git is a free and open source distributed version control system, it deals on an exclusivly local level tied only to the machine it is installed on.
GitHub is a cloud based hosting service for git repositorys. It allows a user to upload their work and have it stored on remote server and be accesed by multiple users, allowing for large scale cooperation.
Now to begin the guide

First thing is first, create and GitHub account at https://github.com/
Then download and install the git application at https://git-scm.com/downloads

### SSH Keys

Now that you have git installed you need to create your local SSH key
1. Open git and enter the following command substituting in the email address you used when creating your GitHub

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. It will then prompt you to "Enter a file in which to save the key" you can simply hit the enter key to accept the default key location
3. After that you will be prompted to create an SSH Key passphrase, simply type in the passphrase you wish to use and hit enter then enter the passphrase again to confirm when prompted to. NOTE: Do not forget the passphrase or else the entire SSH Key will have to be reset, it would be a good idea to write the passphrase down somewhere securely.

4. Once all thse task have been preformed enter the following command to launch the SSH Agent

```
eval "$(ssh-agent -s)"
```
5. Then you add the SSH Key to  the SSH agent if you created a key with a different name then the default then replace the id_ed25519 with the name you chose. 
```
ssh-add ~/.ssh/id_ed25519
```
This has added the SSH key locally and now must be added to your GitHub account
6. In git enter the following command to add your public SSH Key to your clipboard
```
clip < ~/.ssh/id_ed25519.pub
```
7. Then go to GitHub and click on your profile in the top right corner. Then press the settings button that appears from the drop down menu.

8. On the left side of the screen there will be a button that says SSH and GPG keys, click on it.

9. Then on the right side of the screen press the green "New SSH Key" button

10. In the title field add a name for the key, I would recommand naming it the computer that is being used with this key I.E. Andrew's Laptop or something similar.

11. Make sure the key type is Authentication Key.

12. Then paste the public SSH Key into the Key field and click the green "Add New SSH Key" button.
With all this done the SSH Key should be created and added to your account. Keep in mind if you are planning on working from multiple devices you will need to preform this entire process on each computer you plan on working from.

### Cloning and Repository Set Up























In your file directory go to where you want the project to be stored and open git there then do the following commands

git clone git@github.com:AndrewMarinHeusser/CS4220Projects.git

git status
git add .
git commit -m "Insert Message Here"

(Message should be something like "First commit from Andrew Heusser)

thatll get the repositroy downloaded onto your computer and preform your first commit pushing it up to github

then do these commands:

git branch dev1
git checkout dev1
git push origin dev1
git pull origin dev1

This will create the dev branch which is where we'll be preformin all edits on
The main branch will be purly just for storing the latestly working copy
Ill be incharge of merging things from dev1 to main, just tell me when the portion your working on is completed and Ill get started on merging the branches.


### Understanding the Commands
git add . adds all changes made to your pending local git system
git commit then actually adds it to your local git system along with a message explaining what youve done.
git push takes all the commits you have created and sends it to github allowing the rest of us to access it and storing it in a secure cloud
git pull takes the existing items on github and puts it on your computer making sure your local files are up to date

ALWAYS START BY PREFORMING A PULL COMMAND
This will prevent code conflicts and allow us to all work together smoothly.