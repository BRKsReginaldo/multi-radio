# Regras de Desenvolvimento

## Banco de dados

Cada radio possuirá seu próprio banco de dados, por isso é importante criar uma tática que funcione bem para qualquer
microserviço já que estes serão utilizados em todos os outros

Os bancos escolhidos são postgres e mongodb (para dados granulares)

## Backup

Precisamos de backups do banco de dados, os intervalos serão definidos pelas rádios pois cada intervalo terá diferentes
custos (por hora, a cada 2 / 4 / 6 / 8 / 10 / 12 / 24 horas, semanal, mensal)
