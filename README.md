# multiple-git-ssh
git-bash
	cd .ssh (goto .ssh filder)

### *  Create some keys

	ssh-keygen  (creates normal key)
		-f filename (custom file name)
	
#### or

	ssh-keygen -t ed25519 -C "your_email@example.com" (with different file names)

	(.pub is public key next one is private key)


## * Create key in each github account and paste public key
(github>settings>keys)

## * Create 'config' file
(no extansion in .ssh folder)



config file

    #some Account 1
     Host github.com-prj1
     HostName github.com
     IdentityFile ~/.ssh/id_ed25519

    #Some Account 2
    Host github.com-avanessianalvin
     HostName github.com
     IdentityFile ~/.ssh/avanessianalvin_id

    ...

help

    #comment
    Host github.com-SOMESUFFIX to match repository to ssh key
     HostName github.com
     IdentityFile ~./ssh/PRIVATE_KEY_FILE (the one wiht no extension)

## Connect
- If there is an existing repo on local

        git remote rm origin 
            (remove origin if exists)

        git remote add origin git@github.com-SOMESUFFIX/weltho/frontend.git  
            (this can be got from github each repo has an address like : git@github.com:weltho/frontend.git, edit git@github.com-SOMESUFFIX)

        git push -u origin master
            (pushes repo to git hub)

- If no local repo
 
        git clone git@github.com-SOMESUFFIX/weltho/frontend.git
            (edit and commit ...)
        git push origin master

----------------------------------------------------------------
Some gitbash comments

        cd:     cd
        clear:	cls
        cat:	type


> https://www.youtube.com/watch?v=N2hMGEeYR7c
