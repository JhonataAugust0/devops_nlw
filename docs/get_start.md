# Guia de Início Rápido

## Preparando o Ambiente de Desenvolvimento

Este guia irá orientá-lo passo a passo para configurar seu ambiente de desenvolvimento de forma eficiente e rápida.

1. Instale o [Node.js](https://nodejs.org/en/download) e o npm<br>
Certifique-se de ter o Node.js e o npm instalados em seu sistema. Você pode baixar e instalar o Node.js em nodejs.org. Após a instalação, verifique se o Node.js e o npm estão corretamente configurados em seu terminal executando os seguintes comandos:

```
node -v
npm -v
```


2. Instale o [Docker](https://www.docker.com/get-started/) e o Docker Compose<br>
O Docker e o Docker Compose são essenciais para criar e gerenciar contêineres para nossa aplicação. Você pode baixar e instalar o Docker em docker.com. Certifique-se de que o Docker e o Docker Compose estejam corretamente instalados em seu sistema verificando suas versões:

```
docker -v
docker-compose -v
```


3. Instale o [kubectl](https://kubernetes.io/docs/tasks/tools/), [Helm](https://helm.sh/pt/docs/intro/install/) e [k3d](https://k3d.io/v5.6.0/)<br>
O Kubernetes, Helm e k3d são importantes para orquestrar e gerenciar contêineres em um ambiente de produção. Você pode instalar o Kubernetes usando ferramentas como Minikube ou kind. Instale o Helm em helm.sh. O k3d pode ser instalado seguindo as instruções em k3d.io. Verifique se essas ferramentas estão corretamente instaladas em seu sistema:
```
kubectl version --client
helm version --short
k3d version
```


4. Instale a [CLI do Terraform](https://developer.hashicorp.com/terraform/install?product_intent=terraform)<br>
A CLI do Terraform é necessária para gerenciar a infraestrutura como código. Você pode baixar e instalar o Terraform em terraform.io. Após a instalação, verifique se a CLI do Terraform está corretamente configurada em seu sistema:

```
terraform version
```

5. Clone o Repositório do Projeto
Agora que você configurou todas as ferramentas e dependências necessárias, é hora de clonar o repositório do projeto. Use o seguinte comando para clonar o repositório em seu ambiente de desenvolvimento:

```
https://github.com/JhonataAugust0/devops_nlw.git
```

## Agora é só aproveitar!

Por fim, você pode executar localmente o projeto usando o docker ou o kubernetes, para isso basta usar o docker-compose da seguinte forma após definir as variáveis de ambiente do banco de dados:

```
docker-compose up -d --build  // na raíz do projeto
```

Ou então criar um cluster kubernetes com o k3d, definir um namespace e aplicar os arquivos da pasta k8s para a criação automática:

```
k3d cluster create example-cluster
kubectl create ns example-namespace
kubectl apply -f k8s -n example-namespace
```

E, claro, ao publicar o repositório em seu próprio github, o workflow de CI/CD fará isso autonomamente para você. Somente é preciso que você:
1. Configure os secrets no seu repositório para a autenticação com o docker container registry para a publicação da imagem da apliação.
2. Crie um namespace para o ArgoCD e execute-o conforme informado no arquivo [about_argocd]()!