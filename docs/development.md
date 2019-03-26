# Desenvolvimento

Primeiro é necessário clonar o repositório do github

`$ git clone https://github.com/BRKsReginaldo/multi-radio`

## Ambientes

São necessários alguns arquivos de ambiente para a aplicação funcionar corretamente, em seguida vamos mostrar como configurar
um ambiente completo para desenvolvimento

## Ambiente fiefs (feudos)

O ambiente dos feudos (fiefs) fica na pasta landlord/fiefs, e seu arquivo de ambiente exemplo `env.example` pode ser encontrado
na raiz da pasta fiefs

### Exemplo

```dotenv
NODE_ENV=development
PORT=3000

DB_HOST=fake_host
DB_USER=fake_user
DB_PASSWORD=fake_password
DB_PORT=27017
DB_DB=fake_db

TEST_DB_HOST=fake_host_test
TEST_DB_USER=fake_user_test
TEST_DB_PASSWORD=fake_password_test
TEST_DB_PORT=27017
TEST_DB_DB=fake_db_test
```