Usefull youtube video: https://youtu.be/8JJ101D3knE
setting up. 
List of [[Git Commands]]. 

## Set up
### On windows
Go to the following link: https://git-scm.com/downloads, and follow the instructions. 

### On mac
On macOS, check if you have homebrew installed, if not visit this link: https://brew.sh
After homebrew is installed, paste the following command in the command line
```bash
$ brew install git
```


### Setting up your account
configering your name:
```bash
git config --global user. name "Mosh Hamedani"
```
configering your email:
```bash
git config --global user .email programmingwithmosh@gmail.com
```
configering your code editor
```bash
git config --global core.editor "code --wait"
```
to open your configeration file
```bash
git config --global -e
```


##### End of line indications
On windows enter the following command
```bash
git config --global core.autocrlf true
```
On mac enter the following command
```bash
git --version      #checking if git is installed
brew install git
git config --global core.autocrlf input
```
