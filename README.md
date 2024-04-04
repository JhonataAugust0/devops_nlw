# Introdução

Olá, a documentação deste projeto inicia aqui, abaixo há uma lista dos tópicos da documentação informando a ordem recomendada a segui-la. 

- [Sobre a API](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_api.md)
- [Diagrama do banco de dados](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/database_diagram.md)
- [Sobre o docker-compose](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_docker_compose.md)
- [Sobre o Dockerfile](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_docker_image.md)
- [Integração contínua (GitHub Actions)](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/ci_workflow.md)
- [Kubernetes](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_kubernetes.md)
- Entrega contínua 
  -  [Helm](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_helm.md)
  -  [Argocd](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_argocd.md)
- [Comece aqui](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/get_start.md)
- Extra: [Terraform](https://github.com/JhonataAugust0/devops_nlw/blob/master/docs/about_terraform.md)

O projeto contém uma API de gestão de participantes em eventos, entretanto, seu principal intuito se dá pelo propósito de estudar e esclarecer as práticas de Integração Contínua e Entrega Contínua (CI/CD), em um contexto de desenvolvimento de aplicações baseadas em contêineres.

O projeto foi construído durante o evento NLW Unite da [@rocketseat-education](https://github.com/rocketseat-education) tratando-se de um projeto open-source, mas a documentação e demais atualizações deste repositório a partir do lançamento dessa doc são de minha autoria!

O objetivo principal está na utilização de tecnologias modernas e ferramentas de orquestração de contêineres para facilitar o processo de implantação e operação de nossa aplicação. As principais tecnologias e ferramentas utilizadas neste projeto incluem Docker, Kubernetes, k3d (Kubernetes em Docker), Helm, ArgoCD e GitHub Actions. E a API construída com NestJS, Typescript, prismaORM.

Nesta documentação, você encontrará informações detalhadas sobre como configurar, implantar e gerenciar a API de gestão de participantes em eventos, utilizando as práticas recomendadas de CI/CD e as ferramentas mencionadas anteriormente. Desde a configuração do ambiente de desenvolvimento até a implantação automatizada em diferentes ambientes, buscamos fornecer um guia abrangente para ajudá-lo a entender e aproveitar ao máximo a infraestrutura e os processos implementados neste repositório.

Espero que esta documentação sirva como um recurso valioso para você explorar e compreender as práticas de CI/CD e as tecnologias de contêineres em um contexto real de desenvolvimento de software. 

### Sobre mim 
Olá, me chamo Jhonata, sou estudante de sistemas de informação pela PUC Minas, formado técnico em informática pelo SENAC, possuo 2 anos de experiência como desenvolvedor e estou sempre explorando novas tecnologias em busca de mais aprendizado, sinta-se a vontade para falar comigo!

<a href="https://www.linkedin.com/in/jhonata-augusto-2301541b5/" rel="nofollow">
  <img src="https://github.com/dheereshagrwal/colored-icons/blob/master/public/icons/linkedin/linkedin-horizontal.svg" alt="Linkedin Badge" data-canonical-src="https://img.shields.io/badge/-LinkedIn-blue?style=for-the-badge&amp;logo=Linkedin&amp;logoColor=white&amp;link=https://www.linkedin.com/in/jhonata-augusto-2301541b5/" style="width:100px;">
</a> 

<a href="mailto:jhon.augustosilva@gmail.com">
  <img src="https://github.com/dheereshagrwal/colored-icons/blob/master/public/icons/gmail/gmail-horizontal.svg" alt="Gmail Badge" data-canonical-src="https://img.shields.io/badge/-Gmail-c14438?style=for-the-badge&amp;logo=Gmail&amp;logoColor=white&amp;link=mailto:jhon.augustosilva@gmail.com" style="width:100px;">
</a> 
<a href="https://api.whatsapp.com/send?phone=5582982136275&amp;text=Ol%C3%A1!" rel="nofollow">
  <img src="https://github.com/dheereshagrwal/colored-icons/blob/master/public/icons/whatsapp/whatsapp-vertical.svg" alt="Whatsapp Badge" data-canonical-src="https://img.shields.io/badge/-Whatsapp-4CA143?style=for-the-badge&amp;labelColor=4CA143&amp;logo=whatsapp&amp;logoColor=white&amp;link=https://api.whatsapp.com/send?phone=5582982136275&amp;text=Ol%C3%A1!" style="width:68px;">
