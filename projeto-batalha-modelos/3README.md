# ⚔️ SM3 — Batalha de Modelos & Engenharia de Prompt (XML)

## 📚 Descrição do Projeto

Este projeto teve como objetivo desenvolver um **Prompt Estruturado em XML** capaz de instruir múltiplos modelos de Inteligência Artificial a gerar uma aplicação **HTML5 Single Page**, contendo **CSS3 interno**, layout responsivo e organização visual padronizada.

A mesma estrutura de prompt foi aplicada simultaneamente em sete modelos distintos de IA generativa:

- ChatGPT
- Gemini
- DeepSeek
- Qwen
- Grok
- Maritaca
- Claude

O experimento foi desenvolvido na disciplina de **Engenharia de Prompt e Aplicações em IA (2026.1)** com foco em:

- Avaliar capacidade de interpretação semântica;
- Comparar fidelidade ao prompt original;
- Medir qualidade estrutural do HTML/CSS gerado;
- Identificar diferenças de inferência entre modelos;
- Comparar consumo de tokens e eficiência computacional;
- Analisar criatividade e coerência visual.

---

# 👥 Integrantes

- Bryan Thomas Montalvo Ferreira
- Welvis Ribeiro dos Santos
- Naum Gonçalves Gomes

---

# 🧠 Estrutura do Prompt XML

O prompt foi estruturado em XML para garantir:

- Hierarquia semântica;
- Redução de ambiguidade;
- Melhor previsibilidade de saída;
- Padronização entre modelos;
- Facilidade de parsing contextual.

## 📄 Prompt Utilizado

```xml
<tarefa>
  <objetivo>
    Criar uma página HTML5 única com CSS3 interno (single page).
  </objetivo>

  <tema>
    Receita de bolos
  </tema>

  <diretrizes_design>
    <layout>
      Responsivo e minimalista
    </layout>

    <paleta_cores>
      Marrom e Bege
    </paleta_cores>

    <tipografia>
      Sans-serif para títulos, Serif para corpo
    </tipografia>
  </diretrizes_design>

  <obrigatoriedades_tecnicas>
    <item>
      Menu de navegação funcional (âncoras)
    </item>

    <item>
      Seção de portfólio ou galeria
    </item>

    <item>
      Rodapé com informações de contato simuladas
    </item>

    <item>
      Bolo de chocolate
    </item>
  </obrigatoriedades_tecnicas>

  <metrica_obrigatoria>
    Ao final da resposta, informe uma estimativa de quantos tokens foram gerados.
  </metrica_obrigatoria>
</tarefa>
```

---

# 🧩 Estrutura de Arquivos

```txt
📁 projeto-sm3/
│
├── README.md
├── requirements.txt
├── prompt.xml
│
├── outputs/
│   ├── chatgpt.html
│   ├── gemini.html
│   ├── deepseek.html
│   ├── qwen.html
│   ├── grok.html
│   ├── maritaca.html
│   └── claude.html
│
└── assets/
    └── grafico-comparativo.png
```

---

# ⚙️ Requirements

Arquivo `requirements.txt` utilizado no projeto:

```txt
matplotlib>=3.8.0
pandas>=2.2.0
numpy>=1.26.0
```

---

# 🚀 Tecnologias Utilizadas

## Linguagens

- HTML5
- CSS3
- XML

## Ferramentas de IA

| Modelo | Finalidade |
|---|---|
| ChatGPT | Geração de HTML/CSS |
| Gemini | Interpretação estrutural |
| DeepSeek | Inferência de código |
| Qwen | Geração rápida |
| Grok | Estruturação visual |
| Maritaca | Resposta em português |
| Claude | Refinamento avançado |

---

# 🔬 Metodologia de Avaliação

A análise comparativa foi baseada em métricas quantitativas e qualitativas.

## Critérios Avaliados

- Fidelidade ao prompt XML;
- Precisão sintática do HTML5;
- Qualidade do CSS3;
- Responsividade;
- Criatividade visual;
- Quantidade de erros estruturais;
- Eficiência de inferência;
- Consumo de tokens.

---

# 📊 Resultados Comparativos

| Critério | ChatGPT | Gemini | DeepSeek | Qwen | Grok | Maritaca | Claude |
|---|---|---|---|---|---|---|---|
| Precisão do Prompt | 7/10 | 9/10 | 7/10 | 7/10 | 8,5/10 | 7/10 | **10/10** |
| Precisão do HTML | 6,5/10 | 9/10 | 7/10 | 4/10 | 8/10 | 5/10 | **10/10** |
| Criatividade | 3/10 | 9/10 | 7/10 | 3/10 | 8/10 | 2/10 | **10/10** |
| Bugs Encontrados | 1 erro | 1 erro | 2 erros | 0 erros | 1 erro | 1 erro | **Nenhum** |
| Tokens Estimados | ~1000 | ~1450 | ~3000 | ~1450 | ~4820 | ~1300 | ~10500 |

---

# 📈 Gráfico Comparativo de Performance

```txt
Precisão Geral dos Modelos (%)

Claude     ██████████████ 100%
Gemini     ████████████░ 90%
Grok       ██████████░░ 85%
DeepSeek   ████████░░░░ 70%
ChatGPT    ████████░░░░ 68%
Qwen       ██████░░░░░░ 55%
Maritaca   █████░░░░░░░ 47%
```

---

# 🧠 Análise Técnica dos Resultados

## 🔹 Claude

### Pontos Fortes

- Melhor capacidade de inferência contextual;
- Interpretação semântica avançada do XML;
- Estrutura HTML semanticamente correta;
- CSS mais sofisticado;
- Maior nível de responsividade;
- Melhor gerenciamento hierárquico de componentes.

### Motivos da Superioridade

O Claude apresentou maior eficiência em:

- Parsing estrutural;
- Retenção contextual;
- Inferência semântica;
- Organização de layout;
- Consistência visual;
- Aplicação de estilos modernos.

Além disso, demonstrou menor ocorrência de:

- Alucinação estrutural;
- Quebra de hierarquia HTML;
- Inconsistência de CSS;
- Ambiguidade interpretativa.

---

## 🔹 Gemini

### Destaques

- Excelente interpretação de requisitos;
- Boa responsividade;
- HTML semanticamente organizado.

### Limitações

- Pequenas inconsistências visuais;
- Menor refinamento estético comparado ao Claude.

---

## 🔹 DeepSeek

### Destaques

- Boa geração de código;
- Estrutura lógica consistente.

### Problemas Encontrados

- CSS redundante;
- Alguns componentes desalinhados;
- Maior incidência de bugs.

---

## 🔹 Qwen

### Destaques

- Rapidez de inferência;
- Baixo custo computacional.

### Problemas Encontrados

- Baixa criatividade;
- Estrutura HTML simplificada;
- Menor aderência ao prompt.

---

## 🔹 Grok

### Destaques

- Boa criatividade visual;
- Melhor uso de animações.

### Problemas Encontrados

- Pequenos erros semânticos;
- Responsividade inconsistente.

---

## 🔹 Maritaca

### Destaques

- Respostas em português natural;
- Boa contextualização textual.

### Problemas Encontrados

- Estrutura HTML limitada;
- Pouca sofisticação visual;
- Inferência técnica inferior aos demais modelos.

---

# ⚡ Comparação Técnica de Inferência

| Modelo | Inferência | Criatividade | Precisão Técnica | Eficiência |
|---|---|---|---|---|
| Claude | Alta | Alta | Alta | Média |
| Gemini | Alta | Média | Alta | Alta |
| Grok | Média | Alta | Média | Média |
| DeepSeek | Média | Média | Média | Média |
| ChatGPT | Média | Média | Média | Alta |
| Qwen | Baixa | Baixa | Baixa | Alta |
| Maritaca | Baixa | Baixa | Baixa | Média |

---

# 🏆 Conclusão Final

A análise demonstrou diferenças significativas entre os modelos avaliados, especialmente em:

- Capacidade de inferência;
- Interpretação semântica;
- Organização estrutural;
- Precisão técnica;
- Criatividade visual.

O modelo **Claude** apresentou o melhor desempenho global devido à combinação de:

- Alta compreensão contextual;
- Melhor aplicação de hierarquia HTML;
- CSS mais refinado;
- Maior fidelidade ao prompt XML;
- Menor taxa de erros estruturais.

Apesar do elevado consumo de tokens (~10.500), o modelo compensou esse custo com uma saída significativamente mais robusta e tecnicamente superior.

Já modelos como Qwen e Maritaca apresentaram maior velocidade e menor custo computacional, porém com perda perceptível de qualidade estrutural e criatividade.

---

# 📌 Considerações Acadêmicas

Este experimento evidencia como a engenharia de prompt influencia diretamente:

- Qualidade de inferência;
- Precisão semântica;
- Estruturação de código;
- Consistência de respostas em modelos generativos.

Também demonstra que prompts estruturados em XML podem reduzir ambiguidades e melhorar a previsibilidade das respostas em tarefas técnicas.

---

# 📎 Execução do Projeto

## Passo 1 — Clonar o Repositório

```bash
git clone https://github.com/seu-repositorio/projeto-sm3.git
```

## Passo 2 — Acessar a Pasta

```bash
cd projeto-sm3
```

## Passo 3 — Instalar Dependências

```bash
pip install -r requirements.txt
```

## Passo 4 — Abrir os Arquivos HTML

Abra qualquer arquivo da pasta `outputs/` em seu navegador.

Exemplo:

```bash
outputs/claude.html
```

---

# 📄 Licença

Projeto acadêmico desenvolvido exclusivamente para fins educacionais.
