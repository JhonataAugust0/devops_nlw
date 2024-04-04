# Docker-Compose da Aplicação Pass-In

Este documento fornece uma visão geral detalhada do arquivo [docker-compose.yml](https://github.com/JhonataAugust0/devops_nlw/blob/master/docker-compose.yaml), incluindo informações sobre os serviços, configurações, dependências, redes e volumes. Ela serve como um guia útil para entender a infraestrutura da aplicação Pass-In e como os diferentes componentes se relacionam entre si.

O arquivo docker-compose.yml contém a configuração para a execução de serviços relacionados à aplicação Pass-In. Ele define dois serviços principais: um banco de dados PostgreSQL e a API do aplicativo Pass-In.

## Serviços
- PostgreSQL
Propósito: Este serviço fornece um banco de dados PostgreSQL para armazenamento de dados relacionados à aplicação Pass-In.
  - Configurações:
  - Imagem Docker: postgres:16.2-alpine3.19
  - Contêiner name: db-pass-in
  - Portas Expostas: 5432:5432
  - Variáveis de Ambiente:
    - POSTGRES_USER: Usuário do PostgreSQL.
    - POSTGRES_PASSWORD: Senha do PostgreSQL.
    - POSTGRES_DB: Nome do banco de dados PostgreSQL.
  - Volume: O volume db é utilizado para persistir os dados do banco de dados.
  - Healthcheck: Um healthcheck é configurado para garantir a saúde do serviço PostgreSQL. O comando pg_isready é utilizado para verificar a disponibilidade do banco de dados.
- API Pass-In
Propósito: Este serviço é fornece a API Pass-In.
  - Configurações:
  - Contexto de Build: O contexto de build é o diretório atual.
  - Contêiner Nome: api-pass-in
  - Portas Expostas: 3001:3333
  - Variáveis de Ambiente:
    - DATABASE_URL: URL de conexão com o banco de dados PostgreSQL.
    - API_BASE_URL: URL base para a API.
  - Dependências: Este serviço depende do serviço PostgreSQL para funcionar corretamente.
  - Rede: O serviço api-pass-in está conectado à rede passin, permitindo comunicação com outros serviços na mesma rede.

## Dependências
O serviço api-pass-in depende do serviço PostgreSQL para funcionar corretamente. O docker-compose garante que o PostgreSQL esteja pronto antes de iniciar a API.

## Redes
Uma rede personalizada chamada passin é criada para conectar os serviços. Esta rede permite a comunicação entre os serviços api-pass-in e PostgreSQL.
 
## Volumes
O volume db é utilizado para persistir os dados do banco de dados PostgreSQL. Isso garante que os dados não sejam perdidos entre os reinícios dos contêineres.
