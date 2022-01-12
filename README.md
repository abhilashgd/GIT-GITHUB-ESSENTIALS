# GIT-GITHUB-ESSENTIALS

   **inside local machine**
    
       >Staging area // git add
       >commit history //git commit
       
   **to store in a remote server //popular ones are listed below**
    
        >github
        >bit bucket
        >aws code commit
        >git lab
       
**Installing Git**
     
      > https://github.com/git-guides/install-git
      > brew install git
  
**Windows additional installations**
        > https://gitforwindows.org/
        > https://cmder.net/
        
#GIT COMMANDS
        **verify installation**
        % git version
        % git --help
        % ctrl+l // to clear screen
        
   **configure git**
        
        % git config --global user.name "abhilashgd"
        % git config --global user.email "anrewgd@gmail.com"
        % git config --global color.ui auto
        % git config -l
        % q //to come out
        
   **initialising git repository**
        % cd Desktop
        % mkdir learning-git
        % ls 
        % cd learning-git
        % ls
        % git init . //creating new project
        % ls -a
        % rm -rf .git
        % git init .
        
   **git add**  
        % touch index.html
        % touch index.js
        % touch main.css
        % git status
        % git add index.html
        % git status
        % git rm --cached index.html
        % git status
        % git add index.html
        % git add index.js
        % git add .
        % git status
        % git rm -r --cached .
        % git status
        % git add .
        % git status
        % mkdir test
        % cd test
        % touch test.js
        % git status
        % git add .
        % git status
        % git add -A
        % git status
        
   **git commit**
        % git status
        % git commit -m "bootstrap project"
        % git status
        % git log //to check commited info
        % q
        % git show <hash code from log> //to display all committed info
        % vi index.js // i //console.log("hello git"); //:wq // cat index.js
        % git status
        % git diff //gives difference betteen commits
        % git add .
        % git status
        % git commit -m "added console.log"
        % git log
        % git show <hash code from log>
        % git restore index.js
        % git diff
        % git status
        % git diff
        % vi main.css //i //body {} //:wq
        % git status
        % git add .
        % git commit -m "asdffgh"
        % git commit --amend -m "added body{} in main.css" //to modify commit msg
  
 ##**Git hub**
  
  **Git push**
  
        % git remote add origin git@github.com:abhilashgd/GIT-GITHUB-ESSENTIALS.git
        % git branch -M main
        % git push -u origin main
        
##**SSH key SET UP**

  **Setting SSH Key from Github**
        profile—>settings—> SSH and GPG keys—>generating ssh keys—> follow the steps
        % ssh-keygen -t ed25519 -C “anrewgd@gmail.com”
        % <enter>
        % <enter>
        % <enter>
        % eval "$(ssh-agent -s)"
        % vi ~/.ssh/config
        Host *
            AddKeysToAgent yes
            UseKeychain yes
            IdentityFile ~/.ssh/id_ed25519
        :wq
        % ssh-add -K ~/.ssh/id_ed25519
        —> Adding a new SSH key to your GitHub account.
        cat ~/.ssh/id_ed25519.pub
        % pbcopy < ~/.ssh/id_ed25519.pub
        profile—>settings—>ssh & gig keys—>  new ssh key —> <paste the copied key> --> add
        
#GIT PUSH CONTD..
        
         % vi main.go // func main(){} //:wq
         % git status
         % git add .
         % git status
         % git commit -m "added main.go with empty main funciton"
         % git log
         % git pull --rebase
         % git push
      
#GIT PULL
        -->open main.go in github, add package main // commit
        % cat main.go
        % git pull //or git pull --rebase
        % cat main.go

#Branches
        
        //main or master (default branches)
        steps
        -- create a branch //make changes // merge to main branch
        //working with branches
            % git branch //to check current branch
            % q
            % git branch -r //to check all branches in remote
            % q
            % git branch -a 
            % q
            % git branch feature-a //to create a new branch named feature-a
            % git branch -a
            % q
            % git checkout feature-a // to switch branch
            % git checkout - // to switch to previous branch
            % git checkout -
            % vi utils.js // i // //TODO implement utils // :wq
            % git status
            % git add .
            % git commit -m "
            % git commit -m "utils.js with todo"
            % git log
            % q
            % git checkout -
            % git log
            % q
            % git checkout -
            % git push --set-upstream origin feature-a
            % git checkout main
            % git checkout -b to-delete
            % git branch -a
            % git checkout -
            % git branch -d to-delete //deletes branch to-delete
  
#MERGE and PULL REQUESTS
            
           GITHUB-->select branch -->compare and pull requests --> create a pull request --> add reviewers (add follg details-->Assignee-->labels-->projects-->issues)
    settings-->add approver
    merge once approved
    
            % git log --oneline
            % git pull
            % git log --oneline
            % git branch -d feature-a
            % git log --oneline
    
#GIT GENERAL WORKFLOW
        
        - pull latest changes from the master (remote repository) to local machine
        - create a new branch ( git checkout -b <branch>)
        - rebase master with local
        - if there are conflicts, resolve
        - stash my commit, bring changes from master and commit my changes, resolve conflicts
        - finally commit my changes to master branch
        
#conflicts


        % git checkout -b feature-xyz
        % cat index.html
        - https://www.w3schools.com/html/
        % vi index.html // add page or use VSCode
        % git add .
        % git commit -m "added index.html con
tent"
        % git push
        % git push --set-upstream origin feature-xyz
        //make changes in index.html through github like adding p1,h1 in body
        //also make changes locally in index.html
        %  git add .
        % git commit -m "added another p tag"
        % git push // will show conflict
        
    //Merging Conflicts
        % git pull // will display conflicts
        ![Screen Shot 2022-01-12 at 4 29 29 PM](https://user-images.githubusercontent.com/21958756/149128018-ddd88a71-ad51-4ee9-9fe1-73f2926909f3.png)
        VSCode conflict display
        -- we can accept cuurent/incoming/both or compare changes or modify file by editing 
        
        % git status
        % git add .
        % git status
        % git commit -m "merge conflict resolved for index.html"
        % git push
        
#Rebase
        //goto main branch, make some changes in index.html and then rebase
        % git pull --rebase origin main
        or
        % git pull -r origin main
       
        // will display conflicts and conflicts needs to be resolved manually
        //open VScode and resolve conflict by accepting changes etc
        
        % git add .
        % git rebase --continue
        % wq
        % git add .
        % git rebase --continue
        % wq
        % git add .
        % git rebase --continue
        % wq
        % git push
        % git push -f
        or
        % git push --force
        -GITHUB--> pull requests-->compare and pull-->create pull request-->merge pull request
        -->ususally we do SQUASH and merge instead of resolving one by one
    
#GIT Clients //Not recommended to use. better use terminal or IDE or VSCode

        - Github Desktop
        - Sourcetree
        
#GIT PODS
        
        - https://www.gitpod.io/docs/browser-extension/
        - To start a workspace from a GitHub project, prefix the GitHub project URL with gitpod.io/# as described in Getting Started.
        
#Building a portfolio

        - https://docs.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax
        

        
        
  
        
        
    

