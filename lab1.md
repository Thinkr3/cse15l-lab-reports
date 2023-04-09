# Lab 1 - Markdown, URLs, Paths, and the Filesystem

## Ingredients
1. Personal Computer
2. VSCode
3. Git Bash (Optional)
4. Internet Connection (Should be in the same network as server)
5. A server with ssh capabilities

## Some Important Github Terminology 
- **git repository**: A folder that tracks the history of edits to its files
- **Github repository**: A git repository online, like a Google Drive folder with history
- **Github pages**: A service that takes a Github repository and builds a website from it (usually relying on conventions, like index.md)
- **Markdown**: A way to write plain text files with a little bit of formatting
- **commit**: A set of changes to a file or multiple files in a repository. A repository history is made up of commits
- **git clone**: A git action to copy a repository from one place to another (usually from somewhere like Github to our computer). Copies the contents of the folder and the entire history – the whole repository.
- **git commit**: A git action to take some changes we’ve made to files and turn them into a commit in the repository’s history
- **git push**: A git action to send commits from one place to another (usually from our computer to Github)

## Some Important Terminal Commands
- **cd \~**: Go to home directory
- **cd <directory\>**: Go to <directory\>
- **ls <directory\>**: List directories in folder
- **ls -lat**: List directories in folder, each in a new line
- **ls -a**: List all hidden directories 
- **cat <directory\> <directory\>**: Concatenates the contents of file and pastes into the terminal.

## Step 1: Installing VSCode
1. Go to [VSCode's Website](https://code.visualstudio.com/) and download the latest version of VSCode
    - Image
2. Open a new VSCode instance on your computer. A new tab should look like this!
    - Image
3. On the top menu bar select `Terminal > New Terminal`, A new tab within VSCode should appear.
    - Image
4. On the right of the terminal tab select the dropdown menu on the the plus sign and select `Git Bash`.
    - Image
5. You're ready to ssh!

## Step 2: ssh the Server
1. On your git bash terminal type the server you want to connect to: `ssh user@some.host.com`
    - Image
2. Then type in the password to your user
    - Image
3. Bam! Connected and ready to code!

## Step 3: Doing Stuff in the Server
1. Consult the Important Terminal Commands for cool server sleuthing techniques
2. `cd` the server:
    - Image
3. `ls` the server:
    - Image
4. `cat` a file:
    - Image
