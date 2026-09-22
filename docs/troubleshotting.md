## Troubleshooting


# A.Resolving Git Repository Structure and Push Errors

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

# B.GitHub Push and Rebase Error Resolution

1. I initially faced a GitHub authentication error because GitHub does not support using a normal account password for Git operations over HTTPS. I resolved this by using a GitHub Personal Access Token (PAT) for authentication.
2. After authentication was successful, the git push origin main command was rejected with a "fetch first" error because the remote GitHub repository contained commits that were not present in my local repository. I used git pull --rebase origin main to synchronize the local branch with the remote branch.
3. The rebase initially could not start because there were uncommitted local changes. I committed the current assignment changes and then ran the rebase again. During the rebase, Git reported a conflict with README.md because the local commit deleted the file while the GitHub version had modified it. I resolved the conflict by keeping the GitHub version of README.md, staged the resolved file, and ran git rebase --continue.
4. After all conflicts were resolved, the rebase was ready to complete, allowing me to push the updated local main branch to GitHub using git push origin main.
