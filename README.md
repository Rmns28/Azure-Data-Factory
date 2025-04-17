# Projeto Prático - Redundância de Arquivos com Azure Data Factory

## 🔎 Introdução

Neste projeto, vamos aprender como criar um processo completo de **redundância de arquivos** usando os recursos do **Microsoft Azure**. O foco está em usar o **Azure Data Factory** para mover dados de um banco de dados SQL local (on-premises) para o **Azure Data Lake**, salvando os dados em arquivos `.TXT` organizados por camadas como `raw` ou `bronze`.

---

## 🌐 Objetivo

- Criar um fluxo seguro de transferência de dados
- Integrar ambientes locais ao Azure
- Utilizar o Data Factory para transformar e organizar dados
- Gerar arquivos de backup automáticos e estruturados

---

## 🔹 Arquitetura do Projeto

```
[SQL Server Local] → [Integration Runtime] → [Azure Data Factory] → [Azure Data Lake - Blob Storage]
```

*Imagem ilustrativa aqui*

---

## 🔧 Passo a Passo do Projeto

### 1. Criando o Integration Runtime
- No Data Factory, acesse "Infraestrutura de Integração"
- Crie um novo Integration Runtime do tipo "Self-hosted"
- Instale o agente no servidor local

*Imagem ilustrativa aqui*

---

### 2. Conectando ao Banco de Dados SQL Local
- Em "Linked Services", crie uma conexão para seu SQL Server on-premises
- Use as credenciais corretas e selecione o IR criado

*Imagem ilustrativa aqui*

---

### 3. Conectando ao Azure Data Lake (Blob Storage)
- Ainda em "Linked Services", crie uma conexão com sua conta de armazenamento
- Gere as chaves no portal do Azure e cole no Data Factory

*Imagem ilustrativa aqui*

---

### 4. Criando os Datasets
- Crie um dataset para a tabela SQL de origem
- Crie um dataset para a pasta de destino no Blob Storage (formato `.txt`)

*Imagem ilustrativa aqui*

---

### 5. Criando o Pipeline de Cópia
- Crie um novo pipeline
- Adicione a atividade "Copy Data"
- Configure a origem e o destino com os datasets criados

*Imagem ilustrativa aqui*

---

### 6. Configurando o Layout dos Arquivos
- No destino, escolha o formato `.TXT`
- Defina a organização em pastas: `/raw/ano=2025/mes=04/dia=10/`

*Imagem ilustrativa aqui*

---

### 7. Validando e Executando o Pipeline
- Clique em "Validar Tudo"
- Clique em "Publicar"
- Execute o pipeline manualmente ou configure um trigger

*Imagem ilustrativa aqui*

---

### 8. Analisando a Execução
- Veja os detalhes da execução do pipeline
- Verifique os arquivos criados no Blob Storage

*Imagem ilustrativa aqui*

---

## 🧮 O que foi aprendido

- Conectar Azure com recursos on-premises
- Criar pipelines no Azure Data Factory
- Transformar dados relacionais em arquivos estruturados
- Utilizar Blob Storage para backup
- Organizar arquivos em camadas (raw, bronze, etc)

---

## 🌟 Possíveis Evoluções

- Automatizar com triggers agendados
- Adicionar camada silver com dados limpos
- Criar relatórios com Power BI
- Integrar com DataBricks ou Synapse

---

