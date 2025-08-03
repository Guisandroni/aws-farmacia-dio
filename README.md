RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 03/08/2025
Empresa: Abstergo Industries
Responsável: Guilherme Dias

Introdução

Este relatório detalha a implementação de uma arquitetura de nuvem na Abstergo Industries, com base nos princípios de redução de custos, alta disponibilidade e melhoria da segurança. A solução utiliza diversos serviços da Amazon Web Services (AWS) para modernizar a infraestrutura de TI, resolvendo gargalos no armazenamento de dados, na execução de rotinas analíticas e no controle de acessos internos.
Arquitetura da Solução

A arquitetura implementada é uma solução multicamadas, isolada e segura dentro de uma Amazon Virtual Private Cloud (VPC). Os serviços foram configurados para operar de forma a garantir a resiliência e a escalabilidade, com as camadas de aplicação, banco de dados e armazenamento desacopladas e protegidas.
Serviços Implementados
1. Amazon VPC (Virtual Private Cloud)

    Foco: Isolamento e Segurança da Rede

    Descrição do Caso de Uso: A VPC foi a base para toda a arquitetura, criando uma rede virtual privada e isolada dentro da AWS. Utilizamos sub-redes públicas para hospedar recursos que precisam de acesso à internet (como balanceadores de carga e servidores web) e sub-redes privadas para recursos internos, como o banco de dados e os servidores de aplicação, que não podem ser acessados diretamente de fora. Isso garante um nível de segurança fundamental para toda a infraestrutura.

2. Amazon EC2 (Elastic Compute Cloud) com Auto Scaling

    Foco: Processamento e Execução de Aplicações

    Descrição do Caso de Uso: As cargas de trabalho de análises genéticas e aplicações laboratoriais foram migradas de servidores físicos para instâncias Amazon EC2. Para garantir que a aplicação mantenha um desempenho consistente sob alta demanda, implementamos Auto Scaling e um balanceador de carga. Isso permite que a infraestrutura se adapte automaticamente ao tráfego, adicionando ou removendo instâncias EC2 conforme a necessidade.

    Benefícios:

        Performance e Disponibilidade: Aumento na velocidade de processamento e garantia de que a aplicação está sempre disponível.

        Otimização de Custos: Redução do Custo Total de Propriedade (TCO), pagando apenas pela capacidade de computação utilizada.

3. Amazon S3 (Simple Storage Service)

    Foco: Armazenamento Escalável e Seguro

    Descrição do Caso de Uso: O acervo digital de pesquisas clínicas e documentos regulamentares, antes armazenado em servidores locais, foi migrado para o Amazon S3. O S3 é utilizado como um data lake para dados não estruturados. Implementamos versionamento de arquivos para proteção contra exclusão acidental e políticas de ciclo de vida para gerenciar o armazenamento de forma mais econômica, movendo dados para classes mais baratas ao longo do tempo.

    Benefícios:

        Durabilidade e Custo-Benefício: Armazenamento seguro, altamente durável e de baixo custo.

        Automação: Gestão de arquivos e backups automatizada.

4. Amazon RDS (Relational Database Service)

    Foco: Banco de Dados Gerenciado e de Alta Disponibilidade

    Descrição do Caso de Uso: Os bancos de dados de pesquisas clínicas, que exigiam uma solução relacional, foram migrados para o Amazon RDS. Optamos por um motor de banco de dados compatível com PostgreSQL, aproveitando os recursos de gerenciamento da AWS. Isso inclui backups automáticos, replicação de dados entre zonas de disponibilidade (Multi-AZ) e failover automatizado.

    Benefícios:

        Confiabilidade e Alta Disponibilidade: O failover automático para uma réplica em outra AZ garante que o banco de dados esteja sempre disponível, mesmo em caso de falha.

        Gestão Simplificada: A AWS gerencia o provisionamento, o patching e o backup, permitindo que a equipe se concentre no desenvolvimento.

5. AWS IAM (Identity and Access Management)

    Foco: Controle Centralizado de Acessos

    Descrição do Caso de Uso: O controle de acesso aos sistemas, antes descentralizado, foi centralizado através do AWS IAM. Foram definidas políticas de acesso baseadas em papéis (RBAC) e ativada a autenticação multifator (MFA) para garantir que apenas usuários e serviços autorizados possam interagir com os recursos da AWS. O rastreamento de acessos é feito via AWS CloudTrail, garantindo conformidade com normas regulatórias como HIPAA e ANVISA.

    Benefícios:

        Segurança e Conformidade: Controle granular e rastreável dos acessos, fortalecendo a postura de segurança da empresa.


    ✅ Escalabilidade automática para suportar o crescimento futuro.

Essa solução posiciona a Abstergo Industries com uma infraestrutura de TI moderna e robusta, pronta para inovar e expandir seus negócios com segurança e eficiência.
