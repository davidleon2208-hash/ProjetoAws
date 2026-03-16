# RELATORIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 16 de março de 2026 
**Empresa:** Abstergo Industries 
**Responsável:** David Perfeito Leôncio

---

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por David Perfeito Leôncio. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos e modernizar a infraestrutura para uma farmácia virtual.

## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, são descritas as etapas do projeto:

### Etapa 1:
* **AWS Lambda**
* **Computação Serverless (sem servidor)**
* **Descrição:** Utilizada para processar a lógica de back-end (como validação de receitas e cálculo de frete) apenas quando houver requisições, eliminando o custo de manter servidores ligados 24/7.

### Etapa 2:
* **Amazon S3 (Simple Storage Service)** 
* **Armazenamento de objetos e hospedagem estática**
* **Descrição:** Hospedagem do front-end da plataforma e armazenamento de imagens dos produtos. O S3 reduz drasticamente os custos de transferência em comparação a instâncias EC2 tradicionais.

### Etapa 3:
* **Amazon Aurora Serverless**  
* **Banco de dados relacional sob demanda** 
* **Descrição:** Gerenciamento dos dados de inventário e clientes. A versão Serverless escala a capacidade automaticamente e desliga-se em períodos de inatividade, gerando economia direta.

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