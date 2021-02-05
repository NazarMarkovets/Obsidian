#GitBash
1) Go to the official web site to download Git bash
 [git-scm](https://git-scm.com/)


<hr></hr>

# Config setup folder for git bash
1. Call git bash
2. write: nano ``.bashrc``
3. write

```bash
moveHome() { cd /c/my/repostiories; } 
moveHome
export HOME=/c/my/repositories
```

> /c/my/repostiories - your own path to folder you need;

4. Press `CTR+O`
5. Press `CTR+X` 


 
# Styling Bash
 Settings Article: [set cursor](https://vishnupadmanabhan.com/styling-git-bash/)
 Set Colors : [habr](https://habr.com/ru/post/119436/)
 Find in habr the part below: 
 
 >RED='\\033\[0;31m' #  ${RED}
 > 
> GREEN='\\033\[0;32m' #  ${GREEN}

#### Get start:
 - Go to path find the `git-prompt.sh`
 `C:\Program Files\Git\etc\profile.d`
 
-  Open it with VS code for example. 
 
 ==Attention== - System will ask you to save as root
 

 Change file as example
 
 
##### git-prompt.sh
```bash

if test -f /etc/profile.d/git-sdk.sh
then
 TITLEPREFIX=SDK-${MSYSTEM#MINGW}
else
 TITLEPREFIX=$MSYSTEM
fi

if test -f ~/.config/git/git-prompt.sh

then
 . ~/.config/git/git-prompt.sh
else

 	PS1='\\\[\\033\]0;$TITLEPREFIX:$PWD\\007\\\]' # set window title
 	PS1="$PS1"'\\n' # new line
 	PS1="$PS1"'\\\[\\033\[32m\\\]' # change to green
	PS1="$PS1"'\\@ \\h ' # Time and host<space>
 	PS1="$PS1"'\\\[\\033\[35m\\\]' # change to purple
	PS1="$PS1"'$MSYSTEM ' # show MSYSTEM
	PS1="$PS1"'\\\[\\033\[33m\\\]' # change to brownish yellow
	PS1="$PS1"'\\w' # current working directory

if test -z "$WINELOADERNOEXEC"
then

 	GIT\_EXEC\_PATH="$(git --exec-path 2>/dev/null)"
	COMPLETION\_PATH="${GIT\_EXEC\_PATH%/libexec/git-core}"
	COMPLETION\_PATH="${COMPLETION\_PATH%/lib/git-core}"
	COMPLETION\_PATH="$COMPLETION\_PATH/share/git/completion"

if test -f "$COMPLETION\_PATH/git-prompt.sh"

 then
	 . "$COMPLETION\_PATH/git-completion.bash"
	 . "$COMPLETION\_PATH/git-prompt.sh"
	 PS1="$PS1"'\\\[\\033\[36m\\\]' # change color to cyan
	 PS1="$PS1"'\`\_\_git\_ps1\`' # bash function
 	
	fi

 fi
	 PS1="$PS1"'\\\[\\033\[0m\\\]' # change color
	 PS1="$PS1"'\\n' # new line
	 PS1="$PS1"'\\033\[0;31m $ \\033\[0m' # make red color
fi

MSYS2\_PS1="$PS1" # for detection by MSYS2 SDK's bash.basrc

# Evaluate all user-specific Bash completion scripts (if any)
if test -z "$WINELOADERNOEXEC"
then
 for c in "$HOME"/bash\_completion.d/\*.bash
 do
 # Handle absence of any scripts (or the folder) gracefully
 test ! -f "$c" ||
 . "$c"
 done
fi
```


Then:
 
 Open git bash:
 
 - set color theme:
  ![[Pasted image 20210205020752.png]]
  
  - set text:
  ![[Pasted image 20210205020953.png]]
 
 Result: 
 
 ![[Pasted image 20210205021059.png]]