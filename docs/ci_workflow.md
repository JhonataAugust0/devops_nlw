# Fluxo de de trabalho do GitHub Actions para CI:

Esta documentação fornece uma visão geral do fluxo de trabalho do GitHub Actions para Integração Contínua (CI), explicando seus acionadores, jobs e passos. Isso serve como um guia útil para entender como a construção e a implantação automatizadas são realizadas no contexto deste projeto.

O fluxo de trabalho denominado ["CI"](https://github.com/JhonataAugust0/devops_nlw/blob/master/.github/workflows/ci.yml) é responsável por automatizar o processo de construção e implantação de uma imagem Docker para a aplicação.

## Detalhes do Fluxo de Trabalho

- Acionadores (on):
  - O fluxo de trabalho é acionado em cada push para a branch master.
- Jobs:
  - build-and-push: Este job realiza a construção e o envio da imagem Docker.
    - Nome: Build and push
    - Ambiente de Execução: Ubuntu (ubuntu-latest)
    - Passos:
      - Checkout: Baixa o código fonte do repositório.
      - Generate sha: Gera um hash SHA para identificar exclusivamente a versão da imagem.
      - Build docker image: Constrói a imagem Docker usando o hash SHA gerado.
      - Log into the container registry: Realiza o login no registro de contêineres.
      - Push image: Envia a imagem Docker para o registro de contêineres, marcando-a com o hash SHA e a tag "latest".
      - Update image tag: Atualiza a tag da imagem no arquivo de configuração Helm (values.yaml) com o hash SHA gerado.

## Observações
- Este fluxo de trabalho é acionado automaticamente a cada push para a branch master, garantindo que cada alteração no código seja testada e implantada continuamente.
- O job build-and-push realiza a construção da imagem Docker, seu envio para o registro de contêineres e a atualização da tag da imagem no arquivo de configuração Helm, facilitando a implantação em um ambiente Kubernetes.