setup-desktop-linux
=========

Role do Ansible com passos para a pós-instalação de Desktops Linux com programas e ferramentas mais utilizadas.

Distribuições Suportadas pela Role
------------

- Debian 9 ou superior
- Fedora 28 ou superior
- Linux Mint 18 ou superior
- openSUSE Leap 15 ou superior
- openSUSE Tumbleweed
- Ubuntu 18.04 ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
  
- repo: Inclui os repositórios no Sistema.
- extras: Adiciona os repositórios de extras.
  
- update: Realiza atualização dos pacotes.
- default: Instala os pacotes essenciais.
- codecs: Instala os codecs de audio e vídeo.
  
- web: Instala todos os browsers contidos na role.
- chrome: Instala o browser Google Chrome.
- opera: Instala o browser Opera.
- vivaldi: Instala o browser Vivaldi.
- skype: Instala o skype.

- dev: Instala os pacotes de desenvolvimento.
- vscode: Instala o Visual Studio Code.

- docker: Instala o Docker.
- docker-compose: Instala o Docker Compose.

- virtualbox: Realiza a instalação do VirtualBox.
- vagrant: Realiza a instalação do Vagrant.


Variáveis da Role 
--------------

- docker_compose_version: Versão do Docker Compose.
- vagrant_version: Versão do Vagrant.
- virtualbox_version: versão do VirtualBox

Dependências da Role 
--------------

Debian, Linux Mint e Ubuntu:

- openssh-server. Ex.: sudo apt install openssh-server
- python-apt (python 2)
- python3-apt (python 3)
- aptitude

Fedora:

- Pacote python2-dnf. Ex.: sudo dnf install python2-dnf
- Pacote libselinux-python. Ex.: sudo dnf install libselinux-python

openSUSE:

- python-xml
- rpm


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - setup-desktop-linux

Exemplo de uso da Role com variáveis:

    - hosts: desktop
      roles:
         - { role: setup-desktop-linux, docker_compose_version: 1.23.1, virtualbox_version: 5.2 }


Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "web" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, web"
