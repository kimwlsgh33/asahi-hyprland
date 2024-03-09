# Dotfiles

## Asahi Linux

Asahi Linux is updated into Fedora Remix

### Configure Minimal

[What is Asahi Linux?](https://asahilinux.org/)

Install
```sh
curl https://alx.sh | sh
```

- [] Network Setting
    - `nmcli show list`
    - `nmcli conn "ssid" password "password"`
    - `ping 8.8.8.8`
    - `sudo dnf install network-manager-applet`

- [] Update repositories 
    - `sudo dnf update`

- [] Install Required Dependencies
    - Defalts : `sudo dnf install git neovim`
    - Browser : `sudo dnf install firefox`
    - Desktop Env : `sudo dnf install hyprland`

- [] Add Shell Aliases
    | alias | command |
    |---    |---      |
    |v|nvim|
    |editv|nvim $HOME/.config/nvim/init.lua|
    |edits|nvim $HOME/.bashrc|
    |src|source .bashrc|

- [] Install Korean Language
    - Render Korean
        - `localectl list-locales`
        - Default Language to Korean : `localectl set-locale LANG=ko_KR.UTF-8`
        - `sudo nvim /etc/locale.conf` and add a line, `LANG=ko_KR.UTF-8`
        - Download [google-noto-fonts](https://fonts.google.com/noto)
        - Unzip fonts by `unzip Noto_Sans_KR.zip`
        - `mkdir ~/.fonts`
        - `mv *.ttf ~/.fonts`
        - Clean font cache by `fc-cache fv`
        - Reboot computer
    - Input Korean

- [] Install Status Bar
    - EWW
        - Rust Up `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
        - Clone EWW `git clone https://github.com/elkowar/eww`
        - Install prerequisites
            - gtk3 `sudo dnf install glib2-devel`
            - gtk3 `sudo dnf install pango-devel`
            - gtk3 `sudo dnf install atk-devel`
            - gtk3 `sudo dnf install gtk3-devel`
            - gtk3 `sudo dnf install gtk-layer-shell-devel`
        - Build EWW `cargo build --release --no-default-features --features=wayland`
        - Configure EWW
            - `cd target/releases`
            - `chmod +x ./eww`
        - Run EWW
            - `./eww daemon`
            - `./eww open <window_name>`
    - Add repo `sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm`
    - [MPD](https://fedoramagazine.org/playing-music-on-your-fedora-terminal-with-mpd-and-ncmpcpp/)
        - Install Music Player Daemon `sudo dnf install mpd`
        - Install Music Manager `sudo dnf install ncmpcpp`

- [] Install Graphic Driver
    - To render video on browser
    
- [] Install Bluetooth Manager
    - To connect bluetooth devices
    - `sudo dnf install bluez bluez-tools blueman`
    - `sudo systemctl enable bluetooth`
    - `sudo systemctl start bluetooth`

- [] [Github credential](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
    - generate ssh key `ssh-keygen -t ed25519 -C "your_email@example.com"`
    - run ssh-agent `eval "$(ssh-agent -s)"`
    - add ssh key to agent `ssh-add ~/.ssh/id_ed25519`
    - add public key to github account in browser

# Development Environments

## C/C++

### Compiler
- gcc : `sudo dnf install gcc` 
- clang : `sudo dnf install clang` 

### Build Tools
- cmake : `sudo dnf install cmake`
- make : already installed by above command

### Language server
- clangd : `sudo dnf install clang-tools-extra`
