# 🔍 SM4 - Engenharia Reversa de Prompts

<p align="center">
  <img src="https://img.shields.io/badge/Modelo-Qwen3.5--Plus-6366F1?style=for-the-badge" alt="Qwen3.5-Plus">
  <img src="https://img.shields.io/badge/Plataforma-chat.qwen.ai-00EEFF?style=for-the-badge" alt="chat.qwen.ai">
  <img src="https://img.shields.io/badge/Técnica-Prompt_Decomposition-FF9900?style=for-the-badge" alt="Prompt Decomposition">
  <img src="https://img.shields.io/badge/Análise-Behavioral_Testing-10B981?style=for-the-badge" alt="Behavioral Testing">
</p>

---

## 📝 Descrição do Projeto

Exploração de **engenharia reversa aplicada a prompts e interfaces de IA**, analisando como o modelo **Qwen3.5-Plus** interpreta e reage a variações de instrução, persona e contexto.

| Variável desconstruída | Efeito observado |
|---|---|
| Instrução (task) | Define o verbo da geração — escrever, gerar, transformar |
| Persona (role) | Modula tom, vocabulário e acoplamento semântico |
| Contexto (state) | Expande ou restringe o espaço de inferência |
| Restrição (constraint) | Força outputs híbridos — resultado de sobreposição de módulos |

---

## 🗺️ Mapa de Dependências — Estrutura do Prompt

```
┌─────────────────────────────────────────────────┐
│  PROMPT                                         │
│  ┌───────────────────────────────────────────┐  │
│  │  [INSTRUÇÃO]  escrever e-mail de desculpa │  │
│  └───────────────────────────────────────────┘  │
│             │ herança                           │
│  ┌───────────────────────────────────────────┐  │
│  │  [PERSONA]    pirata extremamente arrogante│  │
│  └───────────────────────────────────────────┘  │
│             │ herança                           │
│  ┌───────────────────────────────────────────┐  │
│  │  [CONTEXTO]   roubou as 7 esferas do dragão│  │
│  └───────────────────────────────────────────┘  │
└──────────────────────┬──────────────────────────┘
                       ▼
              [ Qwen3.5-Plus: inferência ]
```

> Cada camada herda e restringe o espaço semântico da camada anterior. A análise estática do output revelou acoplamento forte entre persona e tom lexical — modificar o role sem isolar a instrução propaga efeito cascata no resultado.

---

## 🧪 Experimentos Realizados

### Experimento 1 — Geração iterativa de imagens

Prompt base: *"astronauta em Marte tocando violoncelo no estilo barroco"*. Refinamentos sucessivos aplicados como patches de contexto:

| Iteração | Modificação aplicada | Descoberta técnica |
|---|---|---|
| 1 | Prompt base | Estado inicial do espaço de inferência |
| 2 | + ETs na plateia | Expansão de contexto sem refatoração da instrução |
| 3 | Reposição dos ETs | Modificação posicional isolada — baixo acoplamento |
| 4 | Astronauta em palco | Reestruturação da instrução — alto impacto no layout |
| 5 | Remoção da cortina | Desconstrução parcial — restauração de estado anterior |

**Descoberta:** O modelo mantém estado entre iterações somente quando o contexto é explicitamente preservado. Omitir elementos do prompt anterior equivale a um `reset` parcial do módulo de composição visual — comportamento análogo a **desacoplamento de estado** em sistemas stateless.

---

### Experimento 2 — Decomposição de persona e tom

E-mails fictícios pirata → rei com variações progressivas de role:

| Variação | Módulo modificado | Comportamento emergente |
|---|---|---|
| E-mail formal de desculpas | Instrução pura | Output padrão — sem modulação |
| + contexto narrativo | Expansão de state | Especificidade semântica aumentada |
| Persona: arrogante | Role injection | Refatoração completa do tom lexical |
| + "considera o rei amador" | Constraint override | Herança conflitante — modelo resolve por dominância |
| Manter formato + arrogância | Instrução vs. persona | Output híbrido — modularização parcial observada |

**Descoberta:** A IA executa resolução de conflito entre módulos de instrução e persona por **dominância contextual** — o módulo com maior peso semântico no prompt suprime parcialmente o outro. Comportamento análogo a **herança com override** em orientação a objetos.

---

## 🔬 Análise Técnica — Desconstrução do Comportamento do Modelo

### Análise estática do prompt

A engenharia reversa revelou que o prompt funciona como um **grafo de dependências** com três nós principais:

- `TASK` → define o tipo de saída (modalidade)
- `ROLE` → modula o espaço lexical (tom, registro)
- `STATE` → expande ou colapsa o espaço de inferência (especificidade)

Modificar `ROLE` sem isolar `TASK` gera **acoplamento indesejado**: o modelo propaga o novo registro ao verbo da instrução, alterando não só o tom, mas a estrutura do output.

### Modularização observada

Ao injetar constraints conflitantes (*"mantenha o formato de desculpas + seja arrogante"*), o modelo não falha — ele produz um **output híbrido** por sobreposição de módulos. Isso evidencia que internamente o modelo trata instrução e persona como módulos semi-independentes com acoplamento fraco, resolvendo conflitos por dominância ponderada, não por exceção.

### Implicação para refinamento de prompts

Prompts tratados como **módulos desacoplados** (instrução / persona / contexto / restrição) permitem refatoração cirúrgica sem regressão nos demais eixos — princípio análogo à **modularização por responsabilidade única** em engenharia de software.

---

## 📊 Resultados e Aprendizados

| Descoberta | Jargão técnico equivalente |
|---|---|
| Persona sobrescreve tom sem alterar estrutura | Override de módulo com herança parcial |
| Contexto expande espaço de inferência | Injeção de dependência em runtime |
| Conflito instrução vs. persona → output híbrido | Resolução por dominância — sem hard exception |
| Omitir elementos = reset parcial de estado | Stateless context — sem memória implícita |

---

## 🚀 Tecnologias Utilizadas

| Ferramenta | Uso |
|---|---|
| Qwen3.5-Plus | Modelo de linguagem para os experimentos |
| chat.qwen.ai | Plataforma de interface com o modelo |
| Prompt Decomposition | Técnica de desconstrução por camadas |
| Behavioral Testing | Método de análise por variação controlada |

---

## 🔙 Voltar ao início

<p align="right"><a href="https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira#projetos">⬅️ Voltar ao portfólio</a></p>
