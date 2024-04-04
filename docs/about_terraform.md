## Terraform

O Terraform, desenvolvido pela HashiCorp, é uma ferramenta essencial para automatizar a infraestrutura por meio de uma abordagem de código. Ele permite aos usuários definir e gerenciar recursos de infraestrutura, como servidores, redes e bancos de dados, de forma declarativa, usando arquivos de configuração no formato HCL (HashiCorp Configuration Language). Com o Terraform, é possível provisionar e gerenciar a infraestrutura de maneira previsível e escalável, garantindo a consistência e a integridade ao longo do ciclo de vida dos recursos.

Além disso, o Terraform oferece suporte a vários provedores de nuvem e infraestrutura, permitindo aos usuários provisionar recursos em ambientes como AWS, Azure, Google Cloud, além de infraestrutura local. Com sua capacidade de automatizar a criação, atualização e remoção de recursos, o Terraform simplifica e agiliza o processo de gestão da infraestrutura, tornando-o uma escolha popular entre os profissionais de DevOps e engenheiros de infraestrutura.

O arquivo [providers](https://github.com/JhonataAugust0/devops_nlw/blob/master/terraform/providers.tf) é configurado para autenticar-se na API da DigitalOcean usando um token de acesso fornecido como variável.

O arquivo [main.tf](https://github.com/JhonataAugust0/devops_nlw/blob/master/terraform/main.tf) define a criação de um cluster de banco de dados PostgreSQL na DigitalOcean. 

O recurso digitalocean_database_cluster define as configurações do cluster de banco de dados, como nome, versão do PostgreSQL, região e tamanho do nó. Já o recurso recurso digitalocean_database_db cria um banco de dados dentro do cluster definido anteriormente. Ele depende do provisionamento bem-sucedido do cluster de banco de dados.
