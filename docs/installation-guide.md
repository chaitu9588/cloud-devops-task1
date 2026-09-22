# Installation Guide

## 1.System Requirements

1. Ubuntu Linux
2. Bash
3. Git
4. GitHub
5. SSH
6. Linux networking commands
7. Markdown

## 2.Ubuntu Installation

1.	I have downloaded 24.04.5 version of ubuntu and installed it with help of oracle virtual box of version 7.2.18

2.	Once the installation done, I have Verified the installation using following command:
    
    lsb_release -a

## 3.Then Upadated the system using command:

    sudo apt update
    sudo apt upgrade -y

## 4.Installed essential packages with command:
               
    sudo apt install -y git curl wget unzip openssh-client net-tools tree

## 5.Git Installation

1. Configured git:

   git config --global user.name "username"
   git config --global user.email "useremail"
         
2. And verified using following command:
  
   git config --list           

## 6.Generated ssh key with command:

   ssh-keygen -t ed25519 -C "youremail@example.com"

## 7.Test the SSH connection 

   ssh -T git@github.com

## 8.GitHub Connection

•	Login to github account
•	Click on profile --> go to settings
•	Go to SSH key and GPG key.
•	Click on new key 
•	For Key type, select “Authentication Key”
•	Paste your public key into the Key field.
•	Click Add SSH key.


## 9.Networking Tools

1.	ip addr – Displays the IP addresses and network interfaces configured on the system. 

2.	ping google.com – Checks whether the system can reach google.com over the network and measures the response time. 


3.	ping -c n google.com – Sends exactly n ping packets to google.com and then stops.
EX: ping -c 4 google.com sends 4 packets. 

4.	nslookup – Queries DNS to find the IP address associated with a domain name, or performs reverse DNS lookups. 
5.	curl http://example.com – Sends an HTTP request to the website and displays the response/content in the terminal. 

6.	curl https://example.com – Sends an HTTPS request to the website securely and displays the response/content in the terminal. 

7.	curl -I https://example.com – Sends a request and displays only the HTTP response headers, such as status code, content type, and server information.

8.	ss -tuln – Displays listening TCP and UDP network sockets with their port numbers and addresses. 
•	-t → TCP 
•	-u → UDP 
•	-l → Listening 
•	-n → Show numerical addresses/ports 

9.	netstat -tuln – Displays listening TCP and UDP network connections and their port numbers. It is an older alternative to ss. 

10.	traceroute google.com – Shows the network path (hops/routers) that packets take from your system to google.com, helping identify where network delays or connectivity problems may occur.


## 10. Project Structure

├── cloud-devops-task1
├── configs
├── diagrams
├── docs
│   ├── file2.txt
│   ├── installation-guide.md
│   └── linux-command.md
├── notes
├── README.md
├── screenshots
│   ├── Linux-command-practice-ss.png
│   ├── project setup.png
│   ├── SSH connection test.png
│   └── Tool verification.png
└── scripts


## 11. Bash Automation

1. Define the project name

   PROJECT="Cloud-devops-task1"

   Stores the project name in the PROJECT variable.

2. Create project directories

   mkdir -p "$PROJECT"/{docs,scripts,diagrams,screenshots,configs,notes}

   Creates the main project folder and all required subdirectories automatically.

3. Enter the project directory

   cd "$PROJECMoves into the newly created project directory.

4. Create required files

   touch README.md
   touch .gitignore

5. Creates the README.md and .gitignore files.

   Initialize Git repository

   git init

6. Initializes Git for version control inside the project.

   Add content to README

   echo "# Cloud Computing & DevOps Internship" > README.md

7. Adds the project title to the README.md file.

   Stage all files

   git add .

8. Adds all project files to the Git staging area.

   Create the initial commit

   git commit -m "Initial project setup"

9. Saves the initial project setup as a Git commit.

   Display completion message

   echo "Project initialized successfully."

Displays a message confirming that the project setup is complete.


## 12. Troubleshooting


1.	Problem Faced During Git & GitHub Setup
2.	While setting up my project and pushing the Phase 2 work to GitHub, I initially faced an issue with the Git repository structure. I accidentally initialized Git in my home directory instead of only in the project directory. As a result, Git started showing many files and folders from my home directory as changes.
3.	I identified the issue by checking the Git repository root using:
4.	git rev-parse --show-toplevel
5.	I found that Git was pointing to my home directory instead of my project directory. I removed the incorrect Git repository and initialized Git correctly in my project directory.
6.	I also discovered that the project contained a nested Git repository because I had cloned the GitHub repository inside the project directory. I corrected the repository structure so that the project had only one .git directory at the project root.
7.	After correcting the structure, I connected the local repository to my GitHub repository, changed the branch from master to main, and pulled the existing GitHub history using:
8.	git pull origin main --allow-unrelated-histories
9.	Finally, I staged and committed my Phase 2 documentation and screenshot files successfully. The commit was created with the message:
10.	Add Phase 2 Linux documentation and screenshots
11.	This helped me understand the importance of having the correct Git repository root and maintaining a proper local-to-remote GitHub repository structure.








