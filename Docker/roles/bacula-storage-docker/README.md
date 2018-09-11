Bacula Storage Docker
=========
Descrição 
---------

Esta receita configura um container docker que contém um daemon do bacula-sd instalado. A configuração da-se por estabelecer a comunicação entre o container target e um container rodando o daemon do bacula-director.

Você deve dar atenção ao arquivo vars/main.yml e fazer as alterações necessárias para condizer com seu ambiente.


Requerimentos 
------------

Esta receita trabalha em conjunto com o projeto [Bacula](http://172.16.0.28/pop-pr/bacula "Bacula on Gitlab") e esta configurada para rodar em uma maquina host e não no próprio container, para tanto, esta receita utiliza de algumas diretivas diferentes, como por exemplo as cópias de arquivo para o volume de persistencia do container, além de handlers diferenciados com scripts, entre outras. 

Variaveis da Role
--------------

director_address: Hostname ou endereço da maquina host do container do diretor.
director_name: O nome do diretor, como especificado nos arquivos de configuração do bacula: bacula-dir.conf 
director_docker_data: Volume de persistencia do container diretor, atualmente montado em: /mnt/docker_data/bacula/director/data
director_container_name: Nome do container do Diretor (vide docker-compose)
storage_container_name: Nome do container Storage (vide docker-compose)
archive_device: Diretório que servirá para armazenamento dos backups, atualmente /storage/bacula
storage_docker_data: Volume de persistencia do container storage, atualmente montado em: /mnt/docker_data/bacula/bstorage/data

Playbook Exemplo
----------------

---
  - hosts: srv
    gather_facts: yes
    become: yes
    become_method: sudo
    roles:
      - bacula-storage-docker

License
-------

BSD