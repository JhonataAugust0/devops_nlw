## Kubernetes Service

O recurso Kubernetes [Service](https://github.com/JhonataAugust0/devops_nlw/blob/master/k8s/service.yml) é responsável por expor a aplicação Pass-In dentro do cluster Kubernetes. Ele direciona o tráfego para as instâncias dos pods que correspondem ao seletor 'app: passin'.

O Service está configurado para ouvir na porta 80 e redirecionar o tráfego para os pods que expõem a porta 3333, onde a aplicação Pass-In está sendo executada.

## Kubernetes Deployment 

O recurso Kubernetes [Deployment](https://github.com/JhonataAugust0/devops_nlw/blob/master/k8s/deploymen.yml) é responsável por gerenciar o estado do conjunto de réplicas dos pods da aplicação Pass-In.

O Deployment está configurado para garantir que cinco réplicas da aplicação Pass-In estejam sempre em execução no cluster Kubernetes.

## Configuração

Para executar a aplicação no kubernetes, é necessário criar um cluster e um namespace dedicados, e isso é muito simples, você pode ver no [get_start](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/get_start.md)!
