☁️ Guia de Estudo AWS Certified Cloud Practitioner (CLF-C02)

Um guia completo com os principais serviços e conceitos para a certificação AWS Cloud Practitioner. Formatado para fácil leitura e consulta.

📚 Índice

1. Domínio 1: Conceitos de Nuvem
2. Domínio 2: Segurança e Conformidade
3. Domínio 3: Tecnologia e Serviços de Nuvem
4. Domínio 4: Faturamento, Preços e Suporte
---

🏛️ Domínio 1: Conceitos de Nuvem


Definições Fundamentais

- Computação em Nuvem: Entrega de recursos de TI sob demanda pela internet com preços de pagamento conforme o uso (pay-as-you-go).
- Agilidade: Acelerar a inovação e o provisionamento de recursos.
- Elasticidade: Escalar recursos para cima ou para baixo conforme a demanda (Scale Out / Scale In).
- Alta Disponibilidade: Garantir que uma aplicação opere continuamente, geralmente usando múltiplas Zonas de Disponibilidade.
- Tolerância a Falhas: Capacidade de um sistema se recuperar de falhas em seus componentes.
- CAPEX vs. OPEX: A nuvem transforma despesas de capital (CAPEX) em despesas operacionais (OPEX).

🏛️ AWS Well-Architected Framework

Um conjunto de melhores práticas para construir na nuvem, baseado em 6 pilares:
- operacional: Excelência Operacional
- 🔒 Segurança
- 🤝 Confiabilidade
- ⚡ Eficiência de Desempenho
- 💰 Otimização de Custos
- 🌱 Sustentabilidade

🏗️ Modelos de Computação e Implantação

- IaaS (Infraestrutura como Serviço): Você gerencia o SO e as aplicações. Ex: Amazon EC2.
- PaaS (Plataforma como Serviço): Você gerencia apenas a aplicação. Ex: AWS Elastic Beanstalk.
- SaaS (Software como Serviço): Produto completo pronto para uso. Ex: AWS Marketplace.
- Modelos de Implantação: Nuvem (tudo na AWS), Híbrido (AWS + On-premises) e On-premises (Nuvem Privada).
---

🔒 Domínio 2: Segurança e Conformidade


🤝 Modelo de Responsabilidade Compartilhada

| Responsabilidade da AWS (Segurança DA Nuvem) | Responsabilidade do Cliente (Segurança NA Nuvem) |
| :--- | :--- |
| 🏢 Infraestrutura Física do Datacenter | 📂 Dados do Cliente e Criptografia |
| 💻 Hardware de Computação, Armazenamento e Rede | 👤 Gerenciamento de Identidade e Acesso (IAM) |
| 🌍 Segurança das Regiões e Zonas de Disponibilidade | ⚙️ Configuração do Sistema Operacional e Aplicações |
| 🛡️ Software Global (ex: RDS, S3, DynamoDB) | 🔥 Configuração de Firewalls (ex: Security Groups) |

🔑 Gerenciamento de Identidade e Acesso (IAM)

Serviço global para gerenciar acesso, baseado no Princípio do Menor Privilégio.
- Usuário (User): Uma pessoa ou aplicação.
- Grupo (Group): Uma coleção de usuários.
- Política (Policy): Documento JSON que define permissões.
- Função (Role): Identidade com permissões temporárias. É a forma mais segura de conceder acesso.
- MFA (Multi-Factor Authentication): Camada de segurança extra. Essencial para o Usuário Root.

🛡️ Serviços de Segurança

- AWS Shield: Proteção contra ataques DDoS. A versão Standard é gratuita.
- AWS WAF: Firewall para aplicações web que protege contra exploits comuns.
- AWS KMS: Cria e gerencia chaves de criptografia.
- Amazon Inspector: Análise automatizada de vulnerabilidades em cargas de trabalho.
- Amazon GuardDuty: Detecção inteligente de ameaças que monitora atividades maliciosas.
- Amazon Macie: Usa Machine Learning para descobrir e proteger dados sensíveis no S3.
- AWS Config: Audita e monitora as configurações dos recursos.
- AWS Security Hub: Visão centralizada de alertas de segurança de vários serviços.
- AWS Artifact: Portal para acessar relatórios de conformidade da AWS.
---

🛠️ Domínio 3: Tecnologia e Serviços de Nuvem


💻 Computação

- Amazon EC2: Servidores virtuais (instâncias) na nuvem.
- Elastic Load Balancing (ELB): Distribui o tráfego entre múltiplas instâncias EC2.
- Amazon EC2 Auto Scaling: Adiciona ou remove instâncias EC2 automaticamente com base na demanda.
- AWS Lambda: Computação Serverless. Execute código sem gerenciar servidores.
- AWS Elastic Beanstalk: Orquestração de serviços para implantar aplicações web (PaaS).
- Amazon ECS / EKS: Serviços para orquestração de contêineres (Docker / Kubernetes).

🗄️ Armazenamento

- Amazon S3: Armazenamento de objetos com escalabilidade "infinita".
- Amazon EBS: "Discos rígidos" de rede de alto desempenho para instâncias EC2.
- Amazon EFS: Armazenamento de arquivos de rede (NFS) compartilhado entre instâncias EC2.
- AWS Storage Gateway: Serviço híbrido que conecta seu ambiente on-premises ao armazenamento da AWS.
- AWS Backup: Serviço centralizado para automação e gerenciamento de backups.

Classes de Armazenamento S3

| Classe | Caso de Uso Principal | Acesso |
| :--- | :--- | :--- |
| S3 Standard | Dados acessados com frequência, uso geral | Milissegundos |
| S3 Intelligent-Tiering | Dados com padrões de acesso desconhecidos ou variáveis | Milissegundos |
| S3 Standard-IA | Dados acessados com pouca frequência, mas que precisam de acesso rápido | Milissegundos |
| S3 Glacier Instant Retrieval | Arquivamento com acesso de milissegundos | Milissegundos |
| S3 Glacier Flexible Retrieval| Arquivamento de longo prazo, flexível (minutos a horas) | Minutos a Horas |
| S3 Glacier Deep Archive | Arquivamento mais barato, para retenção de longo prazo | Horas |

🌐 Redes e Entrega de Conteúdo

- Amazon VPC: Sua rede privada e isolada na nuvem.
- Security Group: Firewall para instâncias EC2 (stateful).
- Network ACL (NACL): Firewall para sub-redes (stateless).
- AWS Direct Connect: Conexão de rede dedicada e privada entre seu datacenter e a AWS.
- AWS VPN: Conexão segura entre sua rede e a VPC através da internet.
- Amazon Route 53: Serviço de DNS global.
- Amazon CloudFront: Rede de Distribuição de Conteúdo (CDN) que entrega dados com baixa latência via Edge Locations.

🗃️ Bancos de Dados

- Amazon RDS: Serviço gerenciado para bancos de dados relacionais (SQL).
- Amazon Aurora: Banco de dados relacional da AWS, de alto desempenho, compatível com MySQL e PostgreSQL.
- Amazon DynamoDB: Banco de dados NoSQL (chave-valor) rápido, flexível e totalmente gerenciado.
- Amazon ElastiCache: Serviço de cache em memória para acelerar aplicações.
- Amazon Redshift: Data Warehouse em escala de petabytes para análise de dados.

🚀 Migração e Análise de Dados

- AWS Snow Family: Dispositivos físicos (Snowcone, Snowball) para transferir grandes volumes de dados.
- AWS DMS: Serviço para migrar bancos de dados para a AWS.
- Amazon Athena: Permite fazer consultas em dados no S3 usando SQL padrão.
- Amazon Kinesis: Coleta, processa e analisa streams de dados em tempo real.

⚙️ Gerenciamento, Automação e Integração

- Amazon CloudWatch: Serviço de monitoramento e observabilidade (métricas, logs, alarmes).
- AWS CloudTrail: Registra todas as chamadas de API na sua conta para auditoria.
- AWS Trusted Advisor: Fornece recomendações para otimizar seu ambiente.
- AWS CloudFormation: Infraestrutura como Código (IaC) para provisionar recursos com templates.
- Amazon SQS: Serviço de fila de mensagens para desacoplar componentes.
- Amazon SNS: Serviço de notificação (publicação/assinatura).
---

💰 Domínio 4: Faturamento, Preços e Suporte


💸 Modelos de Preços e Economia

- On-Demand: Pague por hora/segundo. Máxima flexibilidade.
- Savings Plans: Compromisso de uso ($/hora) por 1 ou 3 anos. Flexível.
- Reserved Instances (RIs): Compromisso com um tipo de instância por 1 ou 3 anos. Menos flexível.
- Spot Instances: Maiores descontos em capacidade ociosa, que pode ser interrompida.
- Tagging (Etiquetas): Essencial para organizar recursos e alocar custos.

📊 Ferramentas de Custo

- AWS Free Tier: Nível gratuito para usar certos serviços com limites.
- AWS Pricing Calculator: Estime os custos mensais de sua arquitetura.
- AWS Cost Explorer: Visualize e analise seus custos e uso.
- AWS Budgets: Defina orçamentos e receba alertas de custo.
- AWS Cost and Usage Report (CUR): O relatório de custos mais detalhado.

📞 Planos de Suporte AWS

| Plano | Custo | Suporte Técnico | Tempo de Resposta (Produção Inativa) | Gerente de Contas (TAM) |
| :--- | :--- | :--- |:--- |:--- |
| Basic | Gratuito | - | - | ❌ Não |
| Developer| Mensal | E-mail (Horário comercial) | < 24 horas | ❌ Não |
| Business | Mensal | 24x7 (E-mail, Chat, Telefone)| < 1 hora | ❌ Não |
| Enterprise| Mensal | 24x7 (E-mail, Chat, Telefone)| < 15 minutos | ✅ Sim |
