# linux-configuration

## gnome window common issue

### window top-right button lost

first you need

```bash
sudo apt install gnome-tweaks
```

input command like this

```bash
gsettings set org.gnome.desktop.wm.preferences button-layout ':minimize,maximize,close'
```

or

```bash
gsettings set org.gnome.desktop.wm.preferences button-layout 'close,minimize,maximize:'
```

diff two diverse styles and choose what you like

---

### terminal configuration recommended

|  property  |             val             |
| :--------: | :-------------------------: |
|    col     |             90              |
|    line    |             24              |
| hightlight |            white            |
|   color    | green-char black-background |

### configure shell color

using `dircolors` command

```bash
cd ~
dircolors -p > .dircolors
```

edit .dircolors and select color what you like according to corresponding items

### using oh-my-zsh

clone *oh-my-zsh*

```bash
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```

or

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

change your shell to zsh

if you don't install zsh yet, using the following command

```bash
sudo apt install zsh
```

then

```bash
chsh -s /bin/zsh
```

which means you need logout for using zsh

```bash
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

#### using template for zsh

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

![lost](pictures/p1.png)

in `.zshrc` you can add plugins

![lost](pictures/p2.png)

but then you need download above plugins from github or other websites

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

```bash
git clone https://gitee.com/mirror-hub/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

```bash
git clone https://gitee.com/hailin_cool/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```


```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

till now

## gnome extensions

there two apps can be used to extend gnome

- gnome-tweaks
- gnome-extensions-app

### change filepathname from zh to en

```bash
export LANG=en_US

xdg-user-dirs-gtk-update

export LANG=zh_CH.UTF-8
```

### install monitor

<https://extensions.gnome.org/extension/6682/astra-monitor/>

enjoy it

## sync windows time

```bash
timedatactl set-local-rtc 1
```

```bash
sudo apt install npm
sudo npm install -g pm2
pm2 start hbbs -- -r \[10.10.74.81\] -k _
pm2 start hbbr
pm2 save
pm2 startup
pm2 startup systemd
pm2 save
pm2 unstartup systemd
pm2 save
```

