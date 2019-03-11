# Websites

os websites são a entidade responsavel por identificar os tenants na aplicação, temos rotas disponiveis para todas as 
operações padrões de CRUD

## Rotas

| Rota    | Método | Body                                                    | comentarios
|---------|--------|---------------------------------------------------------|------------------------------------------
| /       | get    |                                                         | lista todos os websites
| /       | post   | [website](../software-engineering/entities.md#websites) | cria um novo website
| /:id    | get    |                                                         | busca um website correspondente com o id
| /:id    | put    | [website](../software-engineering/entities.md#websites) | atualiza um website correspondente com o id com as informações do body
| /:id    | delete |                                                         | delete um website correspondente com o id
