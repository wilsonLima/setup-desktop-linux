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
- ansible: Instala o Ansible.

- docker: Instala o Docker.
- docker-compose: Instala o Docker Compose.

- virtualbox: Realiza a instalação do VirtualBox.
- vagrant: Realiza a instalação do Vagrant.


Variáveis da Role 
--------------

- docker_compose_version: Versão do Docker Compose.
- vagrant_version: Versão do Vagrant.
- virtualbox_version: versão do VirtualBox


Example Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - setup-desktop-linux

Exemplo de uso da Role com variáveis:

    - hosts: desktop
      roles:
         - { role: setup-desktop-linux, docker_compose_version: 1.23.1, virtualbox_version: 5.2 }

License
-------

BSD
