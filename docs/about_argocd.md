# ArgoCD

O [ArgoCD](https://github.com/JhonataAugust0/devops_nlw/blob/master/devops_deploy_cross/apps/passin/argo.yaml) é responsável por definir e gerenciar a implantação contínua de uma aplicação a partir de um repositório Git para um cluster Kubernetes.

Este recurso está configurado para implantar a aplicação Pass-In a partir do repositório Git especificado para o namespace nlw no cluster Kubernetes. Ele define uma política de sincronização automática que realiza a implantação contínua da aplicação e executa a limpeza de recursos não gerenciados.

## ArgoCD: Repository

O ArgoCD [Repository](https://github.com/JhonataAugust0/devops_nlw/blob/master/devops_deploy_cross/apps/passin/repository.yaml), ou repositório do ArgoCD, é um componente que armazena as definições de aplicativos e as configurações necessárias para a implantação contínua de aplicativos em clusters Kubernetes. Ele desempenha um papel fundamental no fluxo de trabalho do ArgoCD, fornecendo uma fonte centralizada de definições de aplicativos e recursos relacionados.

O repositório ArgoCD pode ser configurado para se integrar com vários sistemas de controle de versão, como GitHub, GitLab, Bitbucket, entre outros. Ele contém os arquivos YAML que descrevem as aplicações a serem implantadas, juntamente com as configurações de sincronização e políticas de implantação.

Por meio do repositório do ArgoCD, os usuários podem versionar as definições de aplicativos, rastrear alterações ao longo do tempo e colaborar de forma eficaz na configuração e implantação de aplicativos Kubernetes. Além disso, ele permite que as equipes gerenciem de forma centralizada as configurações de implantação, promovendo a consistência e a governança no ciclo de vida das aplicações.

## Configuração

Para iniciar o argo, você precisa criar um namespace dedicado para ele no cluster da aplicação, para isso basta executar:

```
kubectl create ns argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

cd /devops_deploy_cross/
kubectl apply -n argocd -f apps/passin
```

Obs.: O apply -n argocd -f apps/passin é necessário apenas uma vez por projeto, a partir dessa execução, toda e qualquer alteração que for feita na branch principal do projeto será construída autonomamente enquanto os serviços estiverem no ar!
