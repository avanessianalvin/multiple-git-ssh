# multiple-git-ssh
git-bash
	cd .ssh (goto .ssh filder)

1* CREATE SOME KEYS

	ssh-keygen  (creates normal key)
		-f filename (custom file name)
	
**OR

	ssh-keygen -t ed25519 -C "your_email@example.com" (with different file names)

	(.pub is public key next one is private key)


2* CREATE KEY IN EACH GITHUB ACCONT AND PASTE PUBLIC KEY (github>settings>keys)

3* CREATE 'config' FILE	(no extansion in .ssh folder)

>>>config

#Some Account 1
Host github.com-prj1
 HostName github.com
 IdentityFile ~/.ssh/id_ed25519

#Some Account 2
Host github.com-avanessianalvin
 HostName github.com
 IdentityFile ~/.ssh/avanessianalvin_id

...
#comment
Host github.com-SOMESUFFIX to match repository to ssh key
 HostName github.com
 IdentityFile ~./ssh/PRIVATE_KEY_FILE (the one wiht no extension)

4*CONNECT
-- IF THERE IS AN EXISTING REPO ON COMPUTER:

git remote rm origin 
(remove origin if exists)

git remote add origin git@github.com-SOMESUFFIX/weltho/frontend.git  
(this can be got from github each repo has an address like : git@github.com:weltho/frontend.git, edit git@github.com-SOMESUFFIX)

git push -u origin master
(pushes repo to git hub)

-- IF NO REPO ON COMPUTER
git clone git@github.com-SOMESUFFIX/weltho/frontend.git
EDIT SOME AND COMMIT
git push origin master

----------------------------------------------------------------
SOME GIT-BASH COMMANDS:
cd	cd
clear	cls
cat	type


https://www.youtube.com/watch?v=N2hMGEeYR7c
