 # Gerrit 

**Gerrit** is a source code management platform like GitHub, it can manage multiple repositories and git resources

Gerrit version control system is git, it's provide code review and access control on git repositories 
## Code Review 
is a process of quality assurance that invoves others reading and cheacking source code to offer suggestions, recommendations or approvals
**Gerrit** is web base code review, Read code, Comment on the code and make the code better.  


## Git Server
* Grand ACLS
* Control access to the repositories, not just how can push code  into repository, but also what branches they can see, and what branches they can fetch or clone.
* Support SSH and HTTP 

## Deployment 
WAR file (tomcat, jetty)



 

# Branching Strategy 
* Master -> SPSMAIN
* Release Streams: streams that created from the master
* Side Streams: created from release streams, its created when we made a piece of work  

# Stream Access 
there are three state of the stream:
1. open
2. Restricted
3. Locked



1.  Log into [Gerrit](https://gerrit.app.alcatel-lucent.com/gerrit)
2.  Create your SSH public key:
	1.  Click on your name on the top right-hand side of the screen.	    
	2.  Click on “Settings”.	    
	3.  Click on “SSH Public Keys”.	    
	4.  Gerrit is now ready to accept your SSH public key…
3. On your development system, as your ‘nix user, generate a public key 
(if you don’t already have one):

  
## ssh-keygen 

Generating public/private rsa key pair. Enter file in which to save the key 

(/users/<strong style="background-color: transparent;">your-username</strong>/.ssh/id_rsa): 

Enter passphrase (empty for no passphrase): Enter same passphrase again: 

Your identification has been saved in /users/<strong style="background-color: transparent;"> your-username</strong> /.ssh/id_rsa. 

Your public key has been saved in /users/<strong style="background-color: transparent;"> your-username</strong> /.ssh/id_rsa.pub. 

The key fingerprint is: dd:12:d7:60:c6:f3:4b:d5:21:6e:de:d6:0d:f2:f4:5b <strong style="background-color: transparent;">

your-username</strong>@<strong style="background-color: transparent;">your-host </strong>

The key's randomart image is: +--[ RSA 2048]----+ ... +-----------------+



4. Copy the contents of public key file “~/.ssh/id_rsa.pub” to the text box in Gerrit.





# Clone 
* mkdir /opt/javaProjects/sps
* cd /opt/javaProjects/sps
* git clone ssh://<your_username>@gerrit.ext.net.nokia.com:29418/DSC_SPS/tpapps && mkdir -p tpapps/.git/hooks/ && scp -p -P 29418 <your_username>@gerrit.ext.net.nokia.com:hooks/commit-msg tpapps/.git/hooks/
* cd tpapps
-   git checkout <branch_you_care_about> (e.g. SPSMAIN, or a versioned branch like SPS_18_7)






# JIRA
JERA is popular planning tracking managing tool and issue trackers 

