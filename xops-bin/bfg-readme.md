# https://rtyley.github.io/bfg-repo-cleaner/
+ Removing Crazy Big Files
+ Removing Passwords, Credentials & other Private data
<br>
## Usage
### example
+ java -jar bfg.jar --strip-blobs-bigger-than 100M some-big-repo.git
+ git reflog expire --expire=now --all && git gc --prune=now --aggressive

In all these examples bfg is an alias for java -jar bfg.jar.

Delete all files named 'id_rsa' or 'id_dsa' :

$ bfg --delete-files id_{dsa,rsa}  my-repo.git
Remove all blobs bigger than 50 megabytes :

$ bfg --strip-blobs-bigger-than 50M  my-repo.git
Replace all passwords listed in a file (prefix lines 'regex:' or 'glob:' if required) with ***REMOVED*** wherever they occur in your repository :

$ bfg --replace-text passwords.txt  my-repo.git
Remove all folders or files named '.git' - a reserved filename in Git. These often become a problem when migrating to Git from other source-control systems like Mercurial :

$ bfg --delete-folders .git --delete-files .git  --no-blob-protection  my-repo.git
For further command-line options, you can run the BFG without any arguments, which will output text like this.