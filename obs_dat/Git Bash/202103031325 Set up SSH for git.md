#GitBash 
#Ubuntu 
Open console:
##### cd $HOME
```bash
#enter to console
ssh-keygen -t rsa -b 4096 -C "nazaran237@gmail.io"
	...
#enter password 
Enter file in which to save the key (/home/developer/.ssh/id_rsa): <press Enter>
Enter passphrase: <yourpass>
...

#then write 
eval "$(ssh-agent -s)"
...
ssh-add ~/.ssh/id_rsa
```

Then go to git: Settings/SSH and GPG keys/ new SSH key.
Write title(anything) and for the field ==key== - open console and write:

##### 
```shell
 cat ~/.ssh/id_rsa.pub
```
copy all and paste there

Go to the git local repository:

##### write
```shell
#/path/repository(master)
git remote -v

#output
$ git remote -v
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)

```
SSH won't work after you don't change https URL, for this:


##### Change https to git ssh
```shell
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
#write 
git remote -v

#It was 
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)

#It must be now 
> origin  git@github.com:USERNAME/REPOSITORY.git (fetch)
> origin  git@github.com:USERNAME/REPOSITORY.git (push)

```


Other way but unsecured: 
Set cache for your login and pass for a period of usage:

##### write into bash
```shell
#enable
git config credential.helper 'cache --timeout=300' #300 - 5 min, 3600 - hour

# disable this
git credential-cache exit
```
