# 🛠️ SM7 - Engenharia de Software e IA com Bubble.io

<p align="center">
  <img src="https://img.shields.io/badge/Plataforma-Bubble.io-00EEFF?style=for-the-badge&logo=bubble&logoColor=black" alt="Bubble.io">
  <img src="https://img.shields.io/badge/Engenharia_de_Prompt-XML_Directives-FF9900?style=for-the-badge" alt="Prompt Engineering">
  <img src="https://img.shields.io/badge/LLM_Aplicada-Claude_3.5_Sonnet-D97706?style=for-the-badge" alt="Claude 3.5">
</p>

---

## 📝 Descrição do Projeto

Este projeto consistiu no desenvolvimento do **OrcaFlow**, um sistema de gestão de orçamentos empresariais construído na plataforma no-code Bubble.io. O design do software utilizou Engenharia de Prompt Avançada para automatizar a lógica de dados e workflows.

Desenvolvido para a disciplina de **Engenharia de Software e IA (2026.1)**, o sistema isola dados por usuário de forma segura. Ele permite cadastrar clientes, gerenciar múltiplos itens e controlar o ciclo de vida de propostas comerciais.

---

## 🧠 Engenharia de Prompt e Mitigação de Alucinações

Para estruturar o banco de dados, regras de privacidade e workflows no Bubble, utilizamos um modelo de contexto delimitado. O prompt enviado à LLM foi estruturado em tags XML para guiar o processo de inferência da IA.

Essa técnica de otimização de contexto restringiu o espaço de busca do modelo, impedindo a geração de relacionamentos redundantes. A definição explícita do escopo mitigou alucinações e comportamentos inesperados nas regras lógicas.

### Arquitetura de Delimitação de Contexto (Prompt XML)
```xml
<contexto_arquitetura>
  <plataforma>Bubble.io No-Code</plataforma>
  <restricao_relacionamento>FKs estritamente no lado N da relação. Proibido listas aninhadas.</restricao_relacionamento>
  <seguranca>Privacy Rules baseadas no ID do Creator. Isolamento multi-tenant.</seguranca>
</contexto_arquitetura>
```
## 📊 Análise Comparativa de Saídas da IA

Abaixo está o quadro comparativo que justifica as decisões tomadas na modelagem do sistema após testes de refinamento de prompt:

| Abordagem do Prompt | Comportamento da LLM (Saída) | Impacto na Engenharia de Software | Resultado |
| :--- | :--- | :--- | :--- |
| **Sem Delimitação** | Sugeriu listas de itens dentro da tabela pai (Orçamento). | Alucinação em escala: estouro do limite de peso de busca do Bubble. | **Rejeitado** |
| **Com Tag XML (Projetada)** | Separou as entidades e forçou o relacionamento 1:N via ID. | Total conformidade com a 3ª Forma Normal (3FN). | **Adotado** |

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

---

## ⚙️ Workflows do Sistema

O sistema executa 11 workflows documentados na página de clientes, cobrindo operações críticas de CRUD. Cada ação possui tratamento de exceção para guiar a experiência do usuário.

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

[⬅ Voltar ao portfólio](https://github.com/bryanthomas-dev/portif-lio_Bryan_Thomas)
