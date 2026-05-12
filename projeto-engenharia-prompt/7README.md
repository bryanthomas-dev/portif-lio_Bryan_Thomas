# 🛠️ SM7 - Engenharia de Software e IA com Bubble.io

## 📝 Descrição do Projeto

Este projeto consistiu no desenvolvimento do **OrcaFlow**, um sistema de gestão de orçamentos empresariais construído integralmente com a plataforma **no-code Bubble.io**, seguindo boas práticas de Engenharia de Software: modelagem de banco de dados, regras de privacidade, workflows documentados e estratégia de saída (vendor lock-in).

Desenvolvido como parte da disciplina de **Engenharia de Software e IA (2026.1)**, o OrcaFlow permite que usuários cadastrem clientes, criem e gerenciem orçamentos com múltiplos itens, controlem status e visualizem dados de forma segura e isolada por usuário.

## 🗃️ Modelagem do Banco de Dados

O sistema foi estruturado com 4 entidades principais:

| Tabela | Descrição |
|---|---|
| **Usuario (User)** | Perfis: Administrador, Vendedor ou Visualizador |
| **Cliente (Client)** | Dados de contato e empresa do cliente |
| **Orçamento (Quote)** | Título, valor, validade e status do orçamento |
| **Item do Orçamento (QuoteItem)** | Descrição, quantidade e preço unitário |

**Boa prática aplicada:** FKs sempre no lado N da relação. Nunca criar lista de filhos dentro do pai quando houver risco de ultrapassar 100 itens.

### Option Sets de Status
`Pendente` | `Aprovado` | `Rejeitado` | `Em Revisão` | `Expirado`

## 🔐 Regras de Privacidade

Todas as tabelas possuem regras de privacidade configuradas no Bubble:
- **Cliente:** `This Client's Creator is Current User`
- **Orçamento:** `This Quote's Creator is Current User`
- **Item:** `This QuoteItem's Quote's Creator is Current User`

![Configuração de privacidade no Bubble](./privacidade_bubble.png)
*Figura 1: Painel de privacidade do Bubble com regras aplicadas por tabela.*

## ⚙️ Workflows

O sistema conta com 11 workflows documentados na página de clientes, cobrindo operações de criação, edição, exclusão e cancelamento com feedback visual ao usuário.

![Workflows do sistema](./workflows_bubble.png)
*Figura 2: Painel de workflows da página de clientes no Bubble.*

## 🚨 Estratégia de Saída — Vendor Lock-in

**Risco identificado:** O Bubble retém o código-fonte gerado, caracterizando risco de Vendor Lock-in.

**Estratégia de mitigação:** Habilitar a **Data API do Bubble** para exportar todos os registros em formato JSON via requisições GET autenticadas:

```
GET https://appname.bubbleapps.io/api/1.1/obj/client
GET https://appname.bubbleapps.io/api/1.1/obj/quote
GET https://appname.bubbleapps.io/api/1.1/obj/quoteitem
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
