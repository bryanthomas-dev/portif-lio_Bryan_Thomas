# 🏁 SM1 - A Corrida do Prompt

> **Disciplina:** Engenharia de Prompt e Aplicações em IA (2026.1)  
> **Foco Técnico:** Técnicas de Contextualização, Few-Shot Prompting e Chain-of-Thought (CoT)

---

## 📝 Descrição do Projeto

Este projeto consiste na exploração e análise analítica sobre o impacto das técnicas de Engenharia de Prompt no comportamento, precisão e qualidade das respostas geradas por Grandes Modelos de Linguagem (LLMs). O objetivo principal foi mitigar alucinações e otimizar a assertividade dos modelos por meio de estruturas bem definidas.

### 📷 Fluxo de Execução e Interação
![Fluxo de Interação com LLM](Captura%20de%20tela%202026-03-02%20222537.png)
*Figura 1: Indexação do fluxo de engenharia de prompt aplicado nas interações com as IAs.*

---

## 🚀 Tecnologias Utilizadas

* **Modelos de Linguagem (LLMs):** Anthropic Claude, OpenAI ChatGPT, Alibaba Qwen, Google Gemini.
* **Plataformas de Execução:** Interfaces web oficiais e playgrounds de desenvolvedor.
* **Paradigma:** Engenharia de Prompt aplicada em Linguagem Natural (Português).

---

## 🧠 Profundidade e Redação Técnica: Pilares Utilizados

Para obter o máximo desempenho de cada LLM, as interações não foram baseadas em perguntas simples (prompts diretos). Foram aplicados e comparados metodologicamente os seguintes pilares de estruturação de contexto:

### 1. Instruções Baseadas em Papel (*Role-Playing*)
Atribuiu-se uma persona específica e hiper-especializada ao modelo antes da execução da tarefa principal. Isolar o escopo de atuação da IA alterou o tom, a escolha do vocabulário técnico e a profundidade das respostas, reduzindo a superficialidade do output.

### 2. Aprendizado com Poucos Exemplos (*Few-Shot Prompting*)
Forneceu-se exemplos explícitos de entradas e saídas esperadas dentro da estrutura do prompt. A inclusão dessas amostras serviu como uma âncora comportamental para o modelo, garantindo que o formato final do texto mantivesse a consistência sintática e estrutural exigida pelo projeto.

### 3. Cadeia de Pensamento (*Chain-of-Thought - CoT*)
Forçou-se o modelo a quebrar problemas complexos em etapas lógicas e sequenciais antes de entregar a resposta final (usando gatilhos textuais como *"pense passo a passo"*). Essa abordagem analítica demonstrou-se crucial para tarefas que exigem raciocínio lógico, pois permitiu rastrear falhas de inferência e melhorou drasticamente a exatidão dos resultados gerados.

---

## 📊 Resultados e Aprendizados Analíticos

* **Sensibilidade ao Contexto:** Pequenas variações de tokens na delimitação de tarefas geraram comportamentos completamente distintos nas IAs.
* **Análise Comparativa:** O modelo Claude demonstrou maior aderência e refinamento sintático ao *Few-Shot Prompting*, enquanto o ChatGPT apresentou respostas rápidas e estruturadas sob o efeito de *Chain-of-Thought*.
* **Mitigação de Ruídos:** A estruturação correta eliminou respostas evasivas e padronizou o formato de entrega das informações.

---

## 🔧 Como Executar

Para reproduzir os experimentos realizados neste laboratório, siga o passo a passo abaixo:

1. **Acessar as Plataformas:** Abra a interface do modelo de linguagem de sua preferência (Claude, ChatGPT, Gemini ou Qwen).
2. **Localizar os Prompts:** Navegue até a pasta de arquivos deste diretório e selecione o arquivo com os prompts documentados (`prompts.md` ou equivalente).
3. **Injetar o Contexto:** Copie o prompt estruturado contendo a técnica selecionada (*Few-Shot* ou *CoT*).
4. **Executar a Tarefa:** Submeta o prompt ao modelo e analise criticamente se a cadeia de pensamento gerada corresponde aos parâmetros esperados.
5. **Comparar Outputs:** Repita o processo em ferramentas distintas utilizando as mesmas variáveis de entrada para observar a variação de comportamento.

---

## 🔙 Voltar ao início

<p align="right"><a href="https://github.com/bryanthomas-dev/portfolio-bryan-thomas-montalvo-ferreira">⬅️ Voltar ao início</a></p>
