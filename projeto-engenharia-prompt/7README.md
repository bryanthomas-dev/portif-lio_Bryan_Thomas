# 🛠️ SM7 - Engenharia de Software e IA com Bubble.io

<p align="center">
  <img src="https://img.shields.io/badge/Plataforma-Bubble.io-00EEFF?style=for-the-badge&logo=bubble&logoColor=black" alt="Bubble.io">
  <img src="https://img.shields.io/badge/Engenharia_de_Prompt-XML_Directives-FF9900?style=for-the-badge" alt="Prompt Engineering">
  <img src="https://img.shields.io/badge/LLM_Aplicada-Claude_3.5_Sonnet-D97706?style=for-the-badge" alt="Claude 3.5 Sonnet">
  <img src="https://img.shields.io/badge/Técnica-Context_Delimitation-6366F1?style=for-the-badge" alt="Context Delimitation">
  <img src="https://img.shields.io/badge/Paradigma-No--Code_First-10B981?style=for-the-badge" alt="No-Code First">
</p>

---

## 📝 Descrição do Projeto

O **OrcaFlow** é um sistema de gestão de orçamentos empresariais construído na plataforma no-code **Bubble.io**, desenvolvido para a disciplina de **Engenharia de Software e IA (2026.1)**.

| Característica | Detalhe |
|---|---|
| Plataforma | Bubble.io (No-Code) |
| LLM utilizada | Claude 3.5 Sonnet |
| Técnica de IA | Engenharia de Prompt com XML Directives |
| Isolamento de dados | Multi-Tenancy por usuário |
| Workflows documentados | 11 operações CRUD |

---

## 🗃️ Modelagem do Banco de Dados

Banco de dados relacional estruturado em **4 entidades principais**:

| Entidade | Responsabilidade |
|---|---|
| **Usuario (User)** | Perfis: Administrador, Vendedor ou Visualizador |
| **Cliente (Client)** | Dados de contato e vinculação corporativa |
| **Orçamento (Quote)** | Título, valor, validade e status da proposta |
| **Item do Orçamento (QuoteItem)** | Descrição, quantidade e preço unitário |

> 💡 **Boa prática aplicada:** Chaves estrangeiras (FKs) mapeadas no lado N da relação. Evita sobrecarga de carregamento quando tabelas ultrapassam 100 registros no Bubble.

### Estados de Ciclo de Vida (Option Sets)

`Pendente` | `Aprovado` | `Rejeitado` | `Em Revisão` | `Expirado`

---

## 🔐 Regras de Privacidade (Multi-Tenancy)

Todas as tabelas possuem regras de privacidade configuradas para isolamento lógico:

| Tabela | Regra de Privacidade |
|---|---|
| Cliente | `This Client's Creator is Current User` |
| Orçamento | `This Quote's Creator is Current User` |
| Item | `This QuoteItem's Quote's Creator is Current User` |

<p align="center">
  <img src="data_privacy%20(1).jpeg" alt="Configuração de privacidade no Bubble" width="600"/>
</p>

---

## ⚙️ Workflows do Sistema

O sistema executa **11 workflows** documentados na página de clientes, cobrindo operações críticas de CRUD. Cada ação possui tratamento de exceção para guiar a experiência do usuário.

<p align="center">
  <img src="Workflow%20(1).jpeg" alt="Workflows do sistema no Bubble" width="600"/>
</p>

---

## 🧠 Engenharia de Prompt — Estratégia Anti-Alucinação

A lógica do sistema foi gerada com Claude 3.5 Sonnet utilizando **XML Directives** como técnica central de estruturação contextual. As decisões de design de prompt seguiram princípios de engenharia de software:

### Estrutura das Diretrizes Contextuais

```xml
<context>
  Plataforma: Bubble.io (No-Code). Sem acesso a código-fonte nativo.
  Entidades: Usuario, Cliente, Orçamento, QuoteItem.
  Restrição: Toda FK deve estar no lado N da relação.
</context>

<constraints>
  - Nunca sugerir código JavaScript/backend direto no Bubble
  - Respeitar o modelo de privacidade multi-tenant por Creator
  - Workflows devem incluir tratamento de erro explícito
</constraints>

<output_format>
  Retornar apenas passos clicáveis dentro do editor Bubble.
  Sem ambiguidades: nomear campo, tipo e tabela em cada instrução.
</output_format>
```

### Por que isso mitiga alucinações?

| Problema comum em LLMs | Mitigação aplicada |
|---|---|
| Sugerir recursos inexistentes na plataforma | `<constraints>` delimita o escopo ao Bubble.io |
| Gerar FKs no lado errado da relação | Regra explícita no `<context>` |
| Workflows sem tratamento de erro | `<output_format>` exige inclusão de fallback |
| Misturar paradigmas no-code com código | Restrição explícita no `<constraints>` |

> 🎯 **Decisão de engenharia:** Ao delimitar o contexto com XML, o modelo opera dentro de um "espaço de solução restrito", reduzindo drasticamente respostas fora do domínio da plataforma.

---

## 🚨 Estratégia de Saída — Vendor Lock-in

**Risco Identificado:** O Bubble retém o código-fonte gerado, criando dependência tecnológica severa (*Vendor Lock-in*).

**Mitigação Arquitetural:** Habilitação da **Data API do Bubble** para exportar registros em JSON:

```plaintext
GET [https://appname.bubbleapps.io/api/1.1/obj/client](https://appname.bubbleapps.io/api/1.1/obj/client)
GET [https://appname.bubbleapps.io/api/1.1/obj/quote](https://appname.bubbleapps.io/api/1.1/obj/quote)
GET [https://appname.bubbleapps.io/api/1.1/obj/quoteitem](https://appname.bubbleapps.io/api/1.1/obj/quoteitem)
```
### Stack de Migração Planejada

| Camada | Tecnologia |
|---|---|
| Backend | Node.js + Express |
| Banco de Dados | PostgreSQL |
| Frontend | React + JWT |
| ORM | Prisma ou Sequelize |

---

## 📊 Resultados e Aprendizados

| Entrega | Resultado |
|---|---|
| CRUD completo | ✅ Clientes e Orçamentos funcionais |
| Modelagem relacional | ✅ Boas práticas aplicadas em ambiente no-code |
| Risco de Vendor Lock-in | ✅ Mitigado com estratégia de exportação via Data API |
| Engenharia de Prompt | ✅ XML Directives reduziram retrabalho e alucinações |

> 🔑 **Aprendizado central:** Engenharia de Software vai além do código — envolve arquitetura, segurança, planejamento de continuidade **e** a capacidade de estruturar contexto preciso para sistemas de IA colaborativos.

---

## 🚀 Tecnologias Utilizadas

| Ferramenta | Uso |
|---|---|
| Bubble.io | Plataforma No-Code principal |
| Claude 3.5 Sonnet | LLM para geração de lógica e workflows |
| XML Directives | Técnica de Engenharia de Prompt |
| Bubble Database | Estrutura relacional nativa |
| Data API (Bubble) | Exportação e estratégia anti-lock-in |

---

## 🔙 Voltar ao início

<p align="right"><a href="https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira">⬅️ Voltar ao início</a></p>
