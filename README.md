# netbox-sync

## Projeto Netbox-Sync 

#### Objetivo
A função desse projeto é a sincronização de hosts entre o [Netbox](https://netbox.readthedocs.io/en/stable/) e [Zabbix](https://www.zabbix.com/).

O Netbox é usado como fonte de verdade, trazendo as informações dos hosts que são necessárias para que sejam adicionados e monitorados a partir da plataforma de monitoramento Zabbix. Para isso utilizamos a ferramenta de automação e gerenciamento [Ansible](https://docs.ansible.com/ansible_community.html).

## Construção do Inventário Ansible
A primeira etapa é a construção do inventário com as informações vindas do Netbox. Nessa etapa é executado o script responsável por coletar as informações dos hosts e a partir dessas informações construir o inventário utilizando o plug-in [netbox.netbox.nb_inventory](https://docs.ansible.com/ansible/latest/collections/netbox/netbox/index.html).
Para a construção do inventário, os hosts foram divididos em grupos de hosts. Grupos que são classificados por tags.Essas tags são definidas no Netbox, o Ansible apenas agrupa as máquinas que possuem a mesma tag.
Mais informações sobre grupos, consulte a documentação [Ansible](https://docs.ansible.com/ansible_community.htm).

## Instalando e configurando o Zabbix Agent
Após a construção do inventário com os hosts divididos por grupos, a próxima etapa é a configuração das máquinas para que possam ser adicionadas à plataforma Zabbix. Para isso é necessário que seja instalado o Zabbix Agent nos hosts.

No playbook "install and confugure zabbix agent" estão as tasks responsáveis pela instalação e configuração do Zabbix agent e outros pacotes necessários nas máquinas. Foi selecionado um grupo de hosts específico para a instalação dos pacotes.
Para mais informações sobre a plataforma Zabbix e o Zabbix-agent consulte a documentação [Zabbix](https://www.zabbix.com/documentation/current/en/).

## Dependências
* [zabbix-api](https://www.zabbix.com/documentation/current/pt/manual/api)


### configuracao

Para configurar as senhas copie o arquivo senhas-default para senhras e altere conforme sua necessidade

```
$ cp vars/senhas-default vars/senhas
$ echo '<utilize seu editor de texto para alterar as senhas>'

```