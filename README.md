# EndeavourOS-Snippets

Opinionated guide to facilitate the configuration of EndeavourOS.



## Update

```shell
sudo pacman -Syu
```

```shell
yay -Syu
```



## Install packages

```shell
sudo pacman -S chromium firefox code bitwarden docker docker-compose cups cups-pdf gimp inkscape telegram-desktop spotify-launcher flameshot audacity htop btop net-tools traceroute speedtest-cli git git-lfs openssh curl wget partitionmanager kdeplasma-addons simple-scan patch noto-fonts-emoji
```

```shell
yay -S microsoft-edge-stable-bin skypeforlinux-stable-bin authy onlyoffice-bin ulauncher cpufetch gpufetch-git zsh-theme-powerlevel10k-git ttf-meslo-nerd-font-powerlevel10k epson-inkjet-printer-escpr epsonscan2
```



## Uninstall unnecessary packages

```shell
sudo pacman -R networkmanager-openvpn openvpn
```



## GIT configuration

```shell
git config --global user.name "Giorgio Reale" ; git config --global user.email "#####EMAIL#####" ; git config --global pull.rebase true ; git config --global init.defaultBranch main ; git config --global core.editor nano
```

```shell
mkdir -p .ssh ; cd .ssh ; ssh-keygen -t ed25519 -f github -C github ; ssh-keygen -t ed25519 -f gitlab -C gitlab
```

Add `github.pub` to https://github.com/settings/keys

Add `gitlab.pub` to https://gitlab.com/-/profile/keys

Add this to `.ssh/config`:

```
# GitHub.com
Host github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/github

# GitLab.com
Host gitlab.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/gitlab
```



## Docker configuration

```shell
sudo systemctl enable docker.service
```

```shell
sudo systemctl start docker.service
```



## CODE - OSS configuration

#### Installing packages

Launch VS Code Quick Open (`Ctrl+P`), for each extension paste the corresponding command and press `enter`:

* Atom Keymap
    ```command
    ext install ms-vscode.atom-keybindings
    ```
* Markdown Preview Github Styling
    ```command
    ext install bierner.markdown-preview-github-styles
    ```
* Material Icon Theme
    ```command
    ext install PKief.material-icon-theme
    ```
* Material Product Icons
    ```command
    ext install PKief.material-product-icons
    ```
* Material Theme
    ```command
    ext install Equinusocio.vsc-material-theme
    ```
* PHP Intelephense
    ```command
    ext install bmewburn.vscode-intelephense-client
    ```



#### Apply settings

Open settings (JSON)

```json
{
    "atomKeymap.promptV3Features": true,
    "editor.multiCursorModifier": "ctrlCmd",
    "editor.formatOnPaste": false,
    "editor.cursorBlinking": "smooth",
    "editor.fontFamily": "Fira Code",
    "editor.fontSize": 14,
    "editor.fontWeight": "400",
    "editor.fontLigatures": true,
    "editor.letterSpacing": 0,
    "editor.lineHeight": 0,
    "editor.dragAndDrop": false,
    "editor.mouseWheelZoom": true,
    "workbench.iconTheme": "material-icon-theme",
    "workbench.tree.indent": 15,
    "workbench.productIconTheme": "material-product-icons",
    "workbench.settings.editor": "json",
    "workbench.colorTheme": "Material Theme Darker",
}
```



## Powerlevel10k configuration

Add the following lines to `.zshrc`

```txt
HISTFILE=~/.histfile
HISTSIZE=1000
SAVEHIST=1000

source /usr/share/zsh-theme-powerlevel10k/powerlevel10k.zsh-theme
```

* Open `Konsole`
* Go to `Settings`
* Go to `Manage Profiles...`
* Go to `New`
* Set as `Default profile`
* Set this `Command`: `/bin/zsh`
* Go to `Appearance`
* Set this `Font`: `MesloLGS NF`
* Go to `Edit`
* Set this `Background`: `#000000`



## Bluetooth

Start bluetooth for the session, will stay disabled after reboot:
```shell
sudo systemctl start bluetooth
```

Enable bluetooth per default, will run after every boot:
```shell
sudo systemctl enable bluetooth
```



## Ulauncher theme

Install [GiorgioReale/Ulauncher-Essential-Dark-Theme](https://github.com/GiorgioReale/Ulauncher-Essential-Dark-Theme)

```shell
mkdir -p ~/.config/ulauncher/user-themes
git clone https://github.com/GiorgioReale/Ulauncher-Essential-Dark-Theme.git \
  ~/.config/ulauncher/user-themes/Essential-Dark-Theme
```



## DuckDuckGo settings

Go to this page: [https://duckduckgo.com/settings#theme](https://duckduckgo.com/settings#theme)

```txt
bin smirk mound weary
```



## Update (again) (and again)

```shell
sudo pacman -Syu
```

```shell
yay -Syu
```
