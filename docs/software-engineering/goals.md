# Objetivos

Os objetivos desse projeto é entrar um software multi-tenancy de gerenciamento de radios pessoais, cada radio possuirá
seu próprio dominio, seu controle de acesso e suas próprias estatisticas.

O resultado final deve possuir diversos micro serviços totalmente desacoplados e escalaveis separadamente, com a possibilidade
de colocar todos os serviços em um cluster e escalar verticalmente em qualquer proporção

## Estatisticas

As estatisticas proporcionadas pelo sistema incluem mas não se limitam a 

* quantidade de ouvintes em tempo real
* quantidade de acessos do sistema em determinados periodos (hora | dia | semana | mês)
* quantidade de acessos por plataforma (desktop | tablet | celular)
* quantidade de acessos por região (mapa)
* quantidade de acessos por sistema operacional


## Integração Social

O sistema deverá possuir integração com redes sociais, permitindo que os ouvintes possam curtir | compartilhar as musicas

## Integração com os ouvintes

O sistema deverá possuir uma área para sugestões e críticas dos ouvintes, todos os textos podem ser personalizados

## Banners

O sistema deverá possuir uma area para banners (apenas de imagem)

## Sorteio

O sistema deverá possuir uma area para criar sorteios entre os ouvintes podendo definir regras de sorteio como data de 
inicio / fim, condições como curtiu um determinado numero de musicas ou compartilhou dentro do periodo do sorteio

## Monitoramente

O projeto deve possuir um sistema de monitoramente que detecta problemas no streaming da radio

## Histórico Musical

O sistema deve possuir um serviço que armazena todas as musicas tocadas no player para exibição futura

## Suporte

O sistema deve possuir uma area de suporte para as radios que possuirem duvidas

## Suporte ao usuário

O sistema deve possuir uma area de suporte para os ouvintes caso estes venham a ter problemas com o streaming ou outra parte
do sistema

## Noticias

O sistema deve possuir um sistema de noticias para as radios, visto que a maioria das rádios também postam noticias