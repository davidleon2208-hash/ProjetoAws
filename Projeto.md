# [cite_start]RELATORIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS [cite: 1]

[cite_start]**Data:** 16 de março de 2026 [cite: 2]  
[cite_start]**Empresa:** Abstergo Industries [cite: 3]  
[cite_start]**Responsável:** David Perfeito Leôncio [cite: 4]  

---

## [cite_start]Introdução [cite: 5]
[cite_start]Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por David Perfeito Leôncio. [cite: 6] [cite_start]O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos e modernizar a infraestrutura para uma farmácia virtual. [cite: 7]

## [cite_start]Descrição do Projeto [cite: 8]
[cite_start]O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. [cite: 9] [cite_start]A seguir, são descritas as etapas do projeto: [cite: 10]

### [cite_start]Etapa 1: [cite: 11]
* [cite_start]**AWS Lambda** [cite: 12]  
* [cite_start]**Computação Serverless (sem servidor)** [cite: 13]  
* [cite_start]**Descrição:** Utilizada para processar a lógica de back-end (como validação de receitas e cálculo de frete) apenas quando houver requisições, eliminando o custo de manter servidores ligados 24/7. [cite: 14]

### [cite_start]Etapa 2: [cite: 15]
* [cite_start]**Amazon S3 (Simple Storage Service)** [cite: 16]  
* [cite_start]**Armazenamento de objetos e hospedagem estática** [cite: 17]  
* **Descrição:** Hospedagem do front-end da plataforma e armazenamento de imagens dos produtos. [cite_start]O S3 reduz drasticamente os custos de transferência em comparação a instâncias EC2 tradicionais. [cite: 18]

### [cite_start]Etapa 3: [cite: 19]
* [cite_start]**Amazon Aurora Serverless** [cite: 20]  
* [cite_start]**Banco de dados relacional sob demanda** [cite: 21]  
* **Descrição:** Gerenciamento dos dados de inventário e clientes. [cite_start]A versão Serverless escala a capacidade automaticamente e desliga-se em períodos de inatividade, gerando economia direta. [cite: 22]

---

## Estrutura Técnica Detalhada

### Arquitetura de Pastas (Organização do Código)
Para suportar o desenvolvimento com Java e Docker, o projeto está organizado da seguinte forma:

```text
farmacia-virtual-aws/
├── docker/                 # Configurações Docker
│   ├── Dockerfile          # Imagem para ambiente Java
│   └── docker-compose.yml  # Orquestração local
├── frontend/               # Código para o Amazon S3 (React/HTML)
├── backend/                # Lógica Java (Lambda)
│   ├── src/main/java/      # Controllers, Models e Services
│   └── pom.xml             # Dependências Maven
└── sam-template.yml        # Infraestrutura como Código (AWS SAM)