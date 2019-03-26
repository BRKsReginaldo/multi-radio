# Entidades Globais

## Fiefs (Feudos)

O fief é uma entidade abstrata responsavel por representar todas as radios do sistema, suas propriedades são:

| Coluna               | Tipo    | Chave           | Obrigatório | Padrão   | Comentário
|----------------------|---------|-----------------|-------------|----------|--------------------------
| uuid                 | string  | primary, unique | true        | null     |
| name                 | string  |                 | true        | null     |
| postgres_db_host     | string  |                 | true        | null     |
| postgres_db_port     | string  |                 | true        | null     |
| postgres_db_user     | string  |                 | true        | null     |
| postgres_db_database | string  |                 | true        | null     |
| postgres_db_password | string  |                 | true        | null     |
| mongo_db_host        | string  |                 | true        | null     |
| mongo_db_port        | string  |                 | true        | null     |
| mongo_db_user        | string  |                 | true        | null     |
| mongo_db_database    | string  |                 | true        | null     |
| mongo_db_password    | string  |                 | true        | null     |
| mongo_db_auth        | string  |                 | true        | null     | database that contains auth information
| status               | integer |                 | true        | 1        | 1 == ativo, 0 == inativo

## Hostnames

O hostname é uma entidade que representa uma de muitas formas de se acessar um fief, o hostname possui algumas propriedades
com:

| Coluna               | Tipo    | Chave           | Obrigatório | Padrão      | Comentário
|----------------------|---------|-----------------|-------------|-------------|---------------------------------
| uuid                 | string  | primary, unique | true        | null        | 
| fqdn                 | string  | unique          | true        | null        | fully qualified domain name
| redirect_to          | string  |                 | false       | null        | redireciona pro link caso exista

## Roles

Um role representa um cargo na aplicação, o role possui diversas permissões 

| Coluna               | Tipo    | Chave           | Obrigatório | Padrão      | Comentário
|----------------------|---------|-----------------|-------------|-------------|---------------------------------
| code                 | string  | primary, unique | true        | null        | 
| name                 | string  |                 | true        | null        | nome do cargo
| description          | string  |                 | true        | null        | descrição do cargo e.g admin


## Permissions

Uma permissão concede acesso a determinado recurso na aplicação

| Coluna               | Tipo    | Chave           | Obrigatório | Padrão      | Comentário
|----------------------|---------|-----------------|-------------|-------------|---------------------------------
| code                 | string  | primary, unique | true        | null        | 
| name                 | string  |                 | true        | null        | nome da permissão
| description          | string  |                 | true        | null        | descrição do cargo e.g Fiefs (Feudos)


## PermissionRole

A relação entre um cargo e uma permissão

| Coluna               | Tipo    | Chave                                    | Obrigatório | Padrão      | Comentário
|----------------------|---------|------------------------------------------|-------------|-------------|--------------
| permission_code      | string  | primary, unique, foreign permissions(id) | true        | null        |
| role_code            | string  | primary, unique, foreign roles(id)       | true        | null        |
| read                 | boolean |                                          | true        | false       | permissão de leitura
| write                | boolean |                                          | true        | false       | permissão de escrita

## User

Um usuário do sistema possui permissões admnistrativas como gerenciamento de hostnames, Fiefs (Feudos), roles, permissions além de
poder responder perguntas na area de suporte

| Coluna               | Tipo    | Chave           | Obrigatório | Padrão      | Comentário
|----------------------|---------|-----------------|-------------|-------------|--------------
| uuid                 | string  | primary, unique | true        | null        | 
| name                 | string  |                 | true        | null        | 
| email                | string  |                 | true        | null        | 
| password             | string  |                 | false       | null        | 

## RoleUser

A relação entre um usuario e seus diversos cargos

| Coluna               | Tipo    | Chave                                    | Obrigatório | Padrão      | Comentário
|----------------------|---------|------------------------------------------|-------------|-------------|--------------
| user_uuid            | string  | primary, unique, foreign permissions(id) | true        | null        |
| role_code            | string  | primary, unique, foreign roles(id)       | true        | null        |

## PermissionUser

A relação entre um usuario e suas respectivas permissões

| Coluna               | Tipo    | Chave                                    | Obrigatório | Padrão      | Comentário
|----------------------|---------|------------------------------------------|-------------|-------------|--------------
| user_uuid            | string  | primary, unique, foreign permissions(id) | true        | null        |
| permision_code       | string  | primary, unique, foreign roles(id)       | true        | null        |
| read                 | boolean |                                          | true        | false       | permissão de leitura
| write                | boolean |                                          | true        | false       | permissão de escrita

## PersonalAccessToken

Um token pessoal permite que a api seja acessada programaticamente conforme as permissões da mesma

| Coluna               | Tipo    | Chave                                    | Obrigatório | Padrão      | Comentário
|----------------------|---------|------------------------------------------|-------------|-------------|--------------
| uuid                 | string  | primary, unique                          | true        | null        |   
| name                 | string  |                                          | true        | null        |   
| description          | string  |                                          | true        | null        |   
| token                | string  | unique                                   | true        | null        |

## PersonalAccessTokenRole

A relação entre um token de acesso pessoal e um cargo

| Coluna                     | Tipo    | Chave                                    | Obrigatório | Padrão      | Comentário
|----------------------------|---------|------------------------------------------|-------------|-------------|--------------
| personal_access_token_uuid | string  | primary                                  | true        | null        |   
| role_id                    | string  | primary                                  | true        | null        |   

## PersonalAccessTokenPermission

A relação entre um token de acesso pessoal e suas permissões

| Coluna                     | Tipo    | Chave                                    | Obrigatório | Padrão      | Comentário
|----------------------------|---------|------------------------------------------|-------------|-------------|--------------
| personal_access_token_uuid | string  | primary                                  | true        | null        |   
| permission_id              | string  | primary                                  | true        | null        |   
| read                       | boolean | primary                                  | true        | null        |   
| write                      | boolean | primary                                  | true        | null        |   