# ansible-bacula
Configure dinamicamente instâncias do bacula (Clientes, Storages e Diretores) utilizando o Ansible.


You can read this document in english [here](link "Read me!").
## Introdução 
O Objetivo deste projeto é utilizar o Ansible para automatizar o processo de instalação, configuração e comunicação entre daemons do Bacula. 


Este projeto está intrinsecamente relacionado com o projeto [Bacula as a micro-service](link2 "Bacula on Dockerhub"), fornecido pelo PoP-PR e baseia-se nas configurações deste projeto para realizar as automações.
## O que posso fazer com este projeto?
- Configurar novos Diretores.
- Configurar Storages e comunica-los com os diretores.
- Configurar Clientes e comunica-los com os diretores.
## Configurações Adicionais
As receitas podem rodar em uma máquina virtual (fazendo instalação e configuração dos pacotes) ou uma máquina Host de um container Docker (Orquestrando somente a configuração de novos recursos).

Todas as variáveis relacionadas a configuração encontram-se dentro das subpastas /vars/.
## Requirementos
Ansible 2+
## Rodando
```bash
ansible-playbook playbooks/<nome_playbook> --limit <host>  
```
## Playbook de exemplo
```yml
---
- hosts: srv
  gather_facts: yes
  become: yes
  become_method: sudo
  roles:
    - bacula-storage-docker
```
## Licença 
GLP V3
## Suporte
Todo o projeto é distribuído de maneira gratuita e não possui garantia ou suporte. No entanto, sinta-se livre para contribuir com o projeto e melhora-lo!
## Contribua! 
- Faça um Fork de nosso projeto
- Crie uma branch com sua nova feature (git checkout -b - my-new-feature)
- Commite suas mudanças (git commit -am 'Add some feature')
- Empurre para o branch (git push origin my-new-feature)
- Crie um novo Pull Request
## Autores
Equipe do Ponto de Presença da RNP no Paraná (POP-PR RNP)
