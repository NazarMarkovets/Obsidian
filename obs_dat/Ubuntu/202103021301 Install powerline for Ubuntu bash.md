#GitBash 
#Ubuntu

[First install](https://www.ricalo.com/blog/install-powerline-windows/#install-and-configure-powerline-fonts)



##### Add to cd $HOME .bashrc
```bash
# Powerline configuration
if [ -f /usr/share/powerline/bindings/bash/powerline.sh ]; then
  powerline-daemon -q
  POWERLINE_BASH_CONTINUATION=1
  POWERLINE_BASH_SELECT=1
  source /usr/share/powerline/bindings/bash/powerline.sh
fi
```

[secont install](https://github.com/jaspernbrouwer/powerline-gitstatus)


##### cd $HOME
``` bash
sudo apt install powerline-gitstatus
```





If branches does not changed use  - reload powerline

##### bash cd $HOME
```bash
 powerline-daemon --replace
```


