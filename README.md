# Understanding Git
Let us start!

## What is Git?

An open-source version control system. 
- Version Control System:
    Management of changes performed in a file, document, code or any piece of 
    information. 
    
    Simply put, It's a way to track our code changes, allowing us to save our initial
    version of the code, update the code by committing changes directly into the code in real time. We can hop back to previous versions, allows us to check for bugs/errors. 

## Difference between Git and Github:

Git: A tool to track changes in the code. Allows developers to collaborate with one another, tracking revisions and efficiently managing codebases.

GitHub: A web-based platform that is used to host repositories along with collaboration tools for developers. 

## Common terms used:

- Directory: It is refered to as a folder. 
- Terminal: Interface for text commands.
- CLI: Command Line Interface.
- cd: Change directory
- Code Editor: An environment that lets us edit or write code.
- Repository: A folder or a place where we can store our project.

## Common Git commands:

- clone: Clones the repo existing in GitHub into the local machine.
- add: Track your files and changes in Git.
- commit: Save your files in Git.
- push: Upload your git commits to a remote repo like GitHub.
- pull: Opposite of pull; Download changes from the remote repo into your local machine.
- status: Check which files need to be committed or is being tracked.
- init: Creates a new repo from scratch in the current directory.

## Understanding SSH and the "Common Mistake":

### Creating a local repo via Windows Powershell:

**Move to your preferred directory that you want your local repo to be initialized.**
```bash
New-Item -ItemType Directory -Name "Folder_Name"
cd Folder_Name 
git init
```
I created a folder "Demo" in my preferred directory. I entered that folder and initialized my new local repo using "git init".

### Creating .md file:

```bash
New-Item -ItemType File -Name "File_Name.md"
```
I created a file "README.md".

### Add, commit and push changes:

```bash
git add . 
git commit -m "Successfully created File_Name.md"
git push origin master
```
Here as I try to push my changes to the GitHub, it'll display an error stating: 
**"fatal: 'origin' does not appear to be a git repository"**
This error occured since our remote repository doesn't exist. 

### Create a remote repository in GitHub:

- Click on the profile located on top right corner.
- In the dropdown menu, choose "Your repositories".
- Click on "New" corresponding to the Search bar with the placeholder, "Find a repository".
- Insert your preferred repository name. (In my case, I wrote down "Demo")
- Scroll down and select "Create repository".

### Configuring SSH:

Furthermore, To push into the remote repo, We need to configure our local machine's SSH and add it to the GitHub to prove our identity. 
```bash
ssh-keygen -t rsa -b 4096 -C "your_email"
```
Where,  "-t" refers to the type of encryption key to generate.
        "-b" refers to its strength (Number of bits in the key).
        "-C" refers to the email address.
**This command will generate public/private key and save it to the default directory.**

#### Copying the public key from our local machine:

- cd to the default directory where the keys are located.
- List files using "ls".
- "id_rsa" and "id_rsa.pub" are shown.
**id_rsa represent the private key and the id_rsa.pub is the public key.**
We use public key and store our private key safely in the local machine. We do this; such that when we communicate with GitHub, it'll be able to recognize our machine through the private key present in our machine. Since, only the private key can generate the corresponding public key present in the GitHub. 
**Moving on...**
- View the id_rsa.pub using, "cat id_rsa.pub" command. This will show our public key.
- Select and copy the key, "SHA.....your email_address".

#### Adding the key to our GitHub:

- Click on your Profile.
- In the Dropdown menu, navigate to Settings.
- Under Access, Click "SSH and GPG keys".
- Click on "New SSH key".
- Input your preferred name under "Title".
- Under "Key", paste the copied ida_rsa.pub. 
Now, your local machine is identified to the GitHub.

### Add, commit and push changes Contd:

Continuing from before:
```bash
git add . 
git commit -m "Successfully created File_Name.md"
git push origin master
```
This will now work without any hiccups. 

