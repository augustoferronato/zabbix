Baseado no script original [https://github.com/lorf/zapache/](https://github.com/lorf/zapache/)

# Template Apache #

Este template é utilizado para monitorar os serviços apache

## Pré-Requisitos ##

Modulo server-status habilitado no apache a ser monitorado

## Instalação ##

* Copiar o arquivo zapache para a pasta "externalscripts" do Zabbix
* Dar a permissão chmod a+x zapache
* Dar as permissões chown -R zabbix.zabbix zapache
* Importar o arquivo "Template Apache _ zapache.xml"
* Associar aos hosts que tem o Apache Rodando.



## Em caso de autenticação do Server-Status ##
Em caso que for necessário uma autenticação no server-status do apache, na linha 90 do arquivo zapache, alterar:

> fetch_url() { $wget --no-check-certificate --quiet --header "Cache-Control: no-cache" -O - "$@"; }

para:

> fetch_url() { $wget **-u user:password** --no-check-certificate --quiet --header "Cache-Control: no-cache" -O - "$@"; }

Salvar o arquivo.