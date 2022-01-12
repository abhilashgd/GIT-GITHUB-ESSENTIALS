# GIT-GITHUB-ESSENTIALS

    -inside local machine
       -Staging area // git add
       -commit history //git commit
    - to store in a remote server //popular ones are listed below
        - github
        -bit bucket
        -aws code commit
        -git lab
      //COMMAND
       - git push
     //Installing Git
      -  https://github.com/git-guides/install-git
      - brew install git
      //Windows additional installations
        - https://gitforwindows.org/
        - https://cmder.net/
        
#GIT COMMANDS
        //verify installation
        % git version
        % git --help
        % ctrl+l // to clear screen
        
        //configure git
        % git config --global user.name "abhilashgd"
        % git config --global user.email "anrewgd@gmail.com"
        % git config --global color.ui auto
        % git config -l
        % q //to come out
        
        //initialising git repository
        % cd Desktop
        % mkdir learning-git
        % ls 
        % cd learning-git
        % ls
        % git init . //creating new project
        % ls -a
        % rm -rf .git
        % git init .
        
      //git add  
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
        
      //git commit
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
   
#Git hub
     
     //Git push
        % git remote add origin git@github.com:abhilashgd/GIT-GITHUB-ESSENTIALS.git
        % git branch -M main
        % git push -u origin main
        
     //SSH key SET UP
        
      
      
    
