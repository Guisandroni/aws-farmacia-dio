# Relatório de Implementação de Serviços AWS

**Data:** 03/08/2025
**Empresa:** Abstergo Industries
**Responsável:** Guilherme Dias

## Introdução

Este relatório detalha a implementação de uma arquitetura de nuvem na Abstergo Industries. O projeto teve como foco a redução de custos, o aumento da alta disponibilidade e a melhoria da segurança. Para modernizar a infraestrutura de TI, foram utilizados diversos serviços da Amazon Web Services (AWS) para resolver gargalos no armazenamento de dados, na execução de rotinas analíticas e no controle de acessos internos.

---

## Arquitetura da Solução

A arquitetura implementada é uma solução multicamadas, isolada e segura dentro de uma **Amazon Virtual Private Cloud (VPC)**. Os serviços foram configurados para operar com resiliência e escalabilidade, com as camadas de aplicação, banco de dados e armazenamento desacopladas e protegidas.

---

## Serviços Implementados

### 1. Amazon VPC (Virtual Private Cloud)

* **Foco:** Isolamento e segurança da rede.
* **Caso de Uso:** A VPC foi a base de toda a arquitetura, criando uma rede virtual privada e isolada dentro da AWS. Foram usadas sub-redes públicas para hospedar recursos que precisam de acesso à internet e sub-redes privadas para recursos internos, como o banco de dados e os servidores de aplicação. Isso garante um nível de segurança fundamental para toda a infraestrutura.

### 2. Amazon EC2 (Elastic Compute Cloud) com Auto Scaling

* **Foco:** Processamento e execução de aplicações.
* **Caso de Uso:** As cargas de trabalho de análises genéticas e aplicações laboratoriais foram migradas de servidores físicos para instâncias **Amazon EC2**. Para garantir um desempenho consistente sob alta demanda, foram implementados **Auto Scaling** e um balanceador de carga, permitindo que a infraestrutura se adapte automaticamente ao tráfego.
* **Benefícios:**
    * **Performance e Disponibilidade:** Aumento na velocidade de processamento e garantia de que a aplicação está sempre disponível.
    * **Otimização de Custos:** Redução do Custo Total de Propriedade (TCO), pagando apenas pela capacidade de computação utilizada.

### 3. Amazon S3 (Simple Storage Service)

* **Foco:** Armazenamento escalável e seguro.
* **Caso de Uso:** O acervo digital de pesquisas clínicas e documentos regulamentares, antes armazenado em servidores locais, foi migrado para o **Amazon S3**. O S3 é usado como um **data lake** para dados não estruturados. Também foram implementados o versionamento de arquivos para proteção contra exclusão acidental e políticas de ciclo de vida para gerenciar o armazenamento de forma mais econômica.
* **Benefícios:**
    * **Durabilidade e Custo-Benefício:** Armazenamento seguro, altamente durável e de baixo custo.
    * **Automação:** Gestão de arquivos e backups automatizada.

### 4. Amazon RDS (Relational Database Service)

* **Foco:** Banco de dados gerenciado e de alta disponibilidade.
* **Caso de Uso:** Os bancos de dados de pesquisas clínicas foram migrados para o **Amazon RDS**, utilizando um motor de banco de dados compatível com PostgreSQL. Os backups são automáticos, e a replicação de dados entre zonas de disponibilidade (Multi-AZ) com failover automatizado garante a disponibilidade do banco de dados.
* **Benefícios:**
    * **Confiabilidade e Alta Disponibilidade:** O failover automático para uma réplica em outra Zona de Disponibilidade (AZ) garante que o banco de dados esteja sempre disponível, mesmo em caso de falha.
    * **Gestão Simplificada:** A AWS gerencia o provisionamento, o patching e o backup, permitindo que a equipe se concentre no desenvolvimento.

### 5. AWS IAM (Identity and Access Management)

* **Foco:** Controle centralizado de acessos.
* **Caso de Uso:** O controle de acesso aos sistemas, antes descentralizado, foi centralizado através do **AWS IAM**. Foram definidas políticas de acesso baseadas em papéis (**RBAC**) e ativada a autenticação multifator (**MFA**). O rastreamento de acessos é feito via **AWS CloudTrail**, garantindo conformidade com normas regulatórias como HIPAA e ANVISA.
* **Benefícios:**
    * **Segurança e Conformidade:** Controle granular e rastreável dos acessos, fortalecendo a postura de segurança da empresa.

