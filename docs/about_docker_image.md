# Dockerfile para Aplicação Pass-In

O [Dockerfile](https://github.com/JhonataAugust0/devops_nlw/blob/master/Dockerfile) é responsável por definir a imagem Docker da aplicação Pass-In. Ele descreve os estágios de construção necessários para preparar a aplicação para produção.

Estágios do Dockerfile
1. Base
  - Propósito: Este estágio define a imagem base para construir a aplicação Pass-In.
2. Dependências
  - Propósito: Este estágio é responsável por instalar as dependências da aplicação.

- Etapas:
  - Define o diretório de trabalho como /usr/src/app.
  - Copia os arquivos package.json e package-lock.json para o diretório de trabalho.
  - Executa o comando npm install para instalar as dependências.

1. Build
  - Propósito: Este estágio é responsável por construir a aplicação.

- Etapas:
  - Define o diretório de trabalho como /usr/src/app.
  - Copia todos os arquivos para o diretório de trabalho.
  - Copia as dependências instaladas no estágio de dependências para o diretório de trabalho.
  - Executa o comando npm run build para compilar a aplicação.
  - Executa o comando npm prune --production para remover as dependências de desenvolvimento da aplicação.

1. Deploy
  - Propósito: Este estágio é responsável por criar a imagem final da aplicação para implantação.

- Etapas:
  - Define o diretório de trabalho como /usr/src/app.
  - Instala o Prisma globalmente para facilitar o uso.
  - Copia os arquivos necessários do estágio de build para o diretório de trabalho.
  - Executa o comando prisma generate para gerar os artefatos do Prisma.
  - Expõe a porta 3333 para acesso à aplicação.
  - Define o comando npm start como comando padrão para iniciar a aplicação.

### Uso
Para construir a imagem Docker da aplicação Pass-In e subir seu container, execute o seguinte comando na raiz do projeto:

```
docker-compose up -d --build .
```

Observações
- Este Dockerfile segue uma abordagem de múltiplos estágios para otimizar o tamanho da imagem final.
- Ele utiliza o Node.js como base para construir a aplicação, garantindo que todas as dependências necessárias estejam disponíveis.
- O estágio de construção (build) compila a aplicação e remove as dependências de desenvolvimento, mantendo a imagem final o mais enxuta possível.
- O estágio de implantação (deploy) finaliza a preparação da aplicação e expõe a porta necessária para acesso à mesma.