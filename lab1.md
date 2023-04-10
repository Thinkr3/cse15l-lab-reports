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
    - ![Image](https://user-images.githubusercontent.com/45981739/230802731-b38a2ac2-76ff-429d-8e20-16993eadf354.png)
2. Open a new VSCode instance on your computer. A new tab should look like this!
    - ![Image](https://user-images.githubusercontent.com/45981739/230804209-d92b5660-9456-424f-9167-1334f0bd398e.png)
3. On the top menu bar select `Terminal > New Terminal`, A new tab within VSCode should appear.
    - ![Image](https://user-images.githubusercontent.com/45981739/230804017-1b98157b-0ab6-49dc-bb6e-26e367bff7b9.png)
4. On the right of the terminal tab select the dropdown menu on the the plus sign and select `Git Bash`.
    - ![Image](https://user-images.githubusercontent.com/45981739/230804400-4491a669-bf72-46d0-a81f-fa7d4bbf4a70.png)
5. You're ready to ssh!

## Step 2: ssh the Server
1. On your git bash terminal type the server you want to connect to: `ssh user@some.host.com`
    - ![Image](https://user-images.githubusercontent.com/45981739/230802672-de5ea1b6-c480-405a-8b6a-f3ff6496f1c1.png)
2. Accept the connection between your PC and server
    - ![Image](https://user-images.githubusercontent.com/45981739/230802702-7a9b945d-7c25-4760-aafc-eaf26f8c4f6d.png)
4. Then type in the password to your user
    - ![Image](https://user-images.githubusercontent.com/45981739/230802711-c60fdb13-1824-49cc-ad5a-e03451b774b1.png)
5. Bam! Connected and ready to code!

## Step 3: Doing Stuff in the Server
1. Consult the Important Terminal Commands for cool server sleuthing techniques
2. `cd` the server:
    - ![Image](https://user-images.githubusercontent.com/45981739/230802798-b6d603b9-ce80-471a-bbfb-98212347f704.png)
3. `ls` the server:
    - ![Image](https://user-images.githubusercontent.com/45981739/230802778-adec017a-61d0-4640-9912-599b8f5cc02c.png)
4. `cat` a file:
    - ![Image](https://user-images.githubusercontent.com/45981739/230802862-d9643af9-ea4d-4760-b9fe-cbe96db1db45.png)
5. Remember to close your connection with `Ctrl+D`!
    - ![Image](https://user-images.githubusercontent.com/45981739/230804382-256ec0fa-b8f7-46ca-aabf-73a7313fe6ae.png)

