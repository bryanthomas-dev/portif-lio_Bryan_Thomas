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

O **OrcaFlow** é um sistema de gestão de orçamentos empresariais construído no Bubble.io para a disciplina de **Engenharia de Software e IA (2026.1)**.

| Característica | Detalhe |
|---|---|
| Plataforma | Bubble.io (No-Code) |
| LLM utilizada | Claude 3.5 Sonnet |
| Técnica de IA | XML Directives |
| Isolamento de dados | Multi-Tenancy por Creator |
| Workflows documentados | 11 operações CRUD |

---

## 🗃️ Modelagem do Banco de Dados

| Entidade | Responsabilidade |
|---|---|
| **Usuario (User)** | Perfis: Administrador, Vendedor ou Visualizador |
| **Cliente (Client)** | Dados de contato e vinculação corporativa |
| **Orçamento (Quote)** | Título, valor, validade e status da proposta |
| **Item (QuoteItem)** | Descrição, quantidade e preço unitário |

> 💡 FKs mapeadas no lado N da relação — evita sobrecarga de carregamento acima de 100 registros no Bubble.

### Estados de ciclo de vida

`Pendente` | `Aprovado` | `Rejeitado` | `Em Revisão` | `Expirado`

---

## 🔐 Regras de Privacidade (Multi-Tenancy)

| Tabela | Regra configurada |
|---|---|
| Cliente | `This Client's Creator is Current User` |
| Orçamento | `This Quote's Creator is Current User` |
| Item | `This QuoteItem's Quote's Creator is Current User` |

<p align="center">
  <img src="data_privacy%20(1).jpeg" alt="Configuração de privacidade no Bubble" width="600"/>
</p>

---

## ⚙️ Workflows do Sistema

11 workflows documentados cobrindo operações CRUD completas. Cada ação possui tratamento de exceção explícito para guiar a experiência do usuário.

<p align="center">
  <img src="Workflow%20(1).jpeg" alt="Workflows do sistema no Bubble" width="600"/>
</p>

---

## 🧠 Engenharia de Prompt — Estratégia Anti-Alucinação

### Arquitetura de contexto aplicada

A lógica do sistema foi gerada com **XML Directives** como técnica de delimitação contextual. Cada tag mapeia diretamente para um princípio de arquitetura de software:

| Diretriz | Analogia arquitetural | Função anti-alucinação |
|---|---|---|
| `<context>` | Schema de dados | Define contrato entre sistema e modelo |
| `<constraints>` | Regras de negócio | Restringe espaço de soluções válidas |
| `<output_format>` | Contrato de interface | Garante saída consumível sem retrabalho |

### Estrutura das diretrizes

```xml
<context>
  Plataforma: Bubble.io. Sem acesso a código-fonte nativo.
  Entidades: Usuario, Cliente, Orçamento, QuoteItem.
  Restrição estrutural: FK sempre no lado N da relação.
</context>
```

```xml
<constraints>
  - Nunca sugerir código JavaScript/backend direto no Bubble
  - Respeitar modelo de privacidade multi-tenant por Creator
  - Workflows devem incluir fallback de erro explícito
</constraints>
```

```xml
<output_format>
  Retornar apenas passos clicáveis no editor Bubble.
  Nomear campo, tipo e tabela em cada instrução.
</output_format>
```

### Otimização de tokens de contexto

Ao delimitar o escopo com XML, o modelo concentra peso de atenção nas soluções dentro do domínio Bubble.io. Tokens que seriam alocados para raciocínio sobre backend, SQL direto ou APIs externas são suprimidos pelas `<constraints>`, reduzindo alucinações sobre recursos inexistentes na plataforma.

### Saídas comparativas — com vs. sem delimitação

| Cenário | Sem delimitação | Com XML Directives |
|---|---|---|
| FK entre Quote e QuoteItem | Sugeriu campo no lado 1 (errado) | Corretamente no lado N |
| Tratamento de erro no workflow | Omitido | Incluído com fallback explícito |
| Instrução de privacidade | Genérica, sem campo Creator | Regra exata: `Creator is Current User` |
| Tipo de saída | Pseudocódigo JavaScript | Passos clicáveis no editor Bubble |

> 🎯 **Decisão de engenharia:** O modelo opera em espaço de solução restrito — análogo a um compilador com escopo de variáveis declarado. O que não está no contexto não pode ser inferido como válido.

---

## 🚨 Estratégia de Saída — Vendor Lock-in

**Risco:** O Bubble retém o código-fonte, criando dependência tecnológica severa.

**Mitigação:** Data API habilitada para exportação em JSON.

```
GET https://appname.bubbleapps.io/api/1.1/obj/client
GET https://appname.bubbleapps.io/api/1.1/obj/quote
GET https://appname.bubbleapps.io/api/1.1/obj/quoteitem
```

### Stack de migração planejada

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
| Modelagem relacional | ✅ Boas práticas aplicadas em no-code |
| Vendor Lock-in | ✅ Mitigado com exportação via Data API |
| Engenharia de Prompt | ✅ XML Directives eliminaram retrabalho e alucinações |

> 🔑 Engenharia de Software vai além do código — envolve arquitetura, segurança, continuidade **e** estruturação precisa de contexto para sistemas de IA.

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

<p align="right"><a href="https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira">⬅️ Voltar ao portfólio</a></p>
