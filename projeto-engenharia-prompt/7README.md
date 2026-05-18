# 🛠️ SM7 - Engenharia de Software e IA com Bubble.io

<p align="center">
  <img src="https://img.shields.io/badge/Plataforma-Bubble.io-00EEFF?style=for-the-badge&logo=bubble&logoColor=black" alt="Bubble.io">
  <img src="https://img.shields.io/badge/Engenharia_de_Prompt-XML_Directives-FF9900?style=for-the-badge" alt="Prompt Engineering">
  <img src="https://img.shields.io/badge/LLM_Aplicada-Claude_3.5_Sonnet-D97706?style=for-the-badge" alt="Claude 3.5">
</p>

---

## 📝 Descrição do Projeto

Este projeto consiste no desenvolvimento do **OrcaFlow**, um sistema de gestão de orçamentos empresariais construído na plataforma no-code Bubble.io. O design do ecossistema utilizou Engenharia de Prompt Avançada para automatizar a lógica de dados e os workflows operacionais.

Desenvolvido para a disciplina de **Engenharia de Software e IA (2026.1)**, o sistema isola dados por usuário de forma segura. Ele permite cadastrar clientes, gerenciar múltiplos itens e controlar o ciclo de vida de propostas comerciais.

---

## 🗃️ Modelagem do Banco de Dados

O banco de dados relacional foi estruturado em 4 entidades principais geradas a partir do mapeamento contextual:

* **Usuario (User):** Perfis estruturados como Administrador, Vendedor ou Visualizador.
* **Cliente (Client):** Armazena dados de contato e vinculação corporativa do cliente final.
* **Orçamento (Quote):** Controla o título, valor financeiro consolidado, validade e o status da proposta.
* **Item do Orçamento (QuoteItem):** Detalha a descrição, quantidade volumétrica e preço unitário dos serviços.

> 💡 **Boa prática aplicada:** Chaves estrangeiras (FKs) mapeadas estritamente no lado N da relação. Isso evita sobrecarga de carregamento no ecossistema Bubble quando tabelas ultrapassam 100 registros.

### Estados de Ciclo de Vida (Option Sets)
`Pendente` | `Aprovado` | `Rejeitado` | `Em Revisão` | `Expirado`

---

## 🔐 Regras de Privacidade (Multi-Tenancy)

Todas as tabelas possuem regras de privacidade configuradas para garantir o isolamento lógico dos dados:

* **Cliente:** `This Client's Creator is Current User`
* **Orçamento:** `This Quote's Creator is Current User`
* **Item:** `This QuoteItem's Quote's Creator is Current User`

<p align="center">
  <img src="data_privacy%20(1).jpeg" alt="Configuração de privacidade no Bubble" width="600"/>
</p>

---

## ⚙️ Workflows do Sistema

O sistema executa 11 workflows documentados na página de clientes, cobrindo operações críticas de CRUD. Cada ação possui tratamento de exceção para guiar a experiência do usuário.

<p align="center">
  <img src="Workflow%20(1).jpeg" alt="Workflows do sistema no Bubble" width="600"/>
</p>

---

## 🚨 Estratégia de Saída — Vendor Lock-in

**Risco Identificado:** O Bubble retém o código-fonte gerado, criando dependência tecnológica severa da plataforma (*Vendor Lock-in*).

**Mitigação Arquitetural:** Habilitação da **Data API do Bubble** para expor os endpoints e exportar registros em formato JSON de forma limpa:

```plaintext
GET [https://appname.bubbleapps.io/api/1.1/obj/client](https://appname.bubbleapps.io/api/1.1/obj/client)
GET [https://appname.bubbleapps.io/api/1.1/obj/quote](https://appname.bubbleapps.io/api/1.1/obj/quote)
GET [https://appname.bubbleapps.io/api/1.1/obj/quoteitem](https://appname.bubbleapps.io/api/1.1/obj/quoteitem)
```

**Stack de migração planejada:**
- Backend: Node.js + Express
- Banco de Dados: PostgreSQL
- Frontend: React com autenticação JWT
- ORM: Prisma ou Sequelize

## 🚀 Tecnologias Utilizadas

* **Plataforma:** Bubble.io (No-Code)
* **Banco de Dados:** Bubble Database (estrutura relacional)
* **Autenticação:** Sistema nativo do Bubble
* **Documentação:** Rascunho de BD em PDF + Estratégia de saída em TXT

## 📊 Resultados e Aprendizados

* Entrega de um sistema funcional com CRUD completo para clientes e orçamentos.
* Aplicação prática de **boas práticas de modelagem relacional** em ambiente no-code.
* Compreensão do risco de **Vendor Lock-in** e como mitigá-lo com estratégias de exportação de dados.
* Entendimento de que **Engenharia de Software** vai além do código — envolve arquitetura, segurança e planejamento de continuidade.

---
## 🔙 Voltar ao início

<p align="right"><a href="https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira">⬅️ Voltar ao início</a></p>
