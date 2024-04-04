# Helm

O Helm é um gerenciador de pacotes para Kubernetes, permitindo a definição, compartilhamento e implantação de aplicativos e serviços Kubernetes de forma mais eficiente e consistente. Ele facilita a empacotamento de recursos Kubernetes em artefatos chamados "charts", que incluem definições YAML parametrizadas para simplificar a implantação e atualização de aplicativos em ambientes Kubernetes. Com o Helm, os usuários podem automatizar tarefas complexas de implantação, tornando o processo mais escalável e reproduzível.

## Helm: Service

O recurso Helm [Service](https://github.com/JhonataAugust0/devops_nlw/blob/master/deploy/templates/service.yaml) é responsável por expor a aplicação Pass-In dentro do cluster Kubernetes, permitindo a comunicação com outros serviços dentro do cluster.

Este recurso Service está configurado para expor a aplicação Pass-In dentro do cluster Kubernetes, permitindo que outros serviços se comuniquem com ela através do nome do serviço definido.

## Helm: Deployment
O recurso Helm [Deployment](https://github.com/JhonataAugust0/devops_nlw/blob/master/deploy/templates/deployment.yaml) é uma maneira de gerenciar os recursos Kubernetes através de um template YAML parametrizado.

Este recurso Deployment é gerado com base em um template Helm que aceita parâmetros configuráveis, como a contagem de réplicas e as configurações do contêiner, tornando-o flexível e reutilizável em diferentes ambientes de implantação.


## Helm: HorizontalPodAutoscaler (HPA)

O recurso Helm [HorizontalPodAutoscaler](https://github.com/JhonataAugust0/devops_nlw/blob/master/deploy/templates/hpa.yaml) permite dimensionar automaticamente o número de réplicas dos pods da aplicação Pass-In com base na utilização de recursos, como CPU e memória.

Este recurso HorizontalPodAutoscaler é configurado para ajustar automaticamente o número de réplicas dos pods da aplicação Pass-In com base nos recursos de CPU e/ou memória, dentro dos limites definidos.