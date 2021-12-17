
# Netbox-sync
 
## Description 
A função desse projeto é a sincronização de hosts entre o Netbox e Zabbix.  O Netbox é usado como fonte de verdade, trazendo as informações dos hosts presentes na ferramenta para que sejam monitoradas através da plataforma Zabbix. Utilizamos a ferramenta Ansible para automatizar o processo de sincronização.  

Este módulo utiliza as seguintes ferramentas:
  
Netbox - Responsável pela origem dos dados (Fonte da verdade); 
Ansible - Responsável por sincronizar o Zabbix com as informações do Netbox; 
Zabbix - Ferramenta de monitoramento.   


Mais Informações sobre as ferramentas:  
- [Documentação Netbox](https://netbox.readthedocs.io/en/stable/) 
- [Documentação Zabbix](https://www.zabbix.com/documentation/current/en) 
- [Documentação Ansible](https://docs.ansible.com/ansible_community.html).

#### Dependências 
 - [Zabbix-api](https://www.zabbix.com/documentation/current/pt/manual/api).
 - [Pynetbox](https://pypi.org/project/pynetbox/)

```
pip3 install zabbix-api
pip3 install pynetbox
git clone repo
```
