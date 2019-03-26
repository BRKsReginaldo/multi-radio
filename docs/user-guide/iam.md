# identity access management

toda a logica de identificação e acesso dos fiefs (feudos) fica armazenada no microservice `iam` na pasta `landlord/iam`
esse microserviço utiliza um banco sql para armazenar os roles (cargos), permissions (permissões), users (usuarios), 
access_tokens (tokens de acesso temporarios), refresh_tokens (tokens para gerar um novo access token, pode haver até 50 refresh_tokens ativos por usuario)
 existe também uma tabela que armazena os cargos dos usuarios (user_roles), uma que armazena as permissões do cargo (role_permissions)
 e uma que armazena as permissões diretas do usuário (user_permissions)
 
## JWT 

Para permitir que o token seja decodificado em qualquer um dos microserviços sem a necessidade de acessar o microserviço `IAM`
novamente, é utilizado um token jwt contendo as informações do usuario e os cargos e permissões, esse token pode ser decodificado
pelos microserviços utilizando a variavel de ambiente JWT_SECRET que está presente em todos os microserviços que usam autenticação