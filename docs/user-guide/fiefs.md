# Fiefs (Feudos)

os Fiefs (Feudos) são a entidade responsavel por identificar os tenants na aplicação, temos rotas disponiveis para todas as 
operações padrões de CRUD

## Rotas

| Rota    | Método | Body                                                    | comentarios
|---------|--------|---------------------------------------------------------|------------------------------------------
| /       | get    |                                                         | lista todos os Fiefs (Feudos)
| /       | post   | [fief](../software-engineering/entities.md#Fiefs (Feudos)) | cria um novo fief
| /:id    | get    |                                                         | busca um fief correspondente com o id
| /:id    | put    | [fief](../software-engineering/entities.md#Fiefs (Feudos)) | atualiza um fief correspondente com o id com as informações do body
| /:id    | delete |                                                         | delete um fief correspondente com o id

