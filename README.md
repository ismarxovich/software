# Software package for works

#### Download Fedora 34 command

    $ wget https://download.fedoraproject.org/pub/fedora/linux/releases/34/Workstation/x86_64/iso/Fedora-Workstation-Live-x86_64-34-1.2.iso

#### Fedora setup after installing

    $ sudo dnf check-update
    $ sduo dnf update

#### Docker installing

##### Remove old docker packages

    $ sudo dnf remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-selinux \
                  docker-engine-selinux \
                  docker-engine
    
##### Set up the repository

    $ sudo dnf -y install dnf-plugins-core
    $ sudo dnf config-manager \
                    --add-repo \
                    https://download.docker.com/linux/fedora/docker-ce.repo

##### Install Docker Engine

     $ sudo dnf install docker-ce docker-ce-cli containerd.io

##### Start and checkup docker

    $ sudo systemctl start docker
    $ sudo docker run hello-world
    
#### Installing development stack

    $ cd ./Documents
    $ mkdir work_projects
    $ mkdir main_projects 
    $ ls work_projects
    $ mkdir bitrix
    $ cd ./bitrix
    $ git clone [link here]
    $ docker-compose up -d --build
    $ docker ps -a
    
#### Installing software for taking screenshots

    $ sudo dnf install flameshot
    
then keybinding on settings `flameshot gui` to `PrintScr`
    
#### Installing VSCode

    $ sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    $ sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
    $ dnf check-update
    $ sudo dnf install code
    
#### Installing Chrome browser

    $ sudo dnf install fedora-workstation-repositories
    $ sudo dnf config-manager --set-enabled google-chrome
    $ sudo dnf check-update
    $ sudo dnf install google-chrome-stable
    
#### Get FlatHub for Flatpak

    $ sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
    
#### Installing Skype from Flatpak repo

    $ sudo flatpak install flathub com.skype.Client
    
#### Installing Telegram messenger from Flatpak repo

    $ sudo flatpak install flathub org.telegram.desktop

#### Install Gnome 40 Extensions

    $ sudo dnf --enablerepo=updates-testing install gnome-tweaks
