#GitBash 
#Ubuntu

[First install instruction](https://www.ricalo.com/blog/install-powerline-windows/#install-and-configure-powerline-fonts)
[Second install instruction](https://github.com/jaspernbrouwer/powerline-gitstatus)

Go to console and write:
##### bash $HOME
```shell
> sudo add-apt-repository universe
> sudo apt install --yes powerline

> vim .vimrc

#write 
python3 from powerline.vim import setup as powerline_setup
python3 powerline_setup()
python3 del powerline_setup

set laststatus=2

```

After that:
##### Add to cd $HOME .bashrc
```shell

# Powerline configuration
if [ -f /usr/share/powerline/bindings/bash/powerline.sh ]; then
  powerline-daemon -q
  POWERLINE_BASH_CONTINUATION=1
  POWERLINE_BASH_SELECT=1
  source /usr/share/powerline/bindings/bash/powerline.sh
fi
```
Then apply changes:

##### bash
```shell
source ~/.bashrc
sudo apt install powerline-gitstatus
```

Check path ~/.config. And if there are no path do:

Copy the `/usr/share/powerline/config_files/` folder to `$HOME/.config/powerline`
```shell
mkdir -p $HOME/.config/powerline
cp -R /usr/share/powerline/config_files/* \
      $HOME/.config/powerline/
```
Edit the files there according to your needs. 
A good starting point is the `$HOME/.config/powerline/config.json` file.


##### 
```json
"shell": {
            "colorscheme": "default", //you can change this .config/powerline/colorschemes/shell
            "theme": "default_leftonly", //you can change this by path .config/powerline/themes/shell
            "local_themes": {
                              "continuation": "continuation",
                              "select": "select"
                        	}
		},
```


##### default_left.json (part used for git)
```json
{
"function": "powerline_gitstatus.gitstatus",
"priority": 40
},
```
#### default_left.json (full)
```json
{
        "segments": {
                "left": [
                        {
                                "function": "powerline.segments.common.net.hostname",
                                "priority": 10
                        },
                        {
                                "function": "powerline.segments.common.env.user",
                                "priority": 30
                        },
                        {
                                "function": "powerline.segments.common.env.virtualenv",
                                "priority": 50
                        },
                        {
                                "function": "powerline_gitstatus.gitstatus",
                                "priority": 40
                        },
                        {
                                "function": "powerline.segments.shell.cwd",
                                "priority": 10
                        },
                        {
                                "function": "powerline.segments.shell.jobnum",
                                "priority": 20
                        },
						{
                                "function": "powerline.segments.shell.last_pipe_status",
                                "priority": 10
                        }
                ]
        }
}
```


Go to `.config/powerline/colorschemes/default.json` and add to other groups:

##### default.json
```json
	"gitstatus": { "fg": "gray8", "bg": "gray2", "attrs": [] },
    "gitstatus_branch": { "fg": "gray8", "bg": "gray2", "attrs": [] },
    "gitstatus_branch_clean":    { "fg": "green","bg": "gray2", "attrs": [] },
    "gitstatus_branch_dirty":    { "fg": "gray8","bg": "gray2", "attrs": [] },
    "gitstatus_branch_detached": { "fg": "mediumpurple","bg": "gray2", "attrs": [] },
    "gitstatus_tag":             { "fg": "darkcyan","bg": "gray2", "attrs": [] },
    "gitstatus_behind":          { "fg": "gray10","bg": "gray2", "attrs": [] },
    "gitstatus_ahead":           { "fg": "gray10","bg": "gray2", "attrs": [] },
    "gitstatus_staged":          { "fg": "green","bg": "gray2", "attrs": [] },
    "gitstatus_unmerged":        { "fg": "brightred","bg": "gray2", "attrs": [] },
    "gitstatus_changed":         { "fg": "mediumorange","bg": "gray2", "attrs": [] },
    "gitstatus_untracked":       { "fg": "brightestorange", "bg": "gray2", "attrs": [] },
    "gitstatus_stashed":         { "fg": "darkblue","bg": "gray2", "attrs": [] },
    "gitstatus:divider":         { "fg": "gray8","bg": "gray2", "attrs": [] }
```


If branches are not changed use  - reload powerline

##### bash cd $HOME
```bash
 powerline-daemon --replace
```


